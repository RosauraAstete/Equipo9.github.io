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

## Código en Google Colab
El tratamiento de la señal ECG fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : <https://colab.research.google.com/drive/1sgEgrFBqwY6Eeo2MMIpReVEdn0zYfs1W?usp=sharing>


## 1. Leer el DataSet
La señal ECG a utilizar en este entregable es la señal de inhalación profunda obtenida en el entregable 4.

### Conversión a mV
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alNUC.png)
> Fig 2.  Señal ECG

Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV.

Para ello, se realizará una conversión de unidades con la formula de la Figura 3 [2].

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/formula.PNG)
> Fig 3. Formula de conversión

Una vez realizada esta conversión, se obtiene los valores de la señal ECG en mV.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alUC.png)
> Fig 4. Señal ECG en mV

## 2. Analisis en frecuencia
Se procede a realizar la FFT de la señal ECG.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/FFTse%C3%B1al.png)
> Fig 5. FFT de la señal ECG

Se puede apreciar en la Fig 5. que existe ruido de frecuncias de 60 y 180 Hz, por lo que se procede a realizar un filtrado con filtro digital Notch.

## 3. Filtro Notch

Se aprecia como el ruido de 60 y 180 Hz desaparece despues del filtrado. 

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/FFTfiltrada.png)
> Fig 6. FFT de la señal ECG filtrada

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alfiltrada.png)
> Fig 7. Señal ECG filtrada

## 4. Filtro pasa banda
Creación de filtro pasa banda

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/pasabanda.png)
> Fig 8. Filtro pasa banda

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alPB.png)
> Fig 9. Señal ECG filtrada con pasa banda

## 5. Filtro pasa alto
Creación de filtro pasa alto

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/pasaalto.png)
> Fig 10. Filtro pasa alto

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alPA.png)
> Fig 11. Señal ECG filtrada con pasa alto

## 6. Filtrado derivativo
## 7. Operador cuadrático
## 8. Operador Moving Winfow Integration
## 9. Marcar picos
## 10. Análisis Threshold
## 11. Complejos QRS

