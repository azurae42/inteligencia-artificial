# Agentes - Ejercicio 1.

## Diagrama de la cueva

```
4 | .  W  .  .
3 | .  P  G  .
2 | .  P  P  .
1 | >  .  .  .
     1  2  3  4
```

## Archivos adjuntos

En la carpeta `results/` se encuentran los resultados al ejecutar cada uno de los archivos de python con el argumento `--config config/mi_cueva_4x4.yml`:

- `01_wumpus_world.py`,
- `02_simple_reflex_agent.py`,
- `03_model_based_agent.py`,
- `04_goal_based_agent.py`,
- `05_utility_based_agent.py`.

La nomenclatura de cada archivo incluye el nombre del script de python respectivo, más el sufijo `_results.txt`.

También se incluye un archivo `results/summary.txt`, que compila los últimos estados de cada agente para una visualización rápida de los resultados finales.

En el caso del agente con aprendizaje, `06_learning_agent.py`, se inclyen los resultados para la ejecución con los siguientes números de episodios (`--episodes #`):

- 1500,
- 2000,
- 4000,
- 6000,
- 8000,
- 12000,
- 16000,
- 20000.

El número de episodios se ve reflejado en la nomenclatura como `06_learning_agent_results_(# episodios).txt`.

También se incluye el archivo `results/learning-summary.txt`, el cual exclusivamente compila los últimos estados de cada ejecución del agente con aprendizaje.

```
.
├── 01_wumpus_world.py
├── 02_simple_reflex_agent.py
├── 03_model_based_agent.py
├── 04_goal_based_agent.py
├── 05_utility_based_agent.py
├── 06_learning_agent.py
├── requirements.txt
├── Reporte.md
├── results/
│   ├── 01_wumpus_world_results.txt
│   ├── 02_simple_reflex_agent_results.txt
│   ├── [...]
│   ├── 06_learning_agent_results_1500.txt
│   ├── [...]
│   ├── learning-summary.txt
│   └── summary.txt
├── config/
│   ├── [...]
│   └── mi_cueva_4x4.yaml
├── agents/
│   └── [...]
└── wumpus/
    └── [...]
```

## Observaciones

### Agente de reflejo simple

En este nuevo entorno, el agente de reflejo simple solidificó su estatus como la bombilla menos brillante de entre sus 'hermanos'.

Únicamente dió un paso hacia la derecha hacia la celda `(2,1)`, donde permaneció en un bucle infinito, dando vuelta hacia la derecha en su lugar sin volver a avanzar hacia otra celda, esto debido a las simples instrucciones que dirigen su comportamiento.

En particular, el agente repite la linea: 'si percibe una (brisa), voltear a la derecha', sin posibilidad de realizar otra acción, pues no hay forma de que desaparezca el 'pit' adyacente en la casilla `(2,2)`.

### Los agentes que tuvieron éxito

Además del agente de reflejo simple, los siguientes dos agentes, (agente basado en modelo y el agente basado en meta), tampoco tuvieron éxito para salir de la cueva, es más, sucumbieron al mismo destino que su hermano menos sofisticado, un bucle eterno 