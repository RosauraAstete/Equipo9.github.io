# **LABORATORIO 5: Procedimiento de registro EEG**

## Objetivos

- Adquirir señal biomédica de EEG. 
- Hacer una correcta configuración de BiTalino. 
- Extraer la información de la señal EEG del software OpenSignals (r)evolution
- Analizar la señal EEG obtenida con el OpenBCI

## Introducción

### ANATOMÍA Y FISIOLOGÍA DEL CEREBRO
El sistema nervioso está compuesto por una red de estructuras especializadas que regulan el funcionamiento de los órganos y sistemas y la relación del organismo con el medio externo. Este sistema está organizado para generar respuestas a los cambios internos o externos al organismo evaluando la información que recibe. [1]

El cerebro está compuesto por varias capas, la capa exterior se llama corteza cerebral. Aquí se ejecutan muchas de las funciones clave del sistema nervioso. La corteza se divide en cuatro partes llamadas lóbulos que tienen funciones cerebrales específicas. Estos son el lóbulo frontal, parietal, temporal y occipital. Cada región ha sido subdividida y está asociada a funciones cerebrales específicas. [2]

<p align="center"> 
<img align="center" width="600" height="300" 
src="Archivos/cerebro2.jpg">
<p align="center"> 
Regiones de la corteza cerebral asociadas con las funciones cerebrales [2].
</p>

El lóbulo frontal, en el cual nos enfocaremos en el presente laboratorio, es la región donde se toman la mayoría de sus pensamientos y decisiones conscientes. Asimismo, la corteza frontal contiene áreas motoras donde se controlan los movimientos voluntarios de todas nuestras extremidades y ojos.

<p align="center"> 
<img align="center" width="600" height="300" src="Archivos/cerebro3.jpg">
</p>
<p align="center"> 
El cerebro y sus lóbulos superficiales con sus respectivas funciones (marcados en rojo) [3][9]
</p>


### ENCEFALOGRAMA
El pionero en el EEG en humanos fue un psiquiatra alemán llamado Hans Berger en el año 1924 [4]. 

El EEG  es una técnica electrofisiológica para el registro de la actividad eléctrica que surge del cerebro humano, esta técnica es útil para evaluar pacientes con sospechas de convulsiones, epilepsias y episodios inusuales [4]. 

Para esta técnica indolora se colocan pequeños sensores en el cuero cabelludo para captar las señales eléctricas producidas, estas señales son registradas por una máquina, son amplificadas y aparecer como un gráfico en la pantalla de una computadora o como un registros que se puede imprimir en papel la cual luego será leída por un especialista altamente capacitado [5].

Estas señales se cree que son generadas principalmente por neuronas piramidales corticales en la corteza cerebral que están orientadas perpendicularmente a la superficie del cerebro. La actividad neuronal detectable por el EEG es la suma de los potenciales postsinápticos excitadores e inhibidores de grupos relativamente grandes de neuronas que se activan sincrónicamente [4]. 

Algo importante a considerar es que los artefactos eléctricos biológicos y ambientales con frecuencia interfieren con la capacidad del intérprete para identificar con precisión tanto los ritmos normales como los patrones patológicos [4].


### SEÑAL DEL ELECTROENCEFALOGRAMA
En una imagen de electroencefalograma los nombres de los sitios de los electrodos utilizan abreviaturas alfabéticas que identifican el lóbulo o el área del cerebro de la que cada electrodo registra:

- F = frontal
- Fp = frontopolar
- T = temporal
- C = centro
- P = parietales
- O = occipital
- A = auricular (electrodo de oído) [6]

Las ondas del EEG generalmente se clasifican según su frecuencia, amplitud, forma y posición de los electrodos.

- La frecuencia en Hertz es utilizada para determinar los ritmos normales y anormales.
- La forma de las ondas como alfa, beta, theta, delta y gamma se basa en la frecuencia de la señal, algunas ondas se reconocen en función de su forma, distribución de la cabeza y propiedad de simetría. Asimismo, la forma de la onda es normal a una edad específica, estado de alerta y sueño. Del mismo modo la frecuencia de las ondas cerebrales difiere y corresponde a diferentes comportamientos y estados mentales del cerebro. [7]

