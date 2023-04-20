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
src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/cerebro2.jpg">
<p align="center"> 
Regiones de la corteza cerebral asociadas con las funciones cerebrales. [en línea] Disponible en: https://human-memory.net/sensory-cortex/
</p>

El lóbulo frontal, en el cual nos enfocaremos en el presente laboratorio, es la región donde se toman la mayoría de sus pensamientos y decisiones conscientes. Asimismo, la corteza frontal contiene áreas motoras donde se controlan los movimientos voluntarios de todas nuestras extremidades y ojos.

<p align="center"> 
<img align="center" width="600" height="300" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/cerebro3.jpg">
</p>
<p align="center"> 
El cerebro y sus lóbulos superficiales con sus respectivas funciones (marcados en rojo)
</p>


### ENCEFALOGRAMA
El pionero en el EEG en humanos fue un psiquiatra alemán llamado Hans Berger en el año 1924 [3]. 

El EEG  es una técnica electrofisiológica para el registro de la actividad eléctrica que surge del cerebro humano, esta técnica es útil para evaluar pacientes con sospechas de convulsiones, epilepsias y episodios inusuales [3]. 

Para esta técnica indolora se colocan pequeños sensores en el cuero cabelludo para captar las señales eléctricas producidas, estas señales son registradas por una máquina, son amplificadas y aparecer como un gráfico en la pantalla de una computadora o como un registros que se puede imprimir en papel la cual luego será leída por un especialista altamente capacitado [4].

Estas señales se cree que son generadas principalmente por neuronas piramidales corticales en la corteza cerebral que están orientadas perpendicularmente a la superficie del cerebro. La actividad neuronal detectable por el EEG es la suma de los potenciales postsinápticos excitadores e inhibidores de grupos relativamente grandes de neuronas que se activan sincrónicamente [3]. 

Algo importante a considerar es que los artefactos eléctricos biológicos y ambientales con frecuencia interfieren con la capacidad del intérprete para identificar con precisión tanto los ritmos normales como los patrones patológicos [3].


### SEÑAL DEL ELECTROENCEFALOGRAMA
En una imagen de electroencefalograma los nombres de los sitios de los electrodos utilizan abreviaturas alfabéticas que identifican el lóbulo o el área del cerebro de la que cada electrodo registra:

- F = frontal
- Fp = frontopolar
- T = temporal
- C = centro
- P = parietales
- O = occipital
- A = auricular (electrodo de oído) [5]

Las ondas del EEG generalmente se clasifican según su frecuencia, amplitud, forma y posición de los electrodos.

- La frecuencia en Hertz es utilizada para determinar los ritmos normales y anormales.
- La forma de las ondas como alfa, beta, theta, delta y gamma se basa en la frecuencia de la señal, algunas ondas se reconocen en función de su forma, distribución de la cabeza y propiedad de simetría. Asimismo, la forma de la onda es normal a una edad específica, estado de alerta y sueño. Del mismo modo la frecuencia de las ondas cerebrales difiere y corresponde a diferentes comportamientos y estados mentales del cerebro. [6]

<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/tabla.jpg" width="600" height="400">
</p>

<p align="center"> 
Tipos de ondas de un EEG [6]
</p>

<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/tabla2.jpg" width="600" height="400">
</p>

<p align="center"> 
Tipos de ondas de un EEG [7]
</p>

***
## Materiales y Equipos

