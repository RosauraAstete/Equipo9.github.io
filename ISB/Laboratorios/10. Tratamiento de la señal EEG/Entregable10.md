# Tratamiento de señales EEG 

En el siguente entregable, se presentará una señal EEG.
El tratamiento consiste de los siguientes pasos:
1. Leer y mostrar los Datos
2. Cargar los datos
3. Filtrar la señal con un filtro Notch
4. Detección de eventos
5. Extracción de Características

## Código en Google Colab
El tratamiento de la señal ECG fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : https://colab.research.google.com/drive/1HfNEeCAA7RXt4aH2zUnifKPWNI8O5apw?usp=sharing


## 1. Leer el DataSet
La señal ECG a utilizar en este entregable es la señal de inhalación profunda obtenida en el entregable 4.

### Conversión a mV
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/se%C3%B1al%20basal%20EEG.png)
> Fig 2.  Señal EEG

Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV.

Para ello, se realizará una conversión de unidades con la formula de la Figura 3 [2].

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/formula.png)
(https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/formula%202.png)
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

## 5. Detección de ERP
Ploteo de la señal de audio

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/5d650d4398893f49aa9dffffdabcca82e9757edf/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/Audio%20Signal.png)
> Fig 10. Audio plot

Ploteo de la señal medida como respuesta al estímulo, en este caso el audio previamente mostrado
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/5d650d4398893f49aa9dffffdabcca82e9757edf/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/Se%C3%B1alestimulo.png)
> Fig 11. Señal EEG obtenida como rspuesta al estímulo

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/5d650d4398893f49aa9dffffdabcca82e9757edf/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/correlcruzada.png)
> Fig 12. Correlación cruzada entre ambas señales

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

# Referencias
[1] J. PAN, W. J. TOMPKINS, "A Real-Time QRS Detection Algorithm", IEEE Transactions on Biomedical Engineering, vol. 22, pp- 230-236, March 1985.

[2] PLUX-Wireless Biosignals, S.A., "Electrocardiography (ECG) - Sensor Data Sheet", PLUX-Wireless Biosignals, Lisbon, Portugal, ECG 011020, 2020.