<p align="center"> 
<img align="center" src="Archivos/tabla.jpg" width="600" height="400">
</p>

<p align="center"> 
Tipos de ondas de un EEG [7]
</p>

<p align="center"> 
<img align="center" src="Archivos/tabla2.jpg" width="600" height="400">
</p>

<p align="center"> 
Tipos de ondas de un EEG [8]
</p>

***
## Materiales y Equipos

| Material   | Imagen Referencial  |
|:-------------: |:---------------:| 
| **BITalino** es un kit de herramientas de prototipado rápido para proyectos de salud y bienestar personal. Incluye sensores inalámbricos y una plataforma de software para adquirir, procesar y visualizar datos biomédicos         | ![lot](https://camo.githubusercontent.com/d4a44aa322d672288a9f7497916a86b024eaa53d3fa5c9b670ee08258c660f22/68747470733a2f2f63646e2e737061726b66756e2e636f6d2f2f6173736574732f70617274732f312f312f382f322f382f31343032322d3031612e6a7067)       |
| **OpenBCI GUI** es un software crea herramientas de código abierto para biodetección y neurociencia.         | ![m](Archivos/BCI.jpg)          |
| **OpenSignals Software**: Se puede conectar mediante Bluetooth a la placa BITalino y permite adquirir y visualizar bioseñales          | ![bi](https://cdn.shopify.com/s/files/1/0595/1068/5887/t/6/assets/opensignalshorizontallogocoloralpha-1-1649366393124.png?v=1649366394)      |
| **Ultracortex "Mark IV" EEG Headset** permite adquirir hasta 16 canales de datos de EEG y puede combinarse con la placa OpenBCI Ganglion, Cyton o CytonDaisy.          | ![bi](Archivos/ultra.jpg)      |

***

## Fotos de Conexión Usada

### BiTalino - Cables

<p align="center"> 
<img align="center" src="Archivos/bitalino.jpg" width="600" height="400">
</p>

### Colocación de electrodos
La ubicación de los electrodos en la cabeza es importante para analizar las diferencias entre las señales obtenidas. Existe una convención de posicionamiento de electrodos llamada 10-20 que propone tomar cuatro puntos de referencia craneales universales (nasion, inion y ambos puntos pre-auricular), y distribuye proporcionalmente los electrodos del EEG sobre la superficie de la cabeza. El layout 10-20 tiene una distribución de distancias del 10% y 20% de las curvas de referencia central sagital y coronal. Si este porcentaje disminuye, aumenta la cantidad de electrodos [10].

<p align="center"> 
<img align="center" src="Archivos/cabeza2.jpg" width="650" height="250">
</p>

<p align="center"> 
A-C: Colocacion electrodos EEG estándar del sistema 10-20 [13].
</p>

| **Electrodos - Frente**  | **Electrodos - Ultracortex - Cabeza**  |
|:-------------: |:---------------:|
| ![j](Archivos/electrodos2.jpg)         | ![k](Archivos/juan32.jpg)         | 


### Limitaciones y Consideraciones
Para una mejor adquisición de las señales tanto con el bitalino como con el OpenBCI el ambiente debe ser el adecuado. En nuestro caso esto no fue posible ya que nos encontrábamos en el laboratorio donde había mucho ruido lo que llevaba a distracciones de la persona a la que se le estaba haciendo la medición. Esto hizo que en ocasiones el sujeto comenzara a apretar su mandíbula y esforzarse más para no perder la concentración. Estos movimientos especialmente en la región de la cara tienen un mayor efecto en la señal obtenida. Asimismo, para poder obtener la señal en la fase de referencia, se consideró tapar los ojos del paciente para evitar breves ráfagas de energía y respuestas a estímulos, como destellos de luz [9].
<p align="center"> 
<img align="center" src="Archivos/juan2.jpg" width="400" height="600">
</p>

***

## Videos de la Señales Obtenidas


### Señal EEG Fase de Referencia 

<p align="center"> 
<img align="center" width="1000" height="350" 
src="Archivos/sentado.gif">
</p>

<p align="center"> 
<img align="center" width="1000" height="350" 
src="Archivos/basal.gif">
</p>

### Señal EEG durante Ciclo de Ojos abiertos y cerrados 

<p align="center"> 
<img align="center" width="1000" height="350" 
src="Archivos/ojo%20abierto%20y%20cerrado.gif">
</p>

### Señal EEG durante Ejercicios Matematicos 

<p align="center"> 
<img align="center" width="1000" height="350" 
src="Archivos/ejecricios%20de%20mate.gif">
</p>

***

## Ploteo de las señales en OpenBCI GUI


| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](Archivos/Reposo.png)        | Señal EEG Ciclo de ojos abiertos y cerrados        | ![sinu](Archivos/ojo%20abierto%20y%20cerrado.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](Archivos/reposo%202.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](Archivos/preguntas%20de%20mate.png)        |


## Ploteo de las señales en OpenSignals

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](Archivos/Linea%20basal.png)        | Señal EEG Ciclo de ojos abiertos y cerrados        | ![sinu](Archivos/Ojos%20abiertos.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](Archivos/reoposo%202%20bitalino.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](Archivos/ejercicios%20de%20mate.png)        |

