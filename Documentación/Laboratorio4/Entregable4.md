# **LABORATORIO 4: Uso de BiTalino para ECG**

## Objetivos
---
- Adquirir señal biomédica de ECG. 
- Hacer una correcta configuración de BiTalino. 
- Extraer la información de la señal ECG del software OpenSignals (r)evolution

***
## Introducción

### ANATOMÍA Y FISIOLOGÍA DEL CORAZÓN
El corazón es un órgano muscular compuesto por cuatro cámaras con dos aurículas que desembocan en los ventrículos derecho e izquierdo a través de las válvulas tricúspide y mitral, respectivamente. 
La ramificación de las fibras del músculo cardíaco y su conexión de extremo a extremo entre sí a través de discos intercalados hacen que se contraigan en forma de onda. Asimismo, el trabajo mecánico de bombear sangre a todo el cuerpo ocurre de manera sincronizada y está bajo el control del sistema de conducción cardíaco. Del mismo modo, se compone de dos tipos de células, células marcapasos y células no marcapasos [1]. 

Las células de marcapasos se encuentran principalmente en los nódulos SA y AV, y es el nódulo SA el que impulsa la frecuencia y el ritmo del corazón. El nodo AV queda suprimido por el ritmo más rápido del nodo SA, la función especial de este tipo de células es su despolarización espontánea sin un verdadero potencial de reposo, cuando esta despolarización espontánea alcanza el voltaje umbral, desencadena una despolarización rápida seguida de una repolarización [1]. 

Las células no marcapasos comprenden principalmente las células del músculo cardíaco auricular y ventricular y las fibras de Purkinje del sistema de conducción. Consisten en un verdadero potencial de membrana en reposo y, al iniciarse un potencial de acción, se desencadena una rápida despolarización, seguida de una fase de meseta y la subsiguiente repolarización. Los potenciales de acción son generados por la conductancia iónica a través de la apertura y el cierre de los canales iónicos [1].

### ELECTROCARDIOGRAMA
El electrocardiograma, abreviado como  EKG o ECG fue inventado por primera vez en 1902 por Willem Einthoven “padre de la electrocardiografía”. Poco tiempo después de su invención, el ECG fue reconocido como una sólida herramienta de detección y diagnóstico clínico.
Actualmente, el ECG es una modalidad de diagnóstico no invasivo que tiene un impacto clínico en la investigación de la gravedad de las enfermedades cardiovasculares [1].  El ECG mide la actividad eléctrica del corazón, esta actividad controla el latido del corazón y son las células marcapasos las que liberan ráfagas de energía eléctrica que viajan a través del músculo cardiaco y hacen que este se contraiga, esta contracción genera el bombeo de la sangre a través del corazón [2].

<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/ecg.gif">
</p>
<p align="center"> 
Señal ECG [2]
</p>

Asimismo, la velocidad con la que se mueve el electrocardiógrafo es de 25mm/seg. En la gráfica, el tiempo se representa en el eje x y el voltaje en el eje y. Respecto al eje X, 1 segundo se divide en cinco cuadrados grandes, cada uno de los cuales representa 0,2 segundos [1]. 

### SEÑAL DEL ELECTROCARDIOGRAMA

La señal del ECG tiene como objetivo reflejar la actividad eléctrica del corazón observada desde puntos estratégicos del cuerpo humano. Esta señal se caracteriza por cinco picos conocidos como puntos de referencia, que se representan con las letras P,Q,R, S y T [3].

- La onda P es el resultado de la despolarización de la aurícula y el ventrículo provoca el resto de picos.
- Intervalo PR representa el tiempo desde el comienzo de la despolarización auricular hasta el comienzo de la despolarización ventricular e incluye el retraso en el nodo AV
- El complejo QRS es la despolarización de ambos ventrículos cardiacos, utilizado como punto de referencia para el análisis de señales.
- El intervalo QT es un indicador de la repolarizacíón ventricular
- El segmento ST representa el final de la despolarización ventricular y el comienzo de la repolarización ventricular
- La onda Q representa la despolarización del tabique interventricular.
- La onda R representa el estímulo eléctrico a medida que pasa por los ventrículos durante la despolarización.
- La onda S representa la despolarización final de las fibras de Purkinje.
- La onda T representa la repolarización ventricular [1][3].
<p align="center"> 
<img align="center" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/ecg2.jpg">
</p>
<p align="center"> 
Morfología de la señal ECG [3]
</p>

---

## Materiales y Equipos