| Material   | Imagen Referencial  |
|:-------------: |:---------------:| 
| **BITalino** es un kit de herramientas de prototipado rápido para proyectos de salud y bienestar personal. Incluye sensores inalámbricos y una plataforma de software para adquirir, procesar y visualizar datos biomédicos         | ![lot](https://camo.githubusercontent.com/d4a44aa322d672288a9f7497916a86b024eaa53d3fa5c9b670ee08258c660f22/68747470733a2f2f63646e2e737061726b66756e2e636f6d2f2f6173736574732f70617274732f312f312f382f322f382f31343032322d3031612e6a7067)       |
| **OpenBCI GUI** es un software crea herramientas de código abierto para biodetección y neurociencia.         | ![m](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/BCI.jpg)          |
| **OpenSignals Software**: Se puede conectar mediante Bluetooth a la placa BITalino y permite adquirir y visualizar bioseñales          | ![bi](https://cdn.shopify.com/s/files/1/0595/1068/5887/t/6/assets/opensignalshorizontallogocoloralpha-1-1649366393124.png?v=1649366394)      |
| **Ultracortex "Mark IV" EEG Headset** permite adquirir hasta 16 canales de datos de EEG y puede combinarse con la placa OpenBCI Ganglion, Cyton o CytonDaisy.          | ![bi](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/ultra.jpg)      |

***

## Fotos de Conexión Usada

### BiTalino - Cables

<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/bitalino.jpg" width="600" height="400">
</p>

### Colocación de electrodos
La ubicación de los electrodos en la cabeza es importante para analizar las diferencias entre las señales obtenidas. Existe una convención de posicionamiento de electrodos llamada 10-20 que propone tomar cuatro puntos de referencia craneales universales (nasion, inion y ambos puntos pre-auricular), y distribuye proporcionalmente los electrodos del EEG sobre la superficie de la cabeza. El layout 10-20 tiene una distribución de distancias del 10% y 20% de las curvas de referencia central sagital y coronal. Si este porcentaje disminuye, aumenta la cantidad de electrodos [9].

<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/cabeza2.jpg" width="650" height="250">
</p>

<p align="center"> 
A-C: Colocacion electrodos EEG estándar del sistema 10-20. Modificado de: Seeck, M., Koessler, L., Bast, T., Leijten, F., Michel, C., Baumgartner, C., ... & Beniczky, S. (2017). La serie de electrodos estandarizados del EEG del IFCN. Neurofisiología clínica, 128(10), 2070-2077
</p>

| **Electrodos - Frente**  | **Electrodos - Ultracortex - Cabeza**  |
|:-------------: |:---------------:|
| ![j](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/electrodos2.jpg)         | ![k](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/juan32.jpg)         | 


### Limitaciones y Consideraciones
Para una mejor adquisición de las señales tanto con el bitalino como con el OpenBCI el ambiente debe ser el adecuado. En nuestro caso esto no fue posible ya que nos encontrábamos en el laboratorio donde había mucho ruido lo que llevaba a distracciones de la persona a la que se le estaba haciendo la medición. Esto hizo que en ocasiones el sujeto comenzara a apretar su mandíbula y esforzarse más para no perder la concentración. Estos movimientos especialmente en la región de la cara tienen un mayor efecto en la señal obtenida. Asimismo, para poder obtener la señal en la fase de referencia, se consideró tapar los ojos del paciente para evitar breves ráfagas de energía y respuestas a estímulos, como destellos de luz [8].
<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio5/Archivos/juan2.jpg" width="400" height="600">
</p>

***

## Videos de la Señales Obtenidas


### Señal EEG Fase de Referencia 

<p align="center"> 
<img align="center" width="900" height="450" 
src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/video%201%20claviculas.gif">
</p>

### Señal EEG durante Ciclo de Ojos abiertos y cerrados 

<p align="center"> 
<img align="center" width="900" height="450" 
src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/video%201%20claviculas.gif">
</p>

### Señal EEG durante Ejercicios Matematicos 

<p align="center"> 
<img align="center" width="900" height="450" 
src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/video%201%20claviculas.gif">
</p>

***

## Ploteo de las señales en OpenBCI GUI


| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Estado%20basal%20p1.png)        | Señal EEG Ciclo de ojos abiertos y cerrados        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Inhalacio%CC%81n%20profunda%20p1.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/reposo%20p1.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/ejercicio%20p1.png)        |

## Ploteo de las señales en OpenSignals

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Estado%20basal%20p1.png)        | Señal EEG Ciclo de ojos abiertos y cerrados        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Inhalacio%CC%81n%20profunda%20p1.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/reposo%20p1.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/ejercicio%20p1.png)        |

***
## Resumen y explicación de las señales ploteadas


En el ploteo de las señales para el primer paciente, podemos ver que no tiene tanto ruido como en el paciente 2. Esto se debe a la posición de los electrodos, en el caso de las clavículas, hay menos ruido ya que los músculos de la clavícula tiene menos movimiento que en las muñecas.<br>
Si analizamos las 4 gráficas del primer paciente, tenemos que en la inhalación profunda, el ruido aumenta que se debe al movimiento al realizar la respiración. Este mismo caso vemos luego del ejercicio, además ver de los picos desordenados que encontramos gracias a la interferencia que se genera entre el electrodo y la piel por la agitación del paciente.<br>
En el segundo paciente, vemos un caso similar. En la inhalación profunda encontramos más ruido que luego del ejercicio debido al movimiento de los hombros al inspirar.<br>

