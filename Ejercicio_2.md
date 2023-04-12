# EJERCICIOS DE APRENDIZAJE
## Ejercicio_2
Diagrama EMR de la Base de Datos Tienda: https://github.com/FullStackEggDRoa/dia_93/blob/f835c7d3424a0675f8070c5452d98c0f1d7094c8/Ejercicio_2.mwb 
### 1. Lista el nombre de todos los productos que hay en la tabla producto.
```
SELECT nombre AS "Nombre Producto" FROM producto;
+---------------------------------+
| Nombre Producto                 |
+---------------------------------+
| Disco duro SATA3 1TB            |
| Memoria RAM DDR4 8GB            |
| Disco SSD 1 TB                  |
| GeForce GTX 1050Ti              |
| GeForce GTX 1080 Xtreme         |
| Monitor 24 LED Full HD          |
| Monitor 27 LED Full HD          |
| Portátil Yoga 520               |
| Portátil Ideapd 320             |
| Impresora HP Deskjet 3720       |
| Impresora HP Laserjet Pro M26nw |
+---------------------------------+
```
### 2. Lista los nombres y los precios de todos los productos de la tabla producto.
```
SELECT nombre AS "Nombre Producto", precio AS "Precio Unitario" FROM producto;
+---------------------------------+-----------------+
| Nombre Producto                 | Precio Unitario |
+---------------------------------+-----------------+
| Disco duro SATA3 1TB            |           86.99 |
| Memoria RAM DDR4 8GB            |             120 |
| Disco SSD 1 TB                  |          150.99 |
| GeForce GTX 1050Ti              |             185 |
| GeForce GTX 1080 Xtreme         |             755 |
| Monitor 24 LED Full HD          |             202 |
| Monitor 27 LED Full HD          |          245.99 |
| Portátil Yoga 520               |             559 |
| Portátil Ideapd 320             |             444 |
| Impresora HP Deskjet 3720       |           59.99 |
| Impresora HP Laserjet Pro M26nw |             180 |
+---------------------------------+-----------------+
```
### 3. Lista todas las columnas de la tabla producto.
```
SELECT * FROM producto;
+--------+---------------------------------+--------+-------------------+
| codigo | nombre                          | precio | codigo_fabricante |
+--------+---------------------------------+--------+-------------------+
|      1 | Disco duro SATA3 1TB            |  86.99 |                 5 |
|      2 | Memoria RAM DDR4 8GB            |    120 |                 6 |
|      3 | Disco SSD 1 TB                  | 150.99 |                 4 |
|      4 | GeForce GTX 1050Ti              |    185 |                 7 |
|      5 | GeForce GTX 1080 Xtreme         |    755 |                 6 |
|      6 | Monitor 24 LED Full HD          |    202 |                 1 |
|      7 | Monitor 27 LED Full HD          | 245.99 |                 1 |
|      8 | Portátil Yoga 520               |    559 |                 2 |
|      9 | Portátil Ideapd 320             |    444 |                 2 |
|     10 | Impresora HP Deskjet 3720       |  59.99 |                 3 |
|     11 | Impresora HP Laserjet Pro M26nw |    180 |                 3 |
+--------+---------------------------------+--------+-------------------+
```
### 4. Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.
```
SELECT nombre AS "Nombre Producto", ROUND(precio) AS "Precio U.  Redondeado" FROM producto;
+---------------------------------+-----------------------+
| Nombre Producto                 | Precio U.  Redondeado |
+---------------------------------+-----------------------+
| Disco duro SATA3 1TB            |                    87 |
| Memoria RAM DDR4 8GB            |                   120 |
| Disco SSD 1 TB                  |                   151 |
| GeForce GTX 1050Ti              |                   185 |
| GeForce GTX 1080 Xtreme         |                   755 |
| Monitor 24 LED Full HD          |                   202 |
| Monitor 27 LED Full HD          |                   246 |
| Portátil Yoga 520               |                   559 |
| Portátil Ideapd 320             |                   444 |
| Impresora HP Deskjet 3720       |                    60 |
| Impresora HP Laserjet Pro M26nw |                   180 |
+---------------------------------+-----------------------+
```
### 5. Lista el código de los fabricantes que tienen productos en la tabla producto.
```
SELECT codigo_fabricante  AS "Codigo Fabricante" FROM producto;
+-------------------+
| Codigo Fabricante |
+-------------------+
|                 1 |
|                 1 |
|                 2 |
|                 2 |
|                 3 |
|                 3 |
|                 4 |
|                 5 |
|                 6 |
|                 6 |
|                 7 |
+-------------------+

```
### 6. Lista el código de los fabricantes que tienen productos en la tabla producto, sin mostrar los repetidos.
```
SELECT codigo_fabricante  AS "Codigo Fabricante" FROM producto GROUP BY codigo_fabricante;
+-------------------+
| Codigo Fabricante |
+-------------------+
|                 1 |
|                 2 |
|                 3 |
|                 4 |
|                 5 |
|                 6 |
|                 7 |
+-------------------+
```
### 7. Lista los nombres de los fabricantes ordenados de forma ascendente.
```
SELECT nombre AS "Nombre Fabricante" FROM fabricante ORDER BY nombre ASC;
+-------------------+
| Nombre Fabricante |
+-------------------+
| Asus              |
| Crucial           |
| Gigabyte          |
| Hewlett-Packard   |
| Huawei            |
| Lenovo            |
| Samsung           |
| Seagate           |
| Xiaomi            |
+-------------------+

```
### 8. Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma descendente.

