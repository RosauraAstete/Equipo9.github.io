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
El ERP es definido como la actividad del EEG bloqueada en el tiempo o también llamado potencial relacionado con eventos. Los ERP son voltajes muy pequeños generados como respuesta a estímulos específicos. Con ellos se puede capturar la actividad neuronal que esté relacionada a procesos cognitivos y sensoriales ya que reflejan la actividad de los potenciales postsinápticos cuando muchas neuronas piramidales se disparan en sincronía. [3]

Los ERPs se caracterizan por su forma y tiempo de aparición en relación con el estímulo. Se dividen en dos grandes grupos, las que alcanzan su valor máximo en los primeros 100 milisegundos y los que se generan en partes posteriores. [3]


Ploteo de la señal de audio

![]()
> Fig 6. Audio plot

Ploteo de la señal medida como respuesta al estímulo, en este caso el audio previamente mostrado
![]()
> Fig 7. Señal EEG obtenida como respuesta al estímulo

![]()
> Fig 8. Correlación cruzada entre ambas señales

## 6. Extracción de la banda Alfa
Las ondas alfa van de 8 a 13 Hz de frecuencia y generalmente se observan en estado de relajación o descanso. Son lentas y de menor intensidad que las ondas beta y theta. Estas tienen mayor amplitud en las regiones occipital y frontal, pero también pueden ser notables en las zonas parietales y temporales. [4]

Se necesita conocer esta onda para poder diagnosticar y tratar trastornos neurológicos, ya que se ha demostrado que existen diferencias topográficas en la distribución de estas ondas para cada tipo de patología. [5]



![]()
> Fig 9. Señal ECG y complejos QRS

---
## ¿Qué se puede determinar con el análisis de señales EMG?
El análisis de la amplitud, tendencia central y variabilidad de la señal del electroencefalograma (EEG) puede ser útil para caracterizar y comprender diversas patologías y trastornos del sistema nervioso central. 

Algunas patologías que se pueden determinar con base en estos parámetro son las siguientes:

1. Epilepsia: La epilepsia es un trastorno crónico del cerebro, no contagioso, que se caracteriza por la presencia de convulsiones recurrentes. Estas convulsiones son episodios breves de movimientos involuntarios que pueden afectar una parte específica del cuerpo (convulsiones parciales) o todo el cuerpo en su totalidad (convulsiones generalizadas). En algunos casos, las convulsiones pueden ir acompañadas de pérdida de conciencia y dificultad para controlar las funciones intestinales o vesicales. En el análisis del EEG, se pueden observar cambios en la amplitud, como picos y ondas anormales, que indican actividad epiléptica. Además, la tendencia central y la variabilidad de la señal pueden proporcionar información sobre la frecuencia y la intensidad de las convulsiones [6].

2. Trastornos del sueño: Los trastornos del sueño son condiciones en las que se experimentan dificultades relacionadas con la calidad, el tiempo y la cantidad de sueño, lo que puede causar malestar durante el día y un deterioro en el funcionamiento general. Los cambios en la amplitud y la tendencia central de la señal pueden indicar interrupciones en los patrones normales del sueño. Además, la variabilidad de la señal puede ayudar a identificar la fragmentación del sueño y otros problemas relacionados [7].

3. Encefalopatía: La encefalopatía es un término utilizado para describir cualquier enfermedad que afecte el funcionamiento o la estructura del cerebro. En el EEG, se pueden observar cambios en la amplitud, como ondas lentas o anormales, que indican disfunción cerebral. Además, la tendencia central y la variabilidad de la señal pueden proporcionar información sobre la gravedad y el curso de la encefalopatía [8].

4. Traumatismo craneoencefálico: Una lesión en la cabeza ocurre cuando se recibe un golpe en esta área del cuerpo. Puede ser de naturaleza leve, causando una pequeña protuberancia o hematoma, o puede ser más grave y resultar en lesiones cerebrales como una conmoción cerebral o hemorragia cerebral, el EEG puede mostrar cambios en la amplitud y la tendencia central de la señal, lo que indica disfunción cerebral. La variabilidad de la señal también puede ser útil para evaluar la respuesta cerebral a la lesión y monitorear la evolución del paciente [9]



# Referencias
[1] J. PAN, W. J. TOMPKINS, "A Real-Time QRS Detection Algorithm", IEEE Transactions on Biomedical Engineering, vol. 22, pp- 230-236, March 1985.

[2] PLUX-Wireless Biosignals, S.A., "Electrocardiography (ECG) - Sensor Data Sheet", PLUX-Wireless Biosignals, Lisbon, Portugal, ECG 011020, 2020.

[3] S. Sur and V. Sinha, “Event-related potential: An overview,” vol. 18, no. 1, pp. 70–70, Jan. 2009, doi: https://doi.org/10.4103/0972-6748.57865.

[4]/“Fisiología de la actividad eléctrica del cerebro | FISIOLOGÍA,” fisiologia.facmed.unam.mx. https://fisiologia.facmed.unam.mx/index.php/fisiologia-de-la-actividad-electrica-del-cerebro 
‌
[5] J. Sánchez, M. Jofré, and M. Burán, Available: https://www.ucongreso.edu.ar/wp-content/uploads/2020/09/Las-ondas-alfa-del-electroencefalograma-cuantificado-y-su-relacio%CC%81n-con-la-evocacio%CC%81n-imaginaria-de-contenidos-diferenciados.pdf 

‌‌[6] World, “Epilepsy,” Who.int, Feb. 09, 2023. https://www.who.int/news-room/fact-sheets/detail/epilepsy.

[7] “What are Sleep Disorders?,” Psychiatry.org, 2023. https://www.psychiatry.org/patients-families/sleep-disorders/what-are-sleep-disorders.
‌
[8] “Encephalopathy,” National Institute of Neurological Disorders and Stroke, 2023. https://www.ninds.nih.gov/health-information/disorders/encephalopathy ‌

[9] “Head injuries,” Healthdirect.gov.au, Aug. 03, 2022. https://www.healthdirect.gov.au/head-injuries#:~:text=A%20head%20injury%20is%20a,or%20impairment%2C%20or%20even%20death. (accessed Jun. 03, 2023).

