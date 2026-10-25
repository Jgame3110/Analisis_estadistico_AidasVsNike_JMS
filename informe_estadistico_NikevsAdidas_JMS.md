# Análisis sobre la diferencia de precios entre Adidas y Nike en sus peores productos.

**Autor:** Joaquín Muñoz Salazar  
**Curso:** 1 GIC B  

---

## Índice
1. [Introducción](#introducción)
   - [Contexto](#contexto)
   - [Objetivo](#objetivo)
   - [Alcance](#alcance)
2. [Metodología](#metodología)
   - [Origen de los datos](#origen-de-los-datos)
   - [Herramientas](#herramientas)
3. [Diseño](#diseño)
4. [Resultados](#resultados)
   - [Muestras](#muestras)
   - [Medidas estadísticas](#medidas-estadísticas)
   - [Tablas de contingencia](#tablas-de-contingencia)
   - [Diagramas](#diagramas)
5. [Análisis de resultados](#análisis-de-resultados)
6. [Conclusiones](#conclusiones)
7. [Referencias](#referencias)

---

## Introducción

### Contexto
En el mundo del calzado dos de las grandes marcas son Adidas y Nike, competidoras entre sí en el mundo empresarial, siendo las dos grandes empresas multinacionales. Teniendo un gran catálogo de productos, destacando positiva o negativamente a la apelación de los clientes.

### Objetivo
El objetivo de la investigación que se ha llevado a cabo ha sido "realizar un análisis estadístico descriptivo de los precios en el calzado con peores puntuaciones por parte de los compradores, comprobando la diferencia de precio de estos productos entre las dos marcas".

### Alcance
Esta investigación se limita al calzado con *rating* (puntuación) entre 0 y 0.5 de Nike y Adidas, y se ha utilizado una muestra de 302 (precios).

---

## Metodología

### Origen de los datos
Se ha trabajado con un archivo "Adidas Vs Nike.csv" que incluye los precios de venta de cada zapatilla, así como información sobre la marca a la que corresponde y de su *rating* (puntuación) por parte de los clientes de esa zapatilla, siendo ("Adidas CORE / NEO", "Adidas ORIGINALS" y "Adidas SPORT PERFORMANCE") las marcas que corresponderá a Adidas, y Nike a sí misma.

Se han recopilado los datos para esta investigación mediante un recurso web (Kaggle) el cual fue publicado en 2020/04/13 siendo este una recopilación de datos de otro recurso llamado data world.

### Herramientas
Se han procesado los datos utilizando la aplicación RStudio para Windows, versión 2026.09.0+174.

---

## Diseño

*   **Variables estadísticas:**
    *   Se ha analizado la variable estadística `Sale.Price`, que representa "el precio con el que se ha vendido un producto en concreto de una marca", de tipo cuantitativo continuo, con valores positivos que pueden ser mayores o iguales a 0.
    *   También se ha utilizado la variable estadística `Brand`, de tipo cualitativo, con valores "Adidas CORE / NEO", "Adidas ORIGINALS" y "Adidas SPORT PERFORMANCE" que en su conjunto serían las que identificamos como Adidas, y "Nike".
*   **Población:** 3268 productos. Cada instancia de un precio de una zapatilla, se representará como un producto correspondiente a una de las marcas.
*   **Muestra:** 302 zapatillas, de las cuales 73 corresponden a la marca Adidas y 229 a la marca Nike.
*   **Organización de los datos:** Se han filtrado los datos de "Adidas Vs Nike.csv" para mostrar solo la información relevante a los productos con una puntuación (Rating) entre 0 y 0.5.

---

## Resultados

### Muestras

La muestra completa de 302 precios (`Sale.Price`), ordenados de menor a mayor, es la siguiente:

```text
[1] 9.99 12.99 15.95 16.79 19.79 19.95 19.99 19.99 20.97 21.49 21.49 22.99 23.99 23.99 24.99 24.99 24.99 24.99 24.99 24.99 24.99 26.49 26.49 27.59 27.99 27.99 28.79 29.95 29.99 29.99 29.99 31.97 34.97 34.97 34.97 34.97 34.97 34.97 34.97 34.97 34.97 34.99 35.99 35.99 37.99 39.59 39.97 39.97 39.97 39.99 39.99 39.99 41.97 41.99 41.99 44.79 44.95 44.95 44.95 44.95 44.95 44.95 44.95 44.99 45.59 45.59 45.59 45.59 45.59 45.59 45.59 45.99 46.19 47.97 47.97 47.97 47.99 47.99 47.99 47.99 49.95 49.95 49.95 49.95 49.95 49.99 49.99 52.47 52.47 52.47 52.47 52.47 52.47 52.47 52.47 52.47 52.47 53.97 53.99 54.95 54.95 54.95 54.95 54.95 54.95 54.95 54.95 54.95 54.95 54.95 54.95 55.97 55.99 55.99 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.95 59.99 59.99 59.99 59.99 59.99 59.99 59.99 59.99 62.97 62.97 62.97 62.97 62.97 64.95 64.95 64.95 64.95 64.95 65.97 65.99 67.97 67.97 69.95 69.95 69.95 71.97 71.97 71.99 71.99 71.99 74.95 74.95 74.95 74.95 74.95 74.95 75.99 75.99 76.97 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.95 79.99 79.99 79.99 83.97 83.97 84.95 84.95 84.95 84.95 89.95 89.95 89.95 89.95 89.95 89.95 89.95 89.97 89.97 89.99 90.97 95.97 95.97 97.97 97.97 99.95 99.95 99.95 99.95 99.95 99.95 99.95 99.95 99.95 99.95 99.95 99.95 101.97 104.95 104.95 104.97 109.95 109.95 109.95 109.95 109.95 109.95 109.95 109.95 109.99 109.99 111.97 111.97 111.97 111.97 111.97 111.97 111.97 111.97 111.97 118.97 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.95 119.97 119.97 129.95 129.95 129.95 129.95 129.95 129.95 135.97 135.97 139.95 139.95 139.95 139.95 139.99 149.95 149.95 149.95 149.95 149.95 149.95 149.95 159.95 159.95 159.95 159.95 159.95 159.95 159.95 159.95 159.95 159.95 159.95 159.97 169.95 169.95 169.95 179.95 179.99 189.95 189.95 219.95 219.95 219.95 229.95 229.95 229.95 229.95 239.99 249.95 249.95 365.00
```

La muestra de 73 precios de la marca **Adidas** es la siguiente:
```text
[1] 9.99 12.99 16.79 19.79 19.99 19.99 21.49 21.49 22.99 23.99 23.99 24.99 24.99 24.99 24.99 24.99 24.99 26.49 26.49 27.59 27.99 27.99 28.79 29.99 29.99 29.99 34.99 35.99 35.99 37.99 39.59 39.99 39.99 39.99 41.99 41.99 44.79 44.99 45.59 45.59 45.59 45.59 45.59 45.59 45.99 46.19 47.99 47.99 47.99 47.99 49.99 49.99 53.99 55.99 55.99 59.99 59.99 59.99 59.99 59.99 59.99 65.99 71.99 71.99 71.99 75.99 75.99 79.99 79.99 79.99 89.99 109.99 109.99 139.99 179.99 239.99
```

La muestra de 229 precios de la marca **Nike** es la siguiente:
*(Los 229 precios restantes correspondientes a esta marca, entre 15.95€ y 365.00€).*

### Medidas estadísticas
En la tabla 1 se muestran los resultados de las medidas estadísticas de centralización, dispersión, localización y forma más relevantes, para el total de precios de la muestra, y para los precios de Adidas y de Nike.

**Tabla 1. Medidas de estadísticas descriptivas**

| Medida | Todos | Adidas | Nike |
| :--- | :--- | :--- | :--- |
| **Tamaño muestra** | 302 precios | 73 precios | 229 precios |
| <ins>**Medidas de centralización**</ins> | | | |
| **Media** | 86.88€ | 51.26€ | 98.24€ |
| **Mediana** | 79.95€ | 45.59€ | 89.95€ |
| <ins>**Medidas de dispersión**</ins> | | | |
| **Mínimo** | 9.99€ | 9.99€ | 15.95€ |
| **Máximo** | 365.00€ | 239.99€ | 365.00€ |
| **Rango** | 355.01€ | 230.00€ | 349.05€ |
| **Varianza** | 2558.60€² | 1322.17€² | 2424.40€² |
| **Desviación estándar** | 50.58€ | 36.36€ | 49.24€ |
| **Coeficiente de variación** | 0.58 | 0.71 | 0.50 |
| <ins>**Medidas de localización**</ins> | | | |
| **Primer cuartil (Q1)** | 52.47€ | 27.59€ | 59.95€ |
| **Tercer cuartil (Q3)** | 111.97€ | 59.99€ | 119.95€ |
| **Rango intercuartílico (IQR)** | 59.50€ | 32.40€ | 60.00€ |
| <ins>**Medidas de forma**</ins> | | | |
| **Coeficiente de asimetría** | 1.40 | 2.73 | 1.44 |
| **Coeficiente de apuntamiento (curtosis)** | 3.26 | 9.95 | 3.71 |
| <ins>**Otras**</ins> | | | |
| **Valores inferiores a la media** | 178 (59%) | 48 (66%) | 125 (55%) |
| **Valores superiores a la media** | 124 (41%) | 25 (34%) | 104 (45%) |

### Tablas de contingencia
En la tabla 2 se muestra la tabla de contingencia para las variables precio y marca en el caso de agrupar los precios en 6 intervalos. En la tabla se representa con *f* las frecuencias absolutas y con *h* las frecuencias relativas.

**Tabla 2. Tablas de contingencia para precio y marca (con 6 intervalos)**

| PRECIO / MARCA | Adidas | Nike | f_precio | h_precio |
| :--- | :--- | :--- | :--- | :--- |
| **[0, 50)** | 48 | 26 | 74 | 0.25 |
| **[50, 100)** | 20 | 113 | 133 | 0.44 |
| **[100, 150)** | 4 | 60 | 64 | 0.21 |
| **[150, 200)** | 1 | 19 | 20 | 0.07 |
| **[200, 250)** | 0 | 10 | 10 | 0.03 |
| **[250, 365]** | 0 | 1 | 1 | 0.00 |
| **f_marca** | 73 | 229 | 302 | |
| **h_marca** | 0.24 | 0.76 | | 1.00 |

En la tabla 3 se muestra la tabla de contingencia para las variables precio y marca agrupando el precio en 3 intervalos, diferenciando la calificación de barato (precio entre 0 y 50 euros), de coste medio (entre 50 y 100 euros) y de caras (más de 100 euros).

**Tabla 3. Tabla de contingencia para precio y marca (con 3 intervalos)**

| PRECIO / MARCA | Adidas | Nike | f_precio | h_precio |
| :--- | :--- | :--- | :--- | :--- |
| **[0, 50) Baratas** | 48 | 26 | 74 | 0.25 |
| **[50, 100) Coste Medio** | 20 | 113 | 133 | 0.44 |
| **[100, 365] Caras** | 5 | 90 | 95 | 0.31 |
| **f_marca** | 73 | 229 | 302 | |
| **h_marca** | 0.24 | 0.76 | | 1.00 |

### Diagramas

*(Nota para GitHub: Sube tus imágenes a la carpeta de tu repositorio y enlaza la ruta aquí)*

![Diagrama 1: Porcentaje de zapatillas por marca](ruta/a/tu/imagen_diagrama1.png)  
**Diagrama 1.** Diagrama con el porcentaje de zapatillas por marca.

![Figura 2: Histogramas y Diagramas de Caja](ruta/a/tu/imagen_figura2.png)  
**Figura 2.** Histograma y diagramas de caja de los precios de todas las zapatillas y según su marca.

![Figura 3: Diagramas de distribución](ruta/a/tu/imagen_figura3.png)  
**Figura 3.** Diagramas circulares de distribución de precios.

---

## Análisis de resultados

Analizando la muestra podemos observar que la mayor parte de los datos forman parte de los productos de Nike, siendo estos un 76% (229 precios) del total (302 precios) de la muestra y Adidas un simple 24% (73 precios) tal como se observa en el Diagrama 1 y el apartado de muestras.

De los resultados obtenidos en la tabla 1 y de la observación de los histogramas y diagramas de caja (figura 2), se puede apreciar que la media (línea discontinua) y la mediana (línea continua) son superiores para Nike, donde la media son 98.24€ y la mediana 89.95€ comparado con Adidas, la media es 51.26€ y la mediana 45.59€, lo cual conlleva a ver en los histogramas un desplazamiento en las líneas Nike situada cercana al intervalo de 100€ y Adidas aproximada a 50€. En ambos casos la media es superior a la mediana, lo que indica que hay más precios inferiores a la media, lo cual confirma el coeficiente de asimetría, el cual es positivo en ambas marcas, por lo que en los dos coeficientes hay una asimetría hacia la derecha, como se aprecia en los histogramas de la figura 2. Así, Nike tiene más productos de valor inferior a la media (un 55%) y Adidas un 66%.

Se puede observar que el rango en el caso de Nike (349.05€) es mayor que el rango de Adidas (230.00€). La desviación estándar de ambos es significativamente distinta, acercándose más Nike (49.24€) al valor de rango del total (50.58€) que Adidas (36.36€), si miramos el coeficiente de variación podemos ver que tiene similitud con el rango, Nike (0.50) se acerca al valor total (0.58) y Adidas (0.71) está alejado de los coeficientes de variación de Nike y de todos. Lo que da a entender que los precios en Nike son más homogéneos que en Adidas, lo cual se puede respaldar, debido a que hay un mayor número de precios en Nike (229 precios) que en Adidas (73).

A partir del análisis de los resultados, se concluye que los precios de las zapatillas Nike son significativamente más elevados que los de Adidas. Nike presenta una media superior y concentra la gran mayoría de su catálogo en productos de coste medio y caro, mientras que Adidas tiene una fuerte tendencia hacia los precios baratos.

En cuanto a la variabilidad, los precios de Nike tienen una mayor dispersión absoluta en euros (mayor rango y mayor rango intercuartílico); sin embargo, en términos relativos, la distribución de Nike es más homogénea que la de Adidas (coeficiente de variación de 0.50 frente a 0.71). Esto se explica por la fuerte concentración de los precios de Adidas en sus valores más bajos (alta curtosis), lo que hace que cualquier variación en sus precios destaque más en proporción a su media baja. Finalmente, ambas marcas presentan asimetría hacia la derecha y valores atípicos en sus precios más altos, destacando el límite máximo de la muestra en un modelo de Nike con un valor de 365.00€.

El coeficiente de apuntamiento de Adidas es positivo (+9.95) y el de Nike también (+3.71), lo que indica que la distribución de frecuencias de ambos son "leptocúrticas", como confirman sus histogramas (figura 2). Sin embargo la distribución de Adidas tiene un apuntamiento mucho mayor. Esto indica que los precios de Adidas están fuertemente concentrados en un mismo intervalo (los valores más bajos), mientras que los precios de Nike, aunque también presentan apuntamiento, están un poco más repartidos entre los intervalos considerados en el histograma.

En relación a la clasificación de precios de Barato (precio entre 0€ y 50€), Coste medio (precio mayor o igual 50€ y 100€) y Caro (precio superior o igual a 100€), considerando la muestra completa por marca, como se muestra en la figura 3, la mayoría de los precios, se clasifican en coste medio 44%. En el caso de Adidas se clasifican en barato el 66% de los precios y en Nike 49% son de coste medio. Destacando en Nike un 39% de precios caros comparado con el escaso 7% de Adidas.

---

## Conclusiones

A partir de los análisis de los resultados obtenidos, puede concluirse que los precios de las zapatillas Nike son más elevados que los precios de Adidas, teniendo Nike una media mucho mayor a la de Adidas y con un gran porcentaje de zapatillas de coste medio y caras. Los datos son homogéneos en el caso de Nike pero no para Adidas, con una dispersión no muy acusada para Nike pero sí para Adidas y una gran tendencia a precios baratos, mientras que Nike aunque también tenga algo de tendencia está más repartidos entre las distintas clasificaciones de los precios. También hay algunos datos atípicos en ambas marcas destacando que Adidas presenta 4 datos atípicos y Nike 3, este teniendo el valor más alto de (365.00€).

---

## Referencias
*   Kaggle.com (2020). Archivo de datos csv. Obtenido de: [Adidas Vs Nike Dataset](https://www.kaggle.com/datasets/kaushiksuresh147/adidas-vs-nike?select=Adidas+Vs+Nike.CSV)
*   Mueller, J. (2020). How to Write a Statistical Report. Obtenido de: [wikiHow](https://www.wikihow.com/Write-a-Statistical-Report)