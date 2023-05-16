# Tratamiento de señales

En el siguente entregable, se presentará una señal ECG tratada. El tratamiento realizado está basado en la investigación *A Real-Time QRS Detection Algorithm* publicado por la organización IEEE [1].

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/paper.PNG)
>Fig 1. Investigación *A Real-Time QRS Detection Algorithm*

El tratamiento consiste de los siguientes pasos:
1.  Leer el DataSet
2.  Analizar el ECG en frecuencia
3. Reducir los ruidos con filtro Notch
4. Filtrar la señal con un filtro pasa banda
5. Filtrar la señal con un filtro pasa alto
6. Realizar el filtrado derivativo
7. Elevar al cuadrado la señal
8. Emplear el operador Moving Window Integration
9. Marcar los picos
10. Realizar el análisis de Threshold: hallar el umbral del pico R y ruidos
11. Obtener los complejos QRS en la señal ECG inicial

## Conversión a mV
La señal ECG a utilizar en este entregable es la señal de inhalación profunda obtenida en el entregable 4.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alNUC.png)
> Fig 2.  Señal ECG

Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV.

Para ello, se realizará una conversión de unidades con la formula de la Figura 3 [2].

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/formula.PNG)
> Fig 3. Formula de conversión

Una vez realizada esta conversión, se obtiene los valores de la señal ECG en mV.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alUC.png)
> Fig 3. Señal ECG en mV
