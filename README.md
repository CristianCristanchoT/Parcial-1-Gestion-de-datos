# Parcial 1 - Gestión  de datos



### 1. ¿Qué tipo de variables tiene el dataset? Detalle el tipo de variable de cada columna.

El dataset cuenta con un total de 8 columnas de las cuales 4 son de tipo object (string) y las otras 3 son de tipo float, los nombres y tipos de columnas se presentan a continuación.

| Columna | Tipo |
| ------ | ------ |
| gender | object |
| race/ethnicity | object |
| parental level of education | object |
| lunch | object |
| test preparation course | object |
| math score | float64 |
| reading score | float64 |
| reading score | float64 |


### 2. ¿Qué tipo de problemas de calidad de datos logra identificar? Defina e implemente las estrategias de limpieza de datos que correspondan.

El principal problema detectado fueron registros los cuales no tenían valor NaN,

| Columna | Cantidad de NaN |
| ------ | ------ |
| gender | 47 |
| race/ethnicity | 45 |
| parental level of education | 60 |
| lunch | 54 |
| test preparation course | 41 |
| math score | 51 |
| reading score | 48 |
| reading score | 49 |

Para lidiar con estos se procedió a remover las filas la cuales los contuvieran empleando el siguiente comando de pandas

```sh
estudiantes_df_clean = estudiantes_df.dropna()
```

### 3. ¿En qué asignatura en promedio los estudiantes obtuvieron un mejor puntaje? ¿Hay evidencia de algún sesgo en la distribución de dichos puntajes?

La asignatura en la cual los estudiantes obtuvieron mejores resultados en promedio fue en lectura con 69.25, seguido de escritura con 68.18 y finalmente matemáticas con 66.12, 

En el caso de las notas de matemáticas se puede ver una distribución normal sin ningún sesgo a continuación,
![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/mathscore.png?raw=true)

Pero en el caso de las notas de lectura se puede ver un leve sesgo hacia la izquierda lo que significa que los estudiantes obtuvieron en general peores notas en esta asignatura,
![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/readingscore.png?raw=true)


Finalmente, en el caso de escritura se ve un comportamiento similar que, en lectura, parece ser que de alguna manera las notas de escritura y lectura están correlacionadas,
![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/writingscore.png?raw=true)


### 4. ¿Existe alguna correlación entre los puntajes obtenidos en las tres asignaturas?

Al analizar los mapas de correlación entre las 3 materias presentado a continuación,

![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/correlation.png?raw=true)

Se puede evidenciar una fuerte correlación entre las notas de lectura y escritura, lo cual confirma la teoría propuesta en el punto anterior.

### 5. ¿Hay alguna diferencia observable en los puntajes de la asignatura de matemáticas entre géneros? ¿Qué género obtuvo en promedio los mejores puntajes?

Al analizar la siguiente grafica donde se muestran los boxplots de las notas entre los diferentes géneros presentada a continuación,

![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/Puntajedematematicasporgenero.png?raw=true)

Se evidencia que el genero masculino en promedio obtuvo mejores calificaciones en esta materia, además de que sus cuartiles Q2 y Q3 se encuentran por arriba de los otros géneros.

### 6. ¿Qué nivel de escolaridad tienen los padres de los estudiantes que obtuvieron un puntaje por encima del percentil 85 en la asignatura de escritura? ¿Cómo se distribuye la escolaridad entre esta población?.

Al analizar la distribución presentada a continuación de la escolaridad de los padres entre los mejores alumnos de la asignatura de escritura, se puede ver que en su mayoría los padres de estos presentan un grado de asociado, seguido de la categoría de algo de universidad.

![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/escolaridadpadresmejoresescritura.png?raw=true)



### 7. ¿Qué porcentaje de los estudiantes obtuvieron puntajes iguales o superiores a 90 en las tres asignaturas? De estos estudiantes¿que porcentaje estudió para los exámenes? 

En el caso de los mejores alumnos se encontró que el 65.7 de estos se prepararon para el examen, tal y como se muestra en la siguiente distribucion.

![alt text](https://github.com/CristianCristanchoT/Parcial-1-Gestion-de-datos/blob/master/images/preparacionmejoresestudiantes.png?raw=true)


