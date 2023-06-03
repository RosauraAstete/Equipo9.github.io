# Tratamiento de señales EEG 
El procesamiento de señales es el proceso por el cual se extrae información de una señal que nos permita caracterizarla, para diferenciarla de otras señales, y sacar conclusiones. 
Para ello, se debe realizar un filtrado de la señal EEG, eliminación de artefactos, y normalización de la señal EEG. El filtrado se puede realizar mediante filtros pasa alto, bajo, filtro de banda, y adaptativos. Los artefactos se generan debido a actividad muscular, de movimiento ocular, o por actividad cardiaca. Para eliminarlas además del filtrado se puede usar un promediado o ICA. 
La normalización es un proceso que facilita la comparación y el análisis de la señal. Como cada individuo es diferente se realiza una normalización con Z-score o desviación estándar. 
Espectro de potencia, el dominio de la frecuencia, me brinda una distribución de la energía en diferentes frecuencias espectrales dentro del EEG, lo que permite identificar las frecuencias dominantes. 


En el siguente entregable, se presentará una señal EEG.
El tratamiento consiste de los siguientes pasos:
1. Leer y mostrar los Datos
2. Cargar los datos
3. Filtrar la señal 
4. Detección ERP
5. Extracción de la banda alfa

## Código en Google Colab
El tratamiento de la señal EEG fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : https://colab.research.google.com/drive/1HfNEeCAA7RXt4aH2zUnifKPWNI8O5apw?usp=sharing


## 1. Leer el DataSet
La señal EEG a utilizar en este entregable es la señal de inhalación profunda obtenida en el entregable 5.

### Conversión a mV
![]()
> Fig 2.  Señal EEG

Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV.

Para ello, se realizará una conversión de unidades con la formula de la Figura 3 [2].

![]()
> Fig 3. Formula de conversión

Una vez realizada esta conversión, se obtiene los valores de la señal EEG en mV.

![](g)
> Fig 4. Señal EEG en mV

## 2. Señal Filtrada
Se procede a filtrar la señal EEG.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/FFTse%C3%B1al.png)
> Fig 5. Señal EEG filtrada

## 5. Detección de ERP
Se puede extraer las características temporales espectrales como la amplitud, la fase. ERP análisis de eventos relacionados con respuesta a estímulos.

Ploteo de la señal de audio

![]()
> Fig 6. Audio plot

Ploteo de la señal medida como respuesta al estímulo, en este caso el audio previamente mostrado
![]()
> Fig 7. Señal EEG obtenida como respuesta al estímulo

![]()
> Fig 8. Correlación cruzada entre ambas señales

## 6. Extracción de la banda Alfa

![]()
> Fig 9. Señal ECG y complejos QRS

# Referencias
[1] J. PAN, W. J. TOMPKINS, "A Real-Time QRS Detection Algorithm", IEEE Transactions on Biomedical Engineering, vol. 22, pp- 230-236, March 1985.

[2] PLUX-Wireless Biosignals, S.A., "Electrocardiography (ECG) - Sensor Data Sheet", PLUX-Wireless Biosignals, Lisbon, Portugal, ECG 011020, 2020.
