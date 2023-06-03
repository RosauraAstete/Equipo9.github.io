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

* El máximo es el valor más alto alcanzado por la señal EMG en un período de tiempo determinado. Representa la amplitud máxima de la actividad muscular registrada y puede ser útil para identificar momentos de máxima contracción o picos de actividad.

* El mínimo es el valor más bajo alcanzado por la señal EMG en un período de tiempo determinado. Representa la amplitud mínima de la actividad muscular registrada y puede ser útil para identificar momentos de mínima contracción o periodos de relajación.

* El promedio se calcula sumando todos los valores de la señal EMG y dividiendo por el número total de muestras. Representa la tendencia central de la señal y proporciona una medida de la actividad muscular promedio durante el período de tiempo analizado.

* La desviación estándar es una medida de la variabilidad o dispersión de los valores de la señal EMG con respecto a su promedio. Proporciona información sobre la amplitud de las fluctuaciones en la actividad muscular y puede ser útil para evaluar la estabilidad o variabilidad de la señal.

Estas medidas estadísticas son comunes utilizadas para caracterizar una señal EMG, pues proporcionan información sobre la amplitud, tendencia central y variabilidad de la señal importantes para caracterizar y entender la amplitud, tendencia y variabilidad de la señal EMG, y pueden ser utilizadas en la evaluación clínica, la investigación científica y el monitoreo del rendimiento muscular.


### Root Mean Square

El valor de RMS = 0.1637931652259006

El cálculo del Root Mean Square (RMS) en electromiografía es importante para obtener una medida cuantitativa de la amplitud de una señal EMG. Al calcular el RMS, se toman en cuenta los valores absolutos de la señal EMG durante un período de tiempo determinado, esto implica elevar al cuadrado los valores de la señal, promediar los resultados y luego tomar la raíz cuadrada del promedio para obtener una medida de la amplitud eficaz de la señal.


El RMS se utiliza comúnmente para analizar y caracterizar la actividad eléctrica pues la señal EMG es compleja y variable, y puede contener componentes de frecuencia diferentes; por lo tanto, el cálculo del RMS ayuda a resumir esta señal en un único valor que refleja la magnitud total de la actividad muscular.


### Área bajo la curva

Area bajo la curva = [ 0.06718251,  0.13086815,  0.05141693, ..., -0.046185,  -0.01205472,  0.04502639 ]

El cálculo del área debajo de la curva (ADC) en electromiografía es una medida importante para evaluar la amplitud acumulada de la actividad muscular en un intervalo de tiempo determinado. El ADC representa la integral de la señal EMG en un tiempo específico y se utiliza para comparar la actividad entre músculos, condiciones o sujetos, así como para evaluar la fatiga muscular. 

Es importante tener en cuenta que el ADC no brinda información sobre la forma o la frecuencia de la señal EMG, por lo que se utiliza junto con otras medidas para obtener una visión completa de la actividad eléctrica muscular.

### Potencia Espectral de la Señal
El potencial espectral de la señal, o también llamado la densidad de potencia espectral (PSD), nos muestra la forma en la que la energía de la señal está distribuída sobre las frecuencias en las que está formada. Se calcula mediante la transformada de Fourier de la señal y proporciona información sobre la intensidad o fuerza de cada componente de frecuencia presente en la señal. Con esta gráfica, se puede calcular la Frecuencia Media Instantánea (IMNF). [3]

Además, se utiliza para examinar el nivel de ruido de una señal en un rango específico de frecuencias. Si se normaliza este espectro, esta medida  se vuelve independiente de la duración de la señal. Esto nos permite comparar señales de diferentes duraciones debido a que con la normalización obtenemos una medida relativa de la distribución de energía en el espectro. [4] 

En la gráfica obtenida vemos que los picos más prominentes se encuentran alrededor de las frecuencias de 50Hz aproximadamente. Estas corresponden a las frecuencias armónicas de la señal. Asimismo, podemos ver que el ancho de banda de los picos es aproximadamente 10 Hz, lo que nos indica que existe una concentración de energía en una frecuencia específica. Por último, vemos que la forma del espectro no es uniforme, es decir, podemos afirmar que nuestra señal tiene frecuencias armónicas. [5]

