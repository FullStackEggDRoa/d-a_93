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
### 2. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.
```
SELECT producto.nombre AS "Nombre del Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre del Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo ORDER BY fabricante.nombre ASC;
+---------------------------------+-----------------+-----------------------+
| Nombre del Producto             | Precio Unitario | Nombre del Fabricante |
+---------------------------------+-----------------+-----------------------+
| Monitor 24 LED Full HD          |             202 | Asus                  |
| Monitor 27 LED Full HD          |          245.99 | Asus                  |
| Memoria RAM DDR4 8GB            |             120 | Crucial               |
| GeForce GTX 1080 Xtreme         |             755 | Crucial               |
| GeForce GTX 1050Ti              |             185 | Gigabyte              |
| Impresora HP Deskjet 3720       |           59.99 | Hewlett-Packard       |
| Impresora HP Laserjet Pro M26nw |             180 | Hewlett-Packard       |
| Portátil Yoga 520               |             559 | Lenovo                |
| Portátil Ideapd 320             |             444 | Lenovo                |
| Disco SSD 1 TB                  |          150.99 | Samsung               |
| Disco duro SATA3 1TB            |           86.99 | Seagate               |
+---------------------------------+-----------------+-----------------------+
```
### 3. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más barato.
```
SELECT producto.nombre AS "Nombre de Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo ORDER BY precio ASC LIMIT 1;
+---------------------------+--------------------+----------------------+
| Nombre de Producto        |   Precio Unitario  | Nombre de Fabricante |
+---------------------------+--------------------+----------------------+
| Impresora HP Deskjet 3720 |              59.99 | Hewlett-Packard      |
+---------------------------+--------------------+----------------------+
```
### 4. Devuelve una lista de todos los productos del fabricante Lenovo.
```
SELECT producto.nombre AS "Nombre de Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE fabricante.nombre LIKE '%lenovo%';
+----------------------+-----------------+----------------------+
| Nombre de Producto   | Precio Unitario | Nombre de Fabricante |
+----------------------+-----------------+----------------------+
| Portátil Yoga 520    |             559 | Lenovo               |
| Portátil Ideapd 320  |             444 | Lenovo               |
+----------------------+-----------------+----------------------+
```
### 5. Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que $200.
```
SELECT producto.nombre AS "Nombre de Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE fabricante.nombre LIKE '%crucial%' AND precio >
200;
+-------------------------+-----------------+----------------------+
| Nombre de Producto      | Precio Unitario | Nombre de Fabricante |
+-------------------------+-----------------+----------------------+
| GeForce GTX 1080 Xtreme |             755 | Crucial              |
+-------------------------+-----------------+----------------------+
```
### 6. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packard. Utilizando el operador IN.
```
SELECT producto.nombre AS "Nombre de Producto", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE fabricante.nombre IN ("Asus","Hewlett-Packard");
+---------------------------------+----------------------+
| Nombre de Producto              | Nombre de Fabricante |
+---------------------------------+----------------------+
| Monitor 24 LED Full HD          | Asus                 |
| Monitor 27 LED Full HD          | Asus                 |
| Impresora HP Deskjet 3720       | Hewlett-Packard      |
| Impresora HP Laserjet Pro M26nw | Hewlett-Packard      |
+---------------------------------+----------------------+
```
### 7. Devuelve un listado con el nombre de producto, precio y nombre de fabricante, de todos los productos que tengan un precio mayor o igual a $180. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente)
```
SELECT producto.nombre AS "Nombre de Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE precio >= 180 ORDER BY precio DESC;
+---------------------------------+-----------------+----------------------+
| Nombre de Producto              | Precio Unitario | Nombre de Fabricante |
+---------------------------------+-----------------+----------------------+
| GeForce GTX 1080 Xtreme         |             755 | Crucial              |
| Portátil Yoga 520               |             559 | Lenovo               |
| Portátil Ideapd 320             |             444 | Lenovo               |
| Monitor 27 LED Full HD          |          245.99 | Asus                 |
| Monitor 24 LED Full HD          |             202 | Asus                 |
| GeForce GTX 1050Ti              |             185 | Gigabyte             |
| Impresora HP Laserjet Pro M26nw |             180 | Hewlett-Packard      |
+---------------------------------+-----------------+----------------------+
SELECT producto.nombre AS "Nombre de Producto", precio AS "Precio Unitario", fabricante.nombre AS "Nombre de Fabricante" FROM producto INNER JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE precio >= 180 ORDER BY producto.nombre ASC;
+---------------------------------+-----------------+----------------------+
| Nombre de Producto              | Precio Unitario | Nombre de Fabricante |
+---------------------------------+-----------------+----------------------+
| GeForce GTX 1050Ti              |             185 | Gigabyte             |
| GeForce GTX 1080 Xtreme         |             755 | Crucial              |
| Impresora HP Laserjet Pro M26nw |             180 | Hewlett-Packard      |
| Monitor 24 LED Full HD          |             202 | Asus                 |
| Monitor 27 LED Full HD          |          245.99 | Asus                 |
| Portátil Ideapd 320             |             444 | Lenovo               |
| Portátil Yoga 520               |             559 | Lenovo               |
+---------------------------------+-----------------+----------------------+
```
## Consultas Multitabla
Resuelva todas las consultas utilizando las cláusulas LEFT JOIN y RIGHT JOIN.
### 1. Devuelve un listado de todos los fabricantes que existen en la base de datos, junto con los productos que tiene cada uno de ellos. El listado deberá mostrar también aquellos fabricantes que no tienen productos asociados.
```
SELECT fabricante.nombre AS "Nombre de Fabricante", producto.nombre AS "Nombre de Producto" FROM producto RIGHT JOIN fabricante
 ON producto.codigo_fabricante = fabricante.codigo;
+----------------------+---------------------------------+
| Nombre de Fabricante | Nombre de Producto              |
+----------------------+---------------------------------+
| Asus                 | Monitor 24 LED Full HD          |
| Asus                 | Monitor 27 LED Full HD          |
| Lenovo               | Portátil Yoga 520               |
| Lenovo               | Portátil Ideapd 320             |
| Hewlett-Packard      | Impresora HP Deskjet 3720       |
| Hewlett-Packard      | Impresora HP Laserjet Pro M26nw |
| Samsung              | Disco SSD 1 TB                  |
| Seagate              | Disco duro SATA3 1TB            |
| Crucial              | Memoria RAM DDR4 8GB            |
| Crucial              | GeForce GTX 1080 Xtreme         |
| Gigabyte             | GeForce GTX 1050Ti              |
| Huawei               | NULL                            |
| Xiaomi               | NULL                            |
+----------------------+---------------------------------+
```
### 2. Devuelve un listado donde sólo aparezcan aquellos fabricantes que no tienen ningún producto asociado.
```
SELECT fabricante.nombre AS "Nombre de Fabricante", producto.nombre AS "Nombre de Producto" FROM producto RIGHT JOIN fabricante ON producto.codigo_fabricante = fabricante.codigo WHERE producto.nombre IS NULL;
+----------------------+--------------------+
| Nombre de Fabricante | Nombre de Producto |
+----------------------+--------------------+
| Huawei               | NULL               |
| Xiaomi               | NULL               |
+----------------------+--------------------+
```
## Subconsultas (En la cláusula WHERE)
## Con operadores básicos de comparación
### 1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER JOIN).
```
SELECT nombre AS "Nombre Producto" FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre = "Lenovo");
+----------------------+
| Nombre Producto      |
+----------------------+
| Portátil Yoga 520    |
| Portátil Ideapd 320  |
+----------------------+
```
### 2. Devuelve todos los datos de los productos que tienen el mismo precio que el producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).
```
SELECT * FROM producto WHERE precio = (SELECT MAX(precio) FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre = "Lenovo"));
+--------+--------------------+--------+-------------------+
| codigo | nombre             | precio | codigo_fabricante |
+--------+--------------------+--------+-------------------+
|      8 | Portátil Yoga 520  |    559 |                 2 |
+--------+--------------------+--------+-------------------+
```
### 3. Lista el nombre del producto más caro del fabricante Lenovo.
```
SELECT nombre AS "Nombre de Producto" FROM producto WHERE precio = (SELECT MAX(precio) FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre = "Lenovo"));
+--------------------+
| Nombre de Producto |
+--------------------+
| Portátil Yoga 520  |
+--------------------+
```
### 4. Lista todos los productos del fabricante Asus que tienen un precio superior al precio medio de todos sus productos.
```
SELECT nombre AS "Nombre de Producto" FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre="Asus") AND precio > (SELECT AVG(precio) FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre="Asus"));
+------------------------+
| Nombre de Producto     |
+------------------------+
| Monitor 27 LED Full HD |
+------------------------+
```
## Subconsultas con IN y NOT IN
### 1. Devuelve los nombres de los fabricantes que tienen productos asociados. (Utilizando IN o NOT IN).
```
SELECT nombre AS "Nombre Fabricante" FROM fabricante WHERE codigo IN(SELECT codigo_fabricante FROM producto GROUP BY codigo_fabricante);
+-------------------+
| Nombre Fabricante |
+-------------------+
| Asus              |
| Lenovo            |
| Hewlett-Packard   |
| Samsung           |
| Seagate           |
| Crucial           |
| Gigabyte          |
+-------------------+
```
### 2. Devuelve los nombres de los fabricantes que no tienen productos asociados. (Utilizando IN o NOT IN).
```
SELECT nombre AS "Nombre Fabricante" FROM fabricante WHERE codigo NOT IN(SELECT codigo_fabricante FROM producto GROUP BY codigo_fabricante);
+-------------------+
| Nombre Fabricante |
+-------------------+
| Huawei            |
| Xiaomi            |
+-------------------+
```
## Subconsultas (En la cláusula HAVING)
### 1. Devuelve un listado con todos los nombres de los fabricantes que tienen el mismo número de productos que el fabricante Lenovo.
```
SELECT nombre AS "Nombre Fabricante" FROM fabricante GROUP BY codigo HAVING codigo > (SELECT COUNT(codigo) FROM producto WHERE codigo_fabricante = (SELECT codigo FROM fabricante WHERE nombre = "Lenovo"));
+-------------------+
| Nombre Fabricante |
+-------------------+
| Hewlett-Packard   |
| Samsung           |
| Seagate           |
| Crucial           |
| Gigabyte          |
| Huawei            |
| Xiaomi            |
+-------------------+

```