```
SELECT nombre AS "Nombre de Producto" FROM producto ORDER BY nombre ASC;
+---------------------------------+
| Nombre de Producto              |
+---------------------------------+
| Disco duro SATA3 1TB            |
| Disco SSD 1 TB                  |
| GeForce GTX 1050Ti              |
| GeForce GTX 1080 Xtreme         |
| Impresora HP Deskjet 3720       |
| Impresora HP Laserjet Pro M26nw |
| Memoria RAM DDR4 8GB            |
| Monitor 24 LED Full HD          |
| Monitor 27 LED Full HD          |
| Portátil Ideapd 320             |
| Portátil Yoga 520               |
+---------------------------------+
SELECT nombre AS "Nombre de Producto" FROM producto ORDER BY precio DESC;
+---------------------------------+
| Nombre de Producto              |
+---------------------------------+
| GeForce GTX 1080 Xtreme         |
| Portátil Yoga 520               |
| Portátil Ideapd 320             |
| Monitor 27 LED Full HD          |
| Monitor 24 LED Full HD          |
| GeForce GTX 1050Ti              |
| Impresora HP Laserjet Pro M26nw |
| Disco SSD 1 TB                  |
| Memoria RAM DDR4 8GB            |
| Disco duro SATA3 1TB            |
| Impresora HP Deskjet 3720       |
+---------------------------------+
```
### 9. Devuelve una lista con las 5 primeras filas de la tabla fabricante.
```
SELECT * FROM fabricante LIMIT 5;
+--------+-----------------+
| codigo | nombre          |
+--------+-----------------+
|      1 | Asus            |
|      2 | Lenovo          |
|      3 | Hewlett-Packard |
|      4 | Samsung         |
|      5 | Seagate         |
+--------+-----------------+
```
### 10. Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)
```
SELECT nombre AS "Nombre del Producto", precio AS "Precio Unitario" FROM producto ORDER BY precio ASC LIMIT 1;
+---------------------------+-----------------+
| Nombre del Producto       | Precio Unitario |
+---------------------------+-----------------+
| Impresora HP Deskjet 3720 |           59.99 |
+---------------------------+-----------------+
```
### 11. Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)
```
SELECT nombre AS "Nombre del Producto", precio AS "Precio Unitario" FROM producto ORDER BY precio DESC LIMIT 1;
+-------------------------+-----------------+
| Nombre del Producto     | Precio Unitario |
+-------------------------+-----------------+
| GeForce GTX 1080 Xtreme |             755 |
+-------------------------+-----------------+
```
### 12. Lista el nombre de los productos que tienen un precio menor o igual a $120.
```
SELECT nombre AS "Nombre del Producto" FROM producto WHERE precio < 120;
+---------------------------+
| Nombre del Producto       |
+---------------------------+
| Disco duro SATA3 1TB      |
| Impresora HP Deskjet 3720 |
+---------------------------+
```
### 13. Lista todos los productos que tengan un precio entre $60 y $200. Utilizando el operador BETWEEN.
```
SELECT nombre AS "Nombre del Producto" FROM producto WHERE precio BETWEEN 60 and 200;
+---------------------------------+
| Nombre del Producto             |
+---------------------------------+
| Disco duro SATA3 1TB            |
| Memoria RAM DDR4 8GB            |
| Disco SSD 1 TB                  |
| GeForce GTX 1050Ti              |
| Impresora HP Laserjet Pro M26nw |
+---------------------------------+
```
### 14. Lista todos los productos donde el código de fabricante sea 1, 3 o 5. Utilizando el operador IN.
```
SELECT nombre AS "Nombre del Producto" FROM producto WHERE codigo_fabricante IN(1,3,5);
+---------------------------------+
| Nombre del Producto             |
+---------------------------------+
| Monitor 24 LED Full HD          |
| Monitor 27 LED Full HD          |
| Impresora HP Deskjet 3720       |
| Impresora HP Laserjet Pro M26nw |
| Disco duro SATA3 1TB            |
+---------------------------------+
```
### 15. Devuelve una lista con el nombre de todos los productos que contienen la cadena Portátil en el nombre.
```
SELECT nombre AS "Nombre del Producto" FROM producto WHERE nombre LIKE '%portátil%';
+----------------------+
| Nombre del Producto  |
+----------------------+
| Portátil Yoga 520    |
| Portátil Ideapd 320  |
+----------------------+
```
## Consultas Multitabla
### 1. Devuelve una lista con el código del producto, nombre del producto, código del fabricante y nombre del fabricante, de todos los productos de la base de datos.
```
SELECT producto.codigo AS "Codigo de Producto", producto.nombre AS "Nombre de Producto", producto.codigo_fabricante AS "Codigo
Frabricante", fabricante.nombre AS "Nombre del Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabrica
nte.codigo;
+--------------------+---------------------------------+--------------------+-----------------------+
| Codigo de Producto | Nombre de Producto              | Codigo Frabricante | Nombre del Fabricante |
+--------------------+---------------------------------+--------------------+-----------------------+
|                  1 | Disco duro SATA3 1TB            |                  5 | Seagate               |
|                  2 | Memoria RAM DDR4 8GB            |                  6 | Crucial               |
|                  3 | Disco SSD 1 TB                  |                  4 | Samsung               |
|                  4 | GeForce GTX 1050Ti              |                  7 | Gigabyte              |
|                  5 | GeForce GTX 1080 Xtreme         |                  6 | Crucial               |
|                  6 | Monitor 24 LED Full HD          |                  1 | Asus                  |
|                  7 | Monitor 27 LED Full HD          |                  1 | Asus                  |
|                  8 | Portátil Yoga 520               |                  2 | Lenovo                |
|                  9 | Portátil Ideapd 320             |                  2 | Lenovo                |
|                 10 | Impresora HP Deskjet 3720       |                  3 | Hewlett-Packard       |
|                 11 | Impresora HP Laserjet Pro M26nw |                  3 | Hewlett-Packard       |
+--------------------+---------------------------------+--------------------+-----------------------+
```
