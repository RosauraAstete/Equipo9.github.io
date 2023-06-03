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
En el artículo nos dan la siguiente función que describe al operador:

y[n]=(1/8)(−x[n−2]−2x[n−1]+2x[n+1]+x[n+2])

Para que esta ecuación pueda ser utilizada necesitamos encuadrarla en un rango de  [0,+∞]  haciendo que  n=+2  entonces tenemos:

y[n]=(1/8)(−x[n]−2x[n+1]+2x[n+3]+x[n+4]) 

Por lo tanto:

b=[−1,−2,0,2,1]

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/deri.png)
> Fig 12. Filtro derivativo

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alDERI.png)
> Fig 13. Señal ECG filtrada con filtro derivativo

## 7. Operador cuadrático
Este operador solo tiene como función elevar al cuadrado los valores de la señal.

y[n]=x^2[n]

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alCUAD.png)
> Fig 14. Señal ECG filtrada con filtro cuadrático

## 8. Operador Moving Window Integration
Este operador tiene como función extraer ciertas características de la onda.

y[n]=(1/N)(x[n−(N−1)]+x[n−(N−2)]+..+x[n])

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/se%C3%B1alWIND.png)
> Fig 15. Señal ECG filtrada con Moving Window Integration

## 9. Marcar picos
Colocando marcadores de picos

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/PICOS.png)
> Fig 16. Señal ECG con picos marcados

## 10. Análisis Threshold
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/THRESHOLD.png)
> Fig 17. Señal ECG con análisis Threshold

## 11. Complejos QRS
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/QRS.png)
> Fig 18. Señal ECG y complejos QRS

## ¿Qué se puede determinar con el análisis de señales EMG?
Al analizar la amplitud, tendencia central y variabilidad de la señal EMG, se pueden determinar varias patologías y condiciones relacionadas con el sistema neuromuscular. Asimismo, la razón principal del interés en el análisis de señales EMG se encuentra en el diagnóstico clínico y las aplicaciones biomédicas [d]:

Algunas patologías son las siguientes:

1. Miopatías: Engloban una variedad de trastornos que afectan principalmente la anatomía, el metabolismo o el funcionamiento de los músculos esqueléticos. Estas afecciones suelen manifestarse a través de debilidad muscular que puede interferir con las actividades cotidianas. Al analizar la amplitud de la señal EMG, se puede observar una reducción en la amplitud de la actividad eléctrica en pacientes con miopatías, lo que indica debilidad muscular [e]. 

2. Neuropatías periféricas:Se refiere a una variedad de condiciones en las cuales se produce daño en el sistema nervioso periférico, el cual constituye una amplia red de comunicación encargada de enviar señales entre el sistema nervioso central (el cerebro y la médula espinal) y todas las otras partes del cuerpo. Al analizar la amplitud de la señal EMG, se puede observar una disminución en la amplitud o incluso la ausencia de actividad eléctrica en los músculos afectados [f]. 

3. Esclerosis lateral amiotrófica (ELA): Se trata de una enfermedad neurológica poco común que impacta a las neuronas motoras, es decir, a las células nerviosas ubicadas en el cerebro y la médula espinal encargadas de controlar el movimiento muscular voluntario. En la ELA, el análisis de la amplitud de la señal EMG puede mostrar una disminución en la amplitud de la actividad eléctrica debido a la degeneración de las células nerviosas [g].

4. Síndrome del túnel carpiano: Se trata de una afección neurológica frecuente que se produce cuando el nervio mediano, que se extiende desde el antebrazo hasta la palma de la mano, experimenta compresión o presión en la muñeca. Los síntomas pueden incluir entumecimiento, debilidad, dolor en la mano y la muñeca, así como hinchazón y dificultad para usar los dedos. Al analizar la amplitud de la señal EMG en los músculos afectados, se puede observar una disminución en la amplitud de la actividad eléctrica y posiblemente una menor variabilidad debido a la interferencia en la conducción nerviosa [h]. 


# Referencias
[1] J. PAN, W. J. TOMPKINS, "A Real-Time QRS Detection Algorithm", IEEE Transactions on Biomedical Engineering, vol. 22, pp- 230-236, March 1985.

[2] PLUX-Wireless Biosignals, S.A., "Electrocardiography (ECG) - Sensor Data Sheet", PLUX-Wireless Biosignals, Lisbon, Portugal, ECG 011020, 2020.
