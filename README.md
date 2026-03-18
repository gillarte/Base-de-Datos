#BBDD
DROP DATABASE IF EXISTS compras;
CREATE DATABASE compras;
USE compras;

CREATE TABLE ciudades (
id INT PRIMARY KEY AUTO_INCREMENT,codigopostal INT
);

CREATE TABLE productos (
id INT PRIMARY KEY AUTO_INCREMENT, nombre_producto VARCHAR(60), precio
DOUBLE,stock INT
);

CREATE TABLE cliente (
id INT PRIMARY KEY AUTO_INCREMENT,dni INT, nombre VARCHAR(60),ciudad_id
INT,FOREIGN KEY (ciudad_id) REFERENCES ciudades(id)
);

CREATE TABLE provincias (
id INT PRIMARY KEY AUTO_INCREMENT,nombre_provincia VARCHAR(60), habitantes
INT,ciudad_id INT,FOREIGN KEY (ciudad_id) REFERENCES ciudades(id)
);

CREATE TABLE compras (
id_compra INT PRIMARY KEY AUTO_INCREMENT,id_producto INT,id_cliente
INT,FOREIGN KEY (id_producto) REFERENCES productos(id),FOREIGN KEY(id_cliente)
REFERENCES cliente(id)
);
INSERT INTO ciudades (codigopostal) VALUES
(1000),(2000),(3000),(4000),(5000);

INSERT INTO provincias (nombre_provincia, habitantes, ciudad_id) VALUES
(&#39;Buenos Aires&#39;, 17000000, 1),(&#39;Santa Fe&#39;, 3500000, 2),(&#39;Cordoba&#39;, 3800000,
3),(&#39;Mendoza&#39;, 2000000, 4),(&#39;Salta&#39;, 1400000, 5);

INSERT INTO cliente (dni, nombre, ciudad_id) VALUES
(30111222, &#39;Juan Perez&#39;, 1),(28999888, &#39;Maria Lopez&#39;, 2),(31222333, &#39;Carlos Diaz&#39;,
3),(33444555, &#39;Ana Torres&#39;, 4),(35666777, &#39;Luis Gomez&#39;, 5);

INSERT INTO productos (nombre_producto, precio, stock) VALUES
(&#39;Laptop&#39;, 1200.50, 10),(&#39;Mouse&#39;, 25.99, 50),(&#39;Teclado&#39;, 45.00, 30),(&#39;Monitor&#39;, 300.75,
15),(&#39;Auriculares&#39;, 80.20, 20);

INSERT INTO compras (id_producto) VALUES
(1),(2),(3),(4),(5);
