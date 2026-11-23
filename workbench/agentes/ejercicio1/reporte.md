# Agentes - Ejercicio 1.

## Diagrama de la cueva

```
# mi_cueva_4x4.yaml #

4 | .  W  .  .
3 | .  P  G  .
2 | .  P  P  .
1 | >  .  .  .
     1  2  3  4
```

## Observaciones

### Qué agentes tuvieron éxito y cuáles no

Además del agente de reflejo simple, los siguientes dos agentes, (agente basado en modelo y el agente basado en meta), tampoco tuvieron éxito para salir de la cueva, terminaron en un bucle muy similar al de los primeros agentes más simples.

Sorprendentemente, el agente basado en utilidad (4to agente)  fue el único de los agentes "sencillos" que pudo superar este mapa.

El agente de aprendizaje tuvo bastantes dificultades con este mapa, probé con diferentes cantidades de episodios, no fue hasta los 8000 episodios que el agente empezó a tener éxito en el mapa.

Al probar con episodios arriba de 8000, noté que la puntuación promedio de los últimos 50 episodios **descendió** al correr 12,000 y 16,000 episodios, y sólamente superó este puntaje al alcanzar los 20,000 episodios.

### Agente de reflejo simple

En este nuevo entorno, el agente de reflejo simple solidificó su estatus como la bombilla menos brillante de entre sus 'hermanos'.

Únicamente dió un paso hacia la derecha hacia la celda `(2,1)`, donde permaneció en un bucle infinito, dando vuelta hacia la derecha en su lugar sin volver a avanzar hacia otra celda, esto debido a las simples instrucciones que dirigen su comportamiento.

En particular, el agente repite la linea: 'si percibe una (brisa), voltear a la derecha', sin posibilidad de realizar otra acción, pues no hay forma de que desaparezca el 'pit' adyacente en la casilla `(2,2)`.

## Archivos adjuntos

En la carpeta `results/` se encuentran los resultados al ejecutar cada uno de los archivos de python con el argumento `--config config/mi_cueva_4x4.yml`. Se adjuntan tanto una captura del script corriendo en la terminal, como un archivo de texto con el resto del resultado de la ejecución para cada agente.

La nomenclatura de cada archivo incluye el nombre del script de python respectivo, más el sufijo `_results.txt`.

Los dos resumenes `summary.txt`, compilan los últimos estados de cada agente para una visualización rápida de los resultados finales. `learning-summary.txt`, compila los últimos estados de cada ejecución del agente con aprendizaje.

El agente con aprendizaje, `06_learning_agent.py`, se ejecutó con los siguientes números de episodios (`--episodes #`):

- 1500, 2000, 4000, 6000, 8000, 12000, 16000, 20000.

El número de episodios se ve reflejado en la nomenclatura como `06_learning_agent_results_(# episodios).txt`. 
