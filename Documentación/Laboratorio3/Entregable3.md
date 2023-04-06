# **LABORATORIO 3: Uso de BiTalino para EMG**

## OBJETIVOS
- Adquirir señal biomédica de EMG.
- Hacer una correcta configuración de BiTalino.
- Extraer la información de la señal EMG del software OpenSignals (r)evolution

***
## Conexión Empleada

| Conexión  | Imagen |
|:-------------: |:---------------:|
| BITalino-cables         | <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/ConexionesBiTalino.png"  width="400" height="300">|
| Electrodos-Cuerpo       | <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/ConexionesBrazo.png"  width="400" height="300">|

## Video de la señal EMG adquirida

<p align="center"> 
<img align="center" width="900" height="450" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/EMG.GIF">
</p>

## Ploteo de la señal en OpenSignals

Al igual que los nervios, el tejido muscular conduce potenciales eléctricos y se el nombre asignado a estas señales eléctricas es potencial de acción muscular. Desde el aspecto anatómico y fisiológico, un músculo está compuesto por haces de células especializadas capaces de contraerse y relajarse. En el caso del tejido muscular, este tiene extensibilidad, elasticidad, capacidad de recibir y responder a estímulos y puede acortarse o contraerse. Si bien se pueden identificar tres tipos de tejido muscular, la EMG se aplica para el estudio del músculo esquelético, el cual está unido al hueso y su contracción es la responsable de sostener y mover el esqueleto, esta contracción es iniciada por impulsos de neuronas motoras las cuales pueden proporcionar estimulaciones a muchas fibras musculares. 

No obstante, al detectar y registrar una señal EMG existen factores que afectan en la fidelidad de una señal, tales como la relación señal-ruido y la distorsión de una señal.
Para hablar de la relación señal-ruido debemos de tener en cuenta que el rango de amplitud de una señal EMG es 0-10mV antes de una amplificación y estas señales adquieren ruido mientras van a través de los diferentes tejidos; sin embargo, el ruido eléctrico que afecta la señal EMG se puede clasificar de la siguiente forma:
 - Ruido inherente a los equipos médicos
 - Ruido ambiental
 - Artefacto de movimiento
 - Inestabilidad inherente de la señal

Para poder entender y explicar mejor las tres imágenes obtenidas en el laboratorio, se debe de tener en consideración la siguiente imagen, en la cual se observan los cambios de amplitud cuando el músculo se encuentra en reposo y cuando existe una contracción muscular.

<p align="center"> 
<img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/EjemploEMG.png" align="center">
</p>


| <!-- -->      | <!-- -->        |
|:-------------: |:---------------:|
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda1.png)   | En esta primera imagen se puede observar la señal de EMG durante el silencio eléctrico o el reposo. La amplitud de la señal es muy pequeña y no varía mucho. La pequeña magnitud que se aprecia antes del cambio se debe al ruido explicado anteriormente y a los pequeños movimientos del brazo en reposo.    |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda2.png)   | Se puede observar un incremento en la amplitud de la señal, esto se debe a que en ese momento se comenzó a contraer el músculo y generó la activación de más unidades motoras. Asimismo, la forma de onda es distinta en cada instante de la contacción, esto debido a que se usan diferentes unidades motoras.        |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda3.png)   | En esta última imagen se puede observar cómo la amplitud de la señal decrece hasta ser muy pequeña y no variar mucho. Esto se debe a que el músculo pasa de estar contraído, a estar relajado. Se utiliza una menor cantidad de fibras musculares|        

## Archivos de los datos de la señal ploteada

| <!-- -->      | <!-- -->        |
|:-------------:|:---------------:|
| [Video3](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Video3.txt)         | [Video3Modificado](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Video3Modificado.txt)       | 


## Ploteo de la señal en Python

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EMG         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/se%C3%B1alEMG.png)        | FFT        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/FFT.png)        |
| FFT en decibelios (dB)         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/FFTdB.png)        | Archivo .ipynb         | [EMG.ipynb](https://colab.research.google.com/drive/12pRxEPb44RMLwJIfce5WDyqkPjPfjwqx?usp=sharing)        |


### Python code
```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
import re

## Pasando a dataframe

array1 = np.genfromtxt("Video3Modificado.txt",   skip_header=1, delimiter="\t")
array1

plt.plot(array1[:,-2])
plt.xlabel("Número de muestras")
plt.title("Señal EMG")

###Señal EMG en función del tiempo

## Sabemos que la frecuencia de muestrero fue de 1000 Hz
Fs = 1000
Ts = 1/Fs
n = len(array1[:,-2])
t = np.arange(0,25800,1)*Ts
plt.plot(t, array1[:,-2])
plt.xlabel("Tiempo [segundos]")
plt.title("Señal EMG")

###FFT en frecuencia normalizada en radianes

signal1 = array1[:,-2]
S = np.fft.fftshift(np.fft.fft(signal1))
k = np.arange(-12900,12900,1)
w = (3.1416/12900)*k
plt.plot(w,abs(S))

plt.xlabel("Frecuencias normalizada en radianes")
plt.title("FFT")

### FFT en decibeles dB

N = 2**10                                     # 10 bits, 0-1023

signal1 = array1[:,-2]

signal_fft = np.fft.fft(signal1, N)   
signal_fft = np.fft.fft(signal1, N)           # fft magtinud
signal_fft = np.round(np.abs(signal_fft),3)[0:N//2] # nos quedamos con los componente de la derecha de la FFT
signal_aux = signal_fft/signal_fft.max()     # hallamos el maximo para pasar la magnitud a escala db

with np.errstate(divide='ignore'):
    signal_fft_db = 10*np.log10(signal_aux)  # , out=signal_aux, where=signal_aux >= 0 para evitar division por zero

F_list = np.linspace(0,Fs/2, N//2)
F = np.round(F_list[np.argmax(signal_fft_db)], 1)   # argmax, encuentra el argumento max en un array

plt.plot(F_list, signal_fft_db)  #10 * np.log10(P / Pref) , decibelios
plt.text(F,0, f"{F}Hz")
plt.grid(linestyle=":")
plt.ylabel("Magnitud (db)")
plt.xlabel("Frecuencias (Hz)")
plt.title("FFT en el decibelios")
plt.xlim([0,200])
plt.xticks(np.arange(0,200,10))
plt.show()
```