***
## Resumen y explicación de las señales ploteadas

Las señales ploteadas se encuentran en constante variación y muestran que el EEG del paciente no tiene un patrón definido para ninguno de los 4 casos. Asimismo, tanto para las señales ploteadas en OpenBCI como en Open Signals, se puede observar la presencia de artefactos. Estas son señales intrusas de otras fuentes que a menudo también ingresan en la grabación, oscureciendo la señal EEG de nuestro interés. <br>

Entre los artefactos fisiológicos que alteraron las gráficas podemos mencionar al parpadeo involuntario, la activación muscular durante el apretamiento de los dientes, la tensión del hombre y cuello, sudoración de la piel [3]. Por otro lado, los artefactos técnicos que pudimos notar son el movimiento de los cables. La impedancia de los electrodos (Ω) constituyen una pared de resistencia eléctrica que causa que no se propague bien la actividad eléctrica. No se pudo evitar esta impedancia, pues no se contó con alcohol o gel o pasta conductora para los electrodos del BiTalino y del Ultracortex. <br>

### Comportamiento de la señal EEG:

**Fase de Referencia Inicial**  

Se observa que la señal ploteada es la de menor amplitud con respecto al resto de casos, pues el paciente no realiza ningún esfuerzo que incremente la señal. Asimismo, la señal típicamente muestra patrones de actividad eléctrica cerebral característicos de un cerebro en reposo. En este estado, la señal de EEG se caracteriza por presentar una actividad cerebral de baja frecuencia y amplitud en las ondas alfa (8-13 Hz) y beta (13-30 Hz) [11].

**Ciclo de Ojos Abiertos y Cerrados**  

Se observa que la señal ploteada incrementa de amplitud cuando la persona abre los ojos, esto debido a los destello de luz del ambiente [9]. Asimismo, la señal decrece su amplitud cuando la persona cierra los ojos. Los datos muestran que el poder de las ondas cerebrales de la banda alfa occipital puede incrementarse mediante procesos visuales sensibles al movimiento que persisten cuando los ojos están cerrados. En consecuencia, sugerimos que el poder de estas ondas cerebrales es, al menos en parte, un índice del grado en que la actividad cerebral visual está siendo inhibida. Esto aumenta cuando las personas cierran los ojos, pero puede aumentar aún más mediante la adaptación previa al movimiento radial.

**Fase de Referencia Post Ciclo**  

Se observa un notable decremento de la amplitud de la señal ploteada, pero no al nivel de la fase de referencia incial. Esto debido a que hubo una mayor exposición al ruido. Durante la exposición al ruido, se observa un aumento en la actividad de ondas beta (12-30 Hz) en el EEG, lo que indica una mayor actividad cerebral asociada con la atención y la alerta. Además, es posible que se observen cambios en las ondas alfa (8-12 Hz), que pueden disminuir durante la exposición al ruido debido a la interrupción de la meditación.


**Ejercicios Matemáticos**  

Se observa que la señal ploteada presenta picos de mayor amplitud con respecto al resto de casos, pues, cuando una persona realiza ejercicios matemáticos, la actividad cerebral se incrementa, lo que puede ser captado por la señal de EEG. En este caso, la actividad cerebral predominante es la de ondas beta, que están relacionadas con la atención y concentración mental, por lo que dichas ondas pueden presentar una mayor amplitud y frecuencia debido al esfuerzo que realiza la persona para llegar a la respuesta correcta [12]. 


