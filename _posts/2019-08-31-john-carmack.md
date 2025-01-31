---
layout: micro_post
ublished: true
title: John Carmack
---

No es noticia que Carmack es uno de mis programadores favoritos. Gracias a él aprendí muchísimo
leyendo el código de Quake (especialmente el 2), escuchando sus maravillosas [master class](https://www.youtube.com/watch?v=IyUgHPs86XM) en las
quakecon y leyendo maravillas como [esta](https://www.reddit.com/r/MachineLearning/comments/82mqtw/d_john_carmacks_1week_experience_learning_neural/), cuando se fue una semana aislado a aprender machine learning. La forma en la que "locuta" me hipnotiza.

Hace pocos días le han hecho [una entrevista](https://www.youtube.com/watch?v=udlMSe5-zP8) en un podcast bastante conocido (que no conocía). La entrevista es tan larga como interesante (puedes encontrar resúmenes por ahí), así que da para hablar de bastantes temas: VR, redes sociales y sus problemas, el tema sobre cuantas horas hay que trabajar, coches, videojuegos... en todos ellos su visión es muy muy sensata aunque creo que el hecho de trabajar en Oculus (comprada por facebook) le hace tener una posición un poco sesgada sobre lo que la cúpula de facebook piensa. 

Dejando a un lado esa posición sesgada y que está maravillado con su Tesla... hay dos temas que me
han llamado la atención poderosamente:

El primero es cuando habla sobre la cantidad de horas que trabaja. Comenta que él solo puede ser
productivo 13 horas al día... últimamente ha habido una gran cantidad de comentarios sobre este tema
dando recomendaciones sobre cuanto trabajar. En mi vida ha habido periodos donde he trabajado 10-12
horas al día y no los cambiaría por nada. No es sostenible ni para todo el mundo, obviamente, y cada periodo de la vida tiene diferentes prioridades, pero en mi opinión es complicado ser muy bueno en algo si no inviertes una buena cantidad de horas. De ahí que esté un poco de acuerdo con Carmack aquí sobre que cada uno elija libremente las horas que puede o no trabajar (sabiendo, eso sí, que hay vida necesaria más allá que el editor de código)

El segundo, y más importante, es cuando [habla de la velocidad de computación](https://youtu.be/udlMSe5-zP8?t=3830)

Las máquinas están empezando a ser más lentas, no en absoluto, pero la velocidad a la que la
velocidad crece ha bajado dramáticamente. Y el punto está en que, según carmack, los móviles están
llegando al límite de lo que pueden dar.

Como derivada, y esta es la parte más llamativa, habla de un cambio cultural, tenemos que empezar a
volver a pensar en el performance. Y no es el único, cada semana veo varios artículos sobre como la
web está a rebosar de código que hace que vaya lento en todo lo que no sean móviles de última
generación. La gente ya no sabe que pasa debajo del código que hace (React, te estoy mirando a ti) y
en general se tiende a pensar que con levantar unas cuantas máquinas más en AWS resuelve todos los
problemas. [Aquí una charla](https://www.youtube.com/watch?v=pW-SOdj4Kkk) de otro de mis favoritos, hablando precisamente de como el hecho de que los
desarrolladores actuales no tengamos ni puñetera idea de lo que pasa por debajo es algo muy muy malo
en un futuro próximo (un poco apocalítico, pero bueno)

No puedo estar más agradecido de haber empezado mi carrera profesional haciendo videojuegos, donde
tener que refrescar millones de pixeles 60 veces por segundo hacía que el "performance" fuese un
ciudadano de primera.

Hablaré más sobre este tema en [futuros post](http://javisantana.com/micro/)


### Qué he estado escribiendo esta semana

Este mes de agosto he escrito bastante pero he publicado muy poco, cosas de las vacaciones y que por
otro lado dejo madurar los posts unos días para ver si pasan el test de la lectura después de una
semana.He avanzado con mi serie de post
sobre el data lake, en esta entrega [la trazabilidad](http://javisantana.com/micro/2019-08-28-data-lake-VI-trazabilidad.html)

Estoy escribiendo esta serie con dos objetivos: 
1) Que alguien que se pregunte qué leches es un "data lake" lo sepa
2) Demostrar que un daka lake es una panacea y que no deberías hacer algo así.

### En qué estoy trabajando

Casi todas las bases de datos tienen sistemas para planificar como van a ejecutar una query en base
a unas estadísticas sobre los datos. Suelen ser sistemas complejísimos y a veces tienes que saber
como funcionan para optimizar bien las queries.

Clickhouse, mi base de datos favorita, no tiene un planificador (tiene algo muy simple, que dicho sea de paso simplifica todo el diseño), no obstante las queries se pueden ejecutar con diferentes
parámetros. Estoy usando una aproximación diferente: en vez de calcular estadísticas de los datos y
ver cual es el mejor plan, estoy ejecutando los diferentes tipos de queries con diferentes parámetros y entrenando un modelo de ML para luego saber cual es el mejor plan dados unos parámetros. De momento el modelo predice con exactitud el tiempo de ejecución (lo que me ha sorprendido gratamente).

El objetivo es integrarlo en [Tinybird](https://tinybird.co/) para los endpoints que tengas publicados. Publicaré los resultados en el [blog de Tinybird](https://blog.tinybird.co/)

Hay aproximaciónes para usar ML en bases de datos, [aquí un articulo brutal](https://ai.google/research/pubs/pub46518) de como usar un modelo para
sustituir a los índices tradicionales.

### Extra lap

Si vas a leer algún link de esta lista, que sea este post de Feli, "[tengo cáncer](https://medium.com/@felipecasajus/tengo-cancer-bceee81e75a)"
