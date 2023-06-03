# Tratamiento de señales EMG

En el siguente entregable, se presentará una señal EMG tratada. El tratamiento realizado permitirá mejorar la calidad de la señal y obtener datos cuantitativos y cualitativos sobre la actividad eléctrica de los músculos.

El tratamiento consiste de los siguientes pasos:
1. Leer y mostrar los Datos
2. Cargar los datos
3. Filtrar la señal con un filtro Notch
4. Filtrar la señal con un filtro pasa banda
5. Detección de eventos
6. Extracción de Características

## Código en Google Colab
El tratamiento de la señal EMG fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : https://colab.research.google.com/drive/1c3p3u3bgV1so3WMKKvJRaMzL6VFXSStj?usp=sharing 


## 1. Leer y Mostrar los datos
La señal EMG a utilizar en este entregable es la captada en el entregable número 3.

Archivo txt: [Señal EMG](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/9.%20Tratamiento%20de%20la%20se%C3%B1al%20EMG/Archivos/Se%C3%B1alEMG.txt)

### Conversión a mV

![](https://hackmd.io/_uploads/ryM0iWuLn.jpg)
> Fig 2.  Señal EMG

Esta señal no se encuentra en unidades de voltaje, por lo que habrá que realizar una conversión de unidades para poseer la señal en mV.

Para ello, se realizará una conversión de unidades con la formula de la Figura 3 [1].

![](https://hackmd.io/_uploads/HkTicWuL2.png)
> Fig 3. Formula de conversión

Una vez realizada esta conversión, se obtiene los valores de la señal EMG en mV.

![](https://hackmd.io/_uploads/ryIQT-u82.jpg)
> Fig 4. Señal EMG en mV

## 2. Analisis en frecuencia
Se procede a realizar la FFT de la señal EMG.

![](https://hackmd.io/_uploads/rkgREMu8n.jpg)

> Fig 5. FFT de la señal EMG

Se puede apreciar en la Fig 5. que existe ruido de frecuencias de 60, 180, 300 y 419 Hz, por lo que se procede a realizar un filtrado con filtro digital Notch.

## 3. Filtro Notch

Se aprecia como el ruido de de 60, 180, 300 y 419 Hz desaparece despues del filtrado. 

![](https://hackmd.io/_uploads/SkG2VMO83.jpg)
> Fig 6. FFT de la señal EMG filtrada

![](https://hackmd.io/_uploads/rJMMHfu8n.jpg)
> Fig 7. Señal EMG filtrada

## 4. Filtro pasa banda
La mayor  concentración de energía en las señales EMG es entre los 50 Hz y 150 Hz, aunque su canal de información va de los 20 Hz a los 500 Hz [2]. Por lo tanto, se decidió hacer un filtro pasabanda con frecuencias de corte en 20 y 400 Hz. 

![](https://hackmd.io/_uploads/BJow8MdLh.jpg)
> Fig 8. FFT de la señal EMG filtrada

![](https://hackmd.io/_uploads/HJeLUzuIn.jpg)
> Fig 9. Señal ECG filtrada con pasa banda

## 5. Detección de Eventos
Se utilizó el método de umbral simple para distinguir las activaciones musculares del ruido de fondo. Podemos notar que cuando hay actividad muscular, es decir, una contracción fuerte, la onda cuadrada pasa de baja a alta.

![](https://hackmd.io/_uploads/HytdjfuI3.jpg)
> Fig 10. Detección de activación muscular

## 6. Extracción de Características

### Máximo, Mínimo, Promedio y Desviación Estándar
![](https://hackmd.io/_uploads/r1Nj3Gd83.jpg)
> Fig 11. Máximo, Mínimo, Promedio y Desviación Estándar de la señal EMG

### Root Mean Square

El valor de RMS = 0.1637931652259006


### Área bajo la curva

Area bajo la curva = [ 0.06718251,  0.13086815,  0.05141693, ..., -0.046185,  -0.01205472,  0.04502639 ]

### Potencia Espectral de la Señal

![](https://hackmd.io/_uploads/S1a0f7uI3.jpg)
> Fig 12. Potencia Espectral de la señal EMG

### Potencia Total 

Potencia Total = 0.026677195208098428

### Frecuencia Media

Frecuencia media = 40.0 Hz

---

# Referencias

[1] “Electromyography (EMG) Sensor Data Sheet.” Accessed: Jun. 03, 2023. [Online]. Available: https://www.bitalino.com/storage/uploads/media/revolution-emg-sensor-datasheet-1.pdf

[2] U. Nacional De Colombia, C. Romo, H. Realpe, and J. Jojoa. "Análisis de Señales EMG Superficiales y su 
Aplicación en Control de Prótesis de Mano". Revista Avances en Sistemas e Informática, vol. 4, pp. 127–136, 2007, Available: https://www.redalyc.org/pdf/1331/133116856017.pdf

[3]