***

## Archivos

### Open Signals

- [Fase de Referencia inicial](Archivos/Linea%20basal%202.txt)
- [Ciclo de ojos abiertos y cerrados](Archivos/ojos%20abiertos%20intento%201.txt)
- [Fase de Referencia post ciclo](Archivos/reposo%20de%20referencia%202.txt)
- [Ejercicios Matematicos](Archivos/preguntas%20de%20mate.txt)

### OpenBCI GUI

- [Fase de Referencia inicial](Archivos/FaseDeReferencia1.xlsx)
- [Ciclo de ojos abiertos y cerrados](Archivos/OjosAbiertosCerrados.xlsx)
- [Fase de Referencia post ciclo](Archivos/FaseDeReferencia2.xlsx)
- [Ejercicios Matematicos](Archivos/EjerciciosMatematicos.xlsx)

***

## Ploteo de las señales en Python

### OpenSignals
#### Links to GoogleColab
En el siguiente link, encontrará el código utilizado para el ploteo de las señales con python.
`<link>` : <https://colab.research.google.com/drive/192QPU5XfvNb46xe_tIGbUfdiAgfqOkLe#scrollTo=C2blB8p4P3R->

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](Archivos/estadobasal1.png)        | Señal EEG Ciclo de ojos abiertos y cerrados       | ![sinu](Archivos/ojosAC.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](Archivos/reposo2.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](Archivos/preguntasmate.png)        | 



### OpenBCI
#### Links to GoogleColab
En el siguiente link, encontrará el código utilizado para el ploteo de las señales con python.
`<link>` : https://colab.research.google.com/drive/1vQyoLgNWikoyaLRZOppep34Pg_TXNV3A#scrollTo=jz4e1dXchMz_

#### Señal durante Fase de Referencia Inicial

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Canal 1         | ![sinu](Archivos/1c1.png)        | Canal 2        | ![sinu](Archivos/1c2.png)        |
| Canal 3         | ![sinu](Archivos/1c3.png)        | Canal 4      | ![sinu](Archivos/1c4.png)        |
| Canal 5         | ![sinu](Archivos/1c5.png)        | Canal 6      | ![sinu](Archivos/1c6.png)        |
| Canal 7         | ![sinu](Archivos/1c7.png)        | Canal 8      | ![sinu](Archivos/1c8.png)        |

#### Señal durante Ciclo de Ojos Abiertos y Cerrados

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Canal 1         | ![sinu](Archivos/2c1.png)        | Canal 2        | ![sinu](Archivos/2c2.png)        |
| Canal 3         | ![sinu](Archivos/2c3.png)        | Canal 4      | ![sinu](Archivos/2c4.png)        |
| Canal 5         | ![sinu](Archivos/2c5.png)        | Canal 6      | ![sinu](Archivos/2c6.png)        |
| Canal 7         | ![sinu](Archivos/2c7.png)        | Canal 8      | ![sinu](Archivos/2c8.png)        |
  
#### Señal durante Fase de Referencia Post Ciclo  

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Canal 1         | ![sinu](Archivos/3c1.png)        | Canal 2        | ![sinu](Archivos/3c2.png)        |
| Canal 3         | ![sinu](Archivos/3c3.png)        | Canal 4      | ![sinu](Archivos/3c4.png)        |
| Canal 5         | ![sinu](Archivos/3c5.png)        | Canal 6      | ![sinu](Archivos/3c6.png)        |
| Canal 7         | ![sinu](Archivos/3c7.png)        | Canal 8      | ![sinu](Archivos/3c8.png)        |
  
#### Señal durante Ejercicios Matemáticos
  
| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Canal 1         | ![sinu](Archivos/4c1.png)        | Canal 2        | ![sinu](Archivos/4c2.png)        |
| Canal 3         | ![sinu](Archivos/4c3.png)        | Canal 4      | ![sinu](Archivos/4c4.png)        |
| Canal 5         | ![sinu](Archivos/4c5.png)        | Canal 6      | ![sinu](Archivos/4c6.png)        |
| Canal 7         | ![sinu](Archivos/4c7.png)        | Canal 8      | ![sinu](Archivos/4c8.png)        |