![](https://hackmd.io/_uploads/S1a0f7uI3.jpg)
> Fig 12. Potencia Espectral de la señal EMG


### Potencia Total 
Potencia Total = 0.026677195208098428

La potencia total de una señal se define como la cantidad total de energía o potencia contenida en la señal. Se calcula con la suma de potencias de todas las frecuencias de la señal o mediante la integral de la densidad de potencia espectral (PSD) sobre todo el rango de frecuencias. [6] Este valor nos sirve para hallar algunos otros parámetros así como para caracterizar la señal, comparar la señales y para el control y procesamiento de señales. 
El valor obtenido es relativamente bajo, lo que nos indica que la energía también es baja. Mientras mayor sea el valor de la potencia total, mayor será la intensidad de la señal. 

### Frecuencia Media
Frecuencia media = 40.0 Hz
La frecuencia media de una señal es el promedio de todas las frecuencias presentes en la señal y se calcula mediante la suma de todas las frecuencias y dividiéndola por el número total de frecuencias. [a] Esta frecuencia nos ayuda al momento de caracterizar la señal, realizar el análisis espectral y en el filtrado de las señales, ya que nos puede servir como punto de referencia.

En este caso, un valor de frecuencia media de 40 Hz significa que los valores de las frecuencias se sitúan alrededor de este punto. 


---
## ¿Qué se puede determinar con el análisis de señales EMG?
Al analizar la amplitud, tendencia central y variabilidad de la señal EMG, se pueden determinar varias patologías y condiciones relacionadas con el sistema neuromuscular. Asimismo, la razón principal del interés en el análisis de señales EMG se encuentra en el diagnóstico clínico y las aplicaciones biomédicas [7]:

Algunas patologías son las siguientes:

1. Miopatías: Engloban una variedad de trastornos que afectan principalmente la anatomía, el metabolismo o el funcionamiento de los músculos esqueléticos. Estas afecciones suelen manifestarse a través de debilidad muscular que puede interferir con las actividades cotidianas. Al analizar la amplitud de la señal EMG, se puede observar una reducción en la amplitud de la actividad eléctrica en pacientes con miopatías, lo que indica debilidad muscular [8]. 

2. Neuropatías periféricas:Se refiere a una variedad de condiciones en las cuales se produce daño en el sistema nervioso periférico, el cual constituye una amplia red de comunicación encargada de enviar señales entre el sistema nervioso central (el cerebro y la médula espinal) y todas las otras partes del cuerpo. Al analizar la amplitud de la señal EMG, se puede observar una disminución en la amplitud o incluso la ausencia de actividad eléctrica en los músculos afectados [9]. 

3. Esclerosis lateral amiotrófica (ELA): Se trata de una enfermedad neurológica poco común que impacta a las neuronas motoras, es decir, a las células nerviosas ubicadas en el cerebro y la médula espinal encargadas de controlar el movimiento muscular voluntario. En la ELA, el análisis de la amplitud de la señal EMG puede mostrar una disminución en la amplitud de la actividad eléctrica debido a la degeneración de las células nerviosas [10].

4. Síndrome del túnel carpiano: Se trata de una afección neurológica frecuente que se produce cuando el nervio mediano, que se extiende desde el antebrazo hasta la palma de la mano, experimenta compresión o presión en la muñeca. Los síntomas pueden incluir entumecimiento, debilidad, dolor en la mano y la muñeca, así como hinchazón y dificultad para usar los dedos. Al analizar la amplitud de la señal EMG en los músculos afectados, se puede observar una disminución en la amplitud de la actividad eléctrica y posiblemente una menor variabilidad debido a la interferencia en la conducción nerviosa [11]. 

---
# Referencias

[1] “Electromyography (EMG) Sensor Data Sheet.” Accessed: Jun. 03, 2023. [Online]. Available: https://www.bitalino.com/storage/uploads/media/revolution-emg-sensor-datasheet-1.pdf

[2] U. Nacional De Colombia, C. Romo, H. Realpe, and J. Jojoa. "Análisis de Señales EMG Superficiales y su 
Aplicación en Control de Prótesis de Mano". Revista Avances en Sistemas e Informática, vol. 4, pp. 127–136, 2007, Available: https://www.redalyc.org/pdf/1331/133116856017.pdf

[3] J. L. Correa-Figueroa, E. Morales-Sánchez, J. A. Huerta-Ruelas, José-Joel Gonzalez-Barbosa, and C. R. Cárdenas-Pérez, “SEMG signal acquisition system for muscle fatigue detection,” Jan. 2016, doi: https://doi.org/10.17488/rmib.37.1.4.
‌
[4] J. Correa-Figueroa, E. Morales-Sánchez, J. Huerta-Ruelas, J. González-Barbosa, and C. Cárdenas-Pérez, “REVISTA MEXICANA DE INGENIERÍA BIOMÉDICA ib Sistema de Adquisición de Señales SEMG para la Detección de Fatiga Muscular,” vol. 37, no. 1, pp. 17–27, 2016, doi: https://doi.org/10.17488/RMIB.37.1.4.
‌
[5] G. Pequera and P. Biología, “Análisis tiempo-frecuencia de la.” Available: https://www.colibri.udelar.edu.uy/jspui/bitstream/20.500.12008/8156/1/uy24-17718.pdf

[6] M. o Gonçalves. Levantamento manual de carga repetitivo de curta duração com e sem o uso de cinto pélvico: efeito sobre a atividade EMG normalizada por diferentesv indicadores. Available: https://www.researchgate.net/profile/Mauro-Goncalves/publication/26623006_Effect_of_a_pelvic_belt_on_EMG_activity_during_manual_load_lifting/links/02e7e51d7246b0c856000000/Effect-of-a-pelvic-belt-on-EMG-activity-during-manual-load-lifting.pdf

[7] M. Mamun, M. Mahmood Hussain, and Faisal Mohd-Yasin, “Techniques of EMG signal analysis: detection, processing, classification and applications,” vol. 8, no. 1, pp. 11–35, Mar. 2006, doi: https://doi.org/10.1251/bpo115.
‌
[8] H. Nagy and Karthika Durga Veerapaneni, “Myopathy,” Nih.gov, Aug. 22, 2022. https://www.ncbi.nlm.nih.gov/books/NBK562290/#:~:text=cramps%2C%20and%20spasms.-,Myopathies%20are%20a%20heterogeneous%20group%20of%20disorders%20primarily%20affecting%20the,myopathies%20are%20associated%20with%20rhabdomyolysis.

‌[9] “Peripheral Neuropathy,” National Institute of Neurological Disorders and Stroke, 2023. https://www.ninds.nih.gov/health-information/disorders/peripheral-neuropathy.

[10] “Amyotrophic Lateral Sclerosis (ALS),” National Institute of Neurological Disorders and Stroke, 2021. https://www.ninds.nih.gov/health-information/disorders/amyotrophic-lateral-sclerosis-als 

[11] “Amyotrophic Lateral Sclerosis (ALS),” National Institute of Neurological Disorders and Stroke, 2021. https://www.ninds.nih.gov/health-information/disorders/amyotrophic-lateral-sclerosis-als.