### Comportamiento de la señal EEG:
**Estado inicial de reposo:** Cuando un paciente está en reposo, la señal de ECG describe una frecuencia cardíaca regular y constante, con una duración de ciclo cardíaco (intervalo entre dos ondas R consecutivas) que se encuentra dentro de los valores normales. En este estado, las ondas P, QRS y T en la señal de ECG deberían ser simétricas, tener una forma y amplitud adecuada y estar bien definidas.

**Después de inhalación profunda y aguantar la respiración:** Cuando el paciente aguanta la respiración, la señal de ECG muestra una ligera disminución en la frecuencia cardíaca y de la amplitud, ya que el corazón recibe menos oxígeno. Durante este periodo, la señal muestra una disminución en el número de ondas R debido a la disminución del flujo sanguíneo y la hipoxemia temporal que se produce.

**Reposo post inhalación:** Después de que el paciente deja de aguantar la respiración, la señal de ECG debería volver a su estado inicial de reposo, con un ritmo cardíaco regular y estable.

**Después de realizar actividad física por 10 minutos:** La actividad física aumenta la demanda de oxígeno en el cuerpo y por lo tanto en el corazón, lo que puede resultar en un aumento en la frecuencia cardíaca. La señal de ECG durante la actividad física denota un aumento en la amplitud de las ondas P, QRS y T y una disminución en el intervalo entre ellas, lo que indica una mayor actividad eléctrica en el corazón. Después de la actividad física, la señal de ECG debería volver gradualmente a su estado de reposo normal.

***

## Archivos

### OpenBCI GUI

- [Fase de Referencia inicial]()
- [Ciclo de ojos abiertos y cerrados]()
- [Fase de Referencia post ciclo]()
- [Ejercicios Matematicos]()

### OpenSignals

- [Fase de Referencia inicial]()
- [Ciclo de ojos abiertos y cerrados]()
- [Fase de Referencia post ciclo]()
- [Ejercicios Matematicos]()

***

## Ploteo de las señales en Python

### Links to GoogleColab
En el siguiente link, encontrará el código utilizado para el ploteo de las señales con python. 
`<link>` : https://colab.research.google.com/drive/1BnGfimvitJarySgA-P7BAQgUf0tI0zEb?usp=sharing

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal EEG Fase de Referencia         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Estado%20basal%20p1.png)        | Señal EEG Ciclo de ojos abiertos y cerrados        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Inhalacio%CC%81n%20profunda%20p1.png)        |
| Señal EEG Fase de Referencia Post Ciclo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/reposo%20p1.png)        | Señal EEG durante Ejercicios Matematicos       | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/ejercicio%20p1.png)        |

***

## Conclusiones

- 

***


## Referencias

‌[1] “Sistema nervioso.” Available: https://www.infermeravirtual.com/files/media/file/99/Sistema%20nervioso.pdf?1358605492 <br>
[2] El, “Localización de electrodos del EEG: Layout Fijo vs. Variable | Bitbrain,” Bitbrain, Apr. 30, 2020. https://www.bitbrain.com/es/blog/colocacion-electrodos-eeg (accessed Apr. 20, 2023).<br>
[3] E. K. St et al., “Introduction,” Nih.gov, 2016. https://www.ncbi.nlm.nih.gov/books/NBK390346/ (accessed Apr. 20, 2023).<br>
[4] NHS Choices, “Electroencephalogram (EEG),” 2023. https://www.nhs.uk/conditions/electroencephalogram/ (accessed Apr. 19, 2023).<br>
‌[5] “How to Read an EEG,” Epilepsy Foundation, 2013. https://www.epilepsy.com/diagnosis/eeg/how-read (accessed Apr. 20, 2023).<br>
[6]J. S. Kumara, Analysis of Electroencephalography (EEG) Signals and Its Categorization–A Study https://www.sciencedirect.com/science/article/pii/S1877705812022114 (accessed Apr. 20, 2023).<br>
[7]Priyanka A. Abhang, ”Chapter 2 - Technological Basics of EEG Recording and Operation of Apparatus”, https://www.sciencedirect.com/science/article/abs/pii/B9780128044902000026 (accessed Apr. 20, 2023).<br>
[8] “BITalino (r)evolution Lab Guide.” Available: https://support.pluxbiosignals.com/wp-content/uploads/2022/04/HomeGuide3_EEG.pdf<br>
[9] El, “Localización de electrodos del EEG: Layout Fijo vs. Variable | Bitbrain,” Bitbrain, Apr. 30, 2020. https://www.bitbrain.com/es/blog/colocacion-electrodos-eeg (accessed Apr. 20, 2023).
‌

***