***

## Conclusiones

 - El electroencefalograma es una técnica muy útil para evaluar pacientes con sospechas de alguna enfermedad relacionada con el cerebro.
 - Algo a resaltar cuando se obtuvieron las señales ploteadas y con la revisión bibliográfica es que los ruidos ambientales, la luz y distintos factores que nos rodean con frecuencia interfieren con la capacidad del intérprete para identificar con precisión tanto los ritmos normales como los patrones patológicos.
 - La interpretación de las señales obtenidas puede ser un poco complicada de entender; sin embargo, con la bibliografía referencial pudimos identificar que cuando una persona se encuentra en reposo la señal EEG comúnmente mostrará actividad cerebral con frecuencias bajas y amplitud en las ondas alfa. Por otro lado, si se pudo identificar que cuando nuestro compañero fue sometido a un cuestionario matemático la actividad cerebral incrementó en esta señal predominaron las ondas beta.


***


## Referencias

‌[1] “Sistema nervioso.” Available: https://www.infermeravirtual.com/files/media/file/99/Sistema%20nervioso.pdf?1358605492 <br>
[2] El, “Localización de electrodos del EEG: Layout Fijo vs. Variable | Bitbrain,” Bitbrain, Apr. 30, 2020. https://www.bitbrain.com/es/blog/colocacion-electrodos-eeg (accessed Apr. 20, 2023).<br>
[3] "EEG (Electroencephalography): The Complete Pocket Guide - iMotions". iMotions. https://imotions.com/blog/learning/best-practice/eeg/ (accedido el 20 de abril de 2023). <br>
[4] E. K. St et al., “Introduction,” Nih.gov, 2016. https://www.ncbi.nlm.nih.gov/books/NBK390346/ (accessed Apr. 20, 2023).<br>
[5] NHS Choices, “Electroencephalogram (EEG),” 2023. https://www.nhs.uk/conditions/electroencephalogram/ (accessed Apr. 19, 2023).<br>
‌[6] “How to Read an EEG,” Epilepsy Foundation, 2013. https://www.epilepsy.com/diagnosis/eeg/how-read (accessed Apr. 20, 2023).<br>
[7]J. S. Kumara, Analysis of Electroencephalography (EEG) Signals and Its Categorization–A Study https://www.sciencedirect.com/science/article/pii/S1877705812022114 (accessed Apr. 20, 2023).<br>
[8]Priyanka A. Abhang, ”Chapter 2 - Technological Basics of EEG Recording and Operation of Apparatus”, https://www.sciencedirect.com/science/article/abs/pii/B9780128044902000026 (accessed Apr. 20, 2023).<br>
[9] “BITalino (r)evolution Lab Guide.” Available: https://support.pluxbiosignals.com/wp-content/uploads/2022/04/HomeGuide3_EEG.pdf<br>
[10] El, “Localización de electrodos del EEG: Layout Fijo vs. Variable | Bitbrain,” Bitbrain, Apr. 30, 2020. https://www.bitbrain.com/es/blog/colocacion-electrodos-eeg (accessed Apr. 20, 2023). <br>
‌‌[11] “Electroencefalograma (EEG) | Cigna,” Cigna.com, 2022. https://www.cigna.com/es-us/knowledge-center/hw/pruebas-mdicas/electroencefalograma-aa22249#:~:text=Normal%3A,en%20el%20trazado%20del%20EEG. (accessed Apr. 20, 2023). <br>
[12] “ANÁLISIS CON ELECTROENCEFALOGRAFÍA (EEG) DE LA ESCUCHA DE MÚSICA PARA EL ESTUDIO DE ESTRÉS ACADÉMICO.” Available: https://inaoe.repositorioinstitucional.mx/jspui/bitstream/1009/2048/1/Rogelio%20Sotero%20Reyes%20Galaviz-Tesis%20corregida.pdf <br>
[13] Seeck, M., Koessler, L., Bast, T., Leijten, F., Michel, C., Baumgartner, C., ... & Beniczky, S. (2017). La serie de electrodos estandarizados del EEG del IFCN. Neurofisiología clínica, 128(10), 2070-2077 <br>

***
