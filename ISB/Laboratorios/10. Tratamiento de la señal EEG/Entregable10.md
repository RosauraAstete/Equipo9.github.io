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
> Fig 3. Formula de conversión

Una vez realizada esta conversión, se obtiene los valores de la señal ECG en mV.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/convertido.png)
> Fig 4. Señal ECG en mV

## 2. Señal Filtrada
Se procede a filtrar la señal EEG.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/8.%20Tratamiento%20de%20la%20se%C3%B1al%20ECG/Archivos/FFTse%C3%B1al.png)
> Fig 5. Señal EEG filtrada

## 5. Detección de ERP
Ploteo de la señal de audio

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/1.1.png)
> Fig 6. Audio plot

Ploteo de la señal medida como respuesta al estímulo, en este caso el audio previamente mostrado
![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/1.2.png)
> Fig 7. Señal EEG obtenida como respuesta al estímulo

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/10.%20Tratamiento%20de%20la%20se%C3%B1al%20EEG/Archivos/1.3.png)
> Fig 8. Correlación cruzada entre ambas señales

## 6. Extracción de la banda Alfa

![]()
> Fig 9. Señal ECG y complejos QRS

# Referencias
[1] J. PAN, W. J. TOMPKINS, "A Real-Time QRS Detection Algorithm", IEEE Transactions on Biomedical Engineering, vol. 22, pp- 230-236, March 1985.

[2] PLUX-Wireless Biosignals, S.A., "Electrocardiography (ECG) - Sensor Data Sheet", PLUX-Wireless Biosignals, Lisbon, Portugal, ECG 011020, 2020.