| Material   | Imagen Referencial  |
|:-------------: |:---------------:| 
| **BITalino** es un kit de herramientas de prototipado rápido para proyectos de salud y bienestar personal. Incluye sensores inalámbricos y una plataforma de software para adquirir, procesar y visualizar datos biomédicos         | ![lot](https://camo.githubusercontent.com/d4a44aa322d672288a9f7497916a86b024eaa53d3fa5c9b670ee08258c660f22/68747470733a2f2f63646e2e737061726b66756e2e636f6d2f2f6173736574732f70617274732f312f312f382f322f382f31343032322d3031612e6a7067)       |
| **Fluke ProSim 4 Vital Signs Patient Simulator** es un simulador de paciente que imita los signos vitales del paciente, como la presión arterial, la frecuencia cardiaca y la respiración, para ayudar en el entrenamiento y prueba de equipos médicos          | ![m](https://www.flukebiomedical.com/sites/default/files/styles/slideshow_image/public/prosim4front_0.png)          |
| **OpenSignals Software**: Se puede conectar mediante Bluetooth a la placa BITalino y permite adquirir y visualizar bioseñales          | ![bi](https://cdn.shopify.com/s/files/1/0595/1068/5887/t/6/assets/opensignalshorizontallogocoloralpha-1-1649366393124.png?v=1649366394)      |
***
## Fotos de Conexión Usada

### BiTalino - Cables

<p align="center"> 
<img align="center" src="/Documentación/Laboratorio4/Archivos/conexiones%20bitalino.jpg" width="500" height="400">
</p>

### Electrodos - Cuerpo
Para el primer paciente, la colocación de los electrodos positivo y negativo fue debajo de las clavículas izquierda y derecha respectivamente. El electrodo de referencia se colocó en la cresta ilíaca [5]. Esta ubicación se debe a que en estos puntos se proporciona una vista óptima del corazón. Además, en esta posición se evita la interferencia generada por otros músculos del pecho que se movilizan durante la respiración [4].

Sin embargo, para la segunda paciente, se colocaron los electrodos positivo y negativo en las muñecas izquierda y derecha respectivamente. En la gráfica se puede observar que posee más ruido debido a que los músculos del brazo generan interferencia en la señal [5].

| Paciente 1  | Paciente 2  |
|:-------------: |:---------------:|
| ![j](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/conexiones%20clavicula.jpg)         | ![k](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/conexiones%20mu%C3%B1eca.jpeg)         | 


***

## Video de la Señal en Estado Basal

<p align="center"> 
<img align="center" width="900" height="450" src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/video%201%20claviculas.gif">
</p>

***

## Ploteo de las señales en OpenSignals

### Paciente 1
| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal ECG en Estado Basal         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Estado%20basal%20clavicula.png)        | Señal ECG durante inhalación Profunda        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/Inhalacio%CC%81n%20profunda%20clavicula.png)        |
| Señal ECG durante resposo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG3.png)        | Señal ECG luego del ejercicio        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG4.png)        |

### Paciente 2

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal ECG en Estado Basal         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG1.png)        | Señal ECG durante inhalación Profunda        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG2.png)        |
| Señal ECG durante resposo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG3.png)        | Señal ECG luego del ejercicio        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG4.png)        |

***
## Resumen y explicaciòn de las señales ploteadas


***

## Archivos


***


## Ploteo de las señales en Python

### Links to GoogleColab
En el siguiente link, encontrará el código utilizado para el ploteo de las señales con python. 
`<link>` : https://colab.research.google.com/drive/1BnGfimvitJarySgA-P7BAQgUf0tI0zEb?usp=sharing

### Paciente 1
| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal ECG en Estado Basal         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG1.png)        | Señal ECG durante inhalación Profunda        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG2.png)        |
| Señal ECG durante resposo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG3.png)        | Señal ECG luego del ejercicio        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/SECG4.png)        |

### Paciente 2

| Señal  | Imagen  | Señal | Imagen |
|:-------------: |:---------------:| :-------------:|:-------------:|
| Señal ECG en Estado Basal         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG1.png)        | Señal ECG durante inhalación Profunda        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG2.png)        |
| Señal ECG durante resposo         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG3.png)        | Señal ECG luego del ejercicio        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio4/Archivos/VECG4.png)        |

***

## Comparación de las Señales obtenidas del paciente y las obtenidas mediante el ProSim 4 Vital Signs Patient Simulator


***

## Conclusiones

- El ECG es una herramienta esencial para la detección y el diagnóstico clínico de enfermedades cardíacas.
- La ubicación de los electrodos es importante para obtener una buena señal, ya que si ubicamos los electrodos en las muñecas se observan más ruido debido a que los músculos de brazo generan interferencia en la señal.

***


## Referencias
---
[1] Y. Sattar and L. Chhabra, “Electrocardiogram,” Nih.gov, Jan. 28, 2023. https://www.ncbi.nlm.nih.gov/books/NBK549803/<br>
[2] “ECG,” Utoronto.ca, 2015. http://pie.med.utoronto.ca/heart_physiology/module/ecg.html<br> 
[3] J. Aspuru et al., “Segmentation of the ECG Signal by Means of a Linear Regression Algorithm,” Sensors, vol. 19, no. 4, p. 775, Feb. 2019, doi: https://doi.org/10.3390/s19040775<br>
[4] “Improving ECG Quality Application Note.” Available: https://philipsproductcontent.blob.core.windows.net/assets/20170523/f2fc03ac224d4d5bb6aaa77c0151ac70.pdf<br>
[5] E. Secretario, “ESCUELA TÉCNICA SUPERIOR DE INGENIERÍA Y SISTEMAS DE TELECOMUNICACIÓN PROYECTO FIN DE GRADO.” Available: https://oa.upm.es/67385/1/TFG_JAVIER_CENDEJAS_LOPEZ.pdf
‌
***





