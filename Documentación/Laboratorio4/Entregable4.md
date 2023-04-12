# **LABORATORIO 4: Uso de BiTalino para ECG**

## Objetivos
---
- Adquirir señal biomédica de ECG. 
- Hacer una correcta configuración de BiTalino. 
- Extraer la información de la señal ECG del software OpenSignals (r)evolution

## Conexión Empleada
---
| Conexión  | Imagen |
|:-------------: |:---------------:|
| BITalino-cables         | ![Bitalino](/Documentación/Laboratorio4/Archivos/conexiones%20bitalino.jpg)|
| Electrodos-Cuerpo clavículas       | ![Conexiones clavicula](/Documentación/Laboratorio4/Archivos/conexiones%20clavicula.jpg)|
| Electrodos-Cuerpo muñecas      | ![Conexiones muñecas](/Documentación/Laboratorio3/Archivos/ConexionesBrazo.png)|

## Video de la señal EMG adquirida
---
<p align="center"> 
<img align="center" width="900" height="450" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/video%201%20claviculas.gif">
</p>

## Ploteo de la señal en OpenSignals
---
.

<p align="center"> 
<img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/EjemploEMG.png" align="center">
</p>


| <!-- -->      | <!-- -->        |
|:-------------: |:---------------:|
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda1.png)   | .   |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda2.png)   | .        |
|![o](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio3/Archivos/Onda3.png)   | .|        

## Archivos de los datos de la señal ploteada
---
.....

## Colocación de los electrodos
---
En el primer ensayo, la colocación de los electrodos positivo y negativo fue debajo de las clavículas izquierda y derecha respectivamente. El electrodo de referencia se colocó en la cresta ilíaca [a]. Esta ubicación se debe a que en estos puntos se proporciona una vista óptima del corazón. Además, en esta posición se evita la interferencia generada por otros músculos del pecho que se movilizan durante la respiración [b].

Sin embargo, en el segundo ensayo, se colocaron los electrodos positivo y negativo en las muñecas izquierda y derecha respectivamente. En la gráfica se puede observar que posee más ruido debido a que los músculos del brazo generan interferencia en la señal [a].

## Ploteo de la señal en Python
---

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

## Referencias
---
[1]


