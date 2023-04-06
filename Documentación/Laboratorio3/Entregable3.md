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

EMG (Electromyography) es una técnica de diagnóstico médico que se utiliza para evaluar la actividad eléctrica de los músculos para investigación médica, rehabilitación y evaluación de trastornos neuromusculares. La EMG implica el uso de electrodos colocados en la superficie de la piel o en agujas finas que se insertan en el músculo para medir la actividad eléctrica durante la contracción muscular.

| <!-- -->      | <!-- -->        |
|:-------------: |:---------------:|
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda1.png)   | Explicación: jscidvorjneroibnvifmvfvmfo mfo fepv,fjnbnjbb djnvnidvnrinrbirnbirbmitbmtibtb         |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda2.png)   | Explicación          |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda3.png)   | Explicación          |

## Archivos de los datos de la señal ploteada

| <!-- -->      | <!-- -->        |
|:-------------:|:---------------:|
| [Video3](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Video3.txt)         | [Video3Modificado](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Video3Modificado.txt)       | 


## Ploteo de la señal en Python

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EMG         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/se%C3%B1alEMC.png)        | FFT        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/FFT.png)        |
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





