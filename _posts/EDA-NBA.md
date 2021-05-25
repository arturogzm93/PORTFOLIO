---
layout: article
title: "Estudio de la evolución de la NBA"
categories: portfolio
excerpt: "Análisis exploratorio de datos sobre la evolución de la NBA"
image:
  teaser: NBA-logo.jpg
---

El objetivo de este proyecto es realizar un EDA (Análisis Exploratorio de Datos) sobre la NBA para analizar a través de los datos cómo ha sido la evolución de la competición desde 1980 hasta 2017 y cómo se han ido adaptando a dichos cambios los jugadores que ocupan las posiciones de base y pívot.

**¿Por qué se ha hecho el estudio desde 1980?**
Porque en esa temporada se introdujeron los triples de forma oficial en la competición.

**¿Cuáles fueron las hipótesis planteadas para llevar a cabo el estudio?**
- Ha evolucionado el juego hacia el juego exterior, produciéndose más triples durante los partidos.
- Han aumentado el número de robos y de pérdidas.
- Las posiciones de base y pívot han cambiado y evolucionado su estilo de juego.

El cambio del juego se ha visto afectado debido a que el número de tiros ha ido incrementando poco a poco con el paso de los años, notándose de forma significativa en los lanzamientos de triples y un ligero descenso de los tiros de 2 puntos. Además, el aumento total de tiros de campo ha hecho que el juego sea más rápido y que se produzcan más acciones durante los partidos, viendo esta evolución en el incremento, generalmente, del resto de estadísticas.

![image](/portfolio/images/tiros-totales.jpg)
![image](/portfolio/images/tiros-2-3.jpg)

Atendiendo a los tiros de campo por las 3 posiciones principales de los jugadores, se puede observar que los tiros de 2 puntos tanto de los bases como de los pívots se mantienen o crecen ligeramente, pero los aleros han reducido considerablemente este tipo de tiros. Mientras que los triples se han visto incrementados en todas las posiciones, sobre todo en los aleros, que han evolucionado su juego claramente hacia el juego exterior. También es destacable que los pívots, los jugadores más altos y menos habilidosos del equipo, han cambiado esa tendencia y han ampliado su rango de tiro, pasando de no lanzar casi ningún triple hasta lanzar casi los mismos que los bases, los jugadores más bajos y encargados de dirigir al equipo en la pista.

![image](/portfolio/images/tiros-posiciones.jpg)

La evolución del juego, que ha adoptado una tendencia más ofensiva y centrándose menos en la parcela defensiva, no ha tenido casi impacto en el número de robos y de pérdidas por partidos, cuyas estadísticas se mantienen más o menos similares, no se notan casi diferencias entre diferentes épocas. Esto difiere con mi hipótesis inicial, ya que pensaba que dichas estadísticas habrían aumentado al centrarse más en atacar y despreocupándose un poco más por la defensa.

![image](/portfolio/images/robos-perdidas.jpg)

Se ha hecho uso de las librerías de `numpy` y `pandas` para el tratamiento de los datos y las librerías de `matplotlib` y `seaborn` para realizar las diferentes gráficas. 

La base de datos se ha obtenido en la web de Kaggle, desde el siguiente [enlace](https://www.kaggle.com/drgilermo/nba-players-stats).

Todas las gráficas y el código del proyecto se pueden ver accediendo a este [repositorio](https://github.com/arturogzm93/EDA-NBA).
