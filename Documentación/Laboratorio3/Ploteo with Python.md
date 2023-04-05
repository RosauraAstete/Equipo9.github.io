
####Python code

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
plt.title("Señal EMC")

###Señal EMC en función del tiempo

## Sabemos que la frecuencia de muestrero fue de 1000 Hz
Fs = 1000
Ts = 1/Fs
n = len(array1[:,-2])
t = np.arange(0,25800,1)*Ts
plt.plot(t, array1[:,-2])
plt.xlabel("Tiempo [segundos]")
plt.title("Señal EMC")

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
