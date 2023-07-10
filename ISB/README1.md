# Introducción a Señales Biomédicas
Bienvenidos al repositorio del **equipo 9**

Somos estudiantes de la carrera de Ingeniería Biomédica PUCP-UPCH 2023-1.
El proyecto abordará los temas de adquisición y procesamiento de señales electromiográficas. Se verá contenido teórico y práctico para conocer los procesos tecnológicos que se utilizan para el manejo de señales.

**Señal de interés:** Electrocardiograma (ECG)

**Integrantes del grupo:**  

 - Sebastian Alberto Chion Alvarado (colaborador) - sebastian.chion@upch.pe
 - Juan Manuel Mena Carrillo (colaborador) - juan.mena@upch.pe
 - Valeria Oriana Zavaleta Jave (colaborador) - valeria.zavaleta@upch.pe
 - Sofia Micaela Franco Zevallos (colaborador) - sofia.franco@upch.pe
 - Rosaura Valeria Astete Castro (colaborador) - rosaura.astete@upch.pe
 - Ariana Milagros Figueroa Chavez (colaborador) - ariana.figueroa@upch.pe

# Tabla de contenidos
1. [¿Qué es una Bioseñal?](#¿que-es-una-bioseñal?)
3. [Materiales](#materiales)
4. [Metodología](#metodología)
5. [Temática del proyecto](#temática-del-proyecto)
6. [Contenido del curso](#contenido-del-curso) 
7. [Participantes](#participantes)
8. [Docentes del curso](#docentes-del-curso)

---
### **¿Qué es una Bioseñal?**
<p align="justify"> 
Una bioseñal es una señal eléctrica, mecánica, química u óptica que se origina en un organismo vivo, como un ser humano o un animal que puede ser medida y analizada para obtener
información sobre el funcionamiento del cuerpo y para detectar posibles enfermedades o trastornos.
Algunos ejemplos comunes de bioseñales son el electrocardiograma (ECG), que mide la actividad eléctrica del corazón, la electromiografía (EMG), que mide 
la actividad eléctrica de los músculos, y la electroencefalografía (EEG), que mide la actividad eléctrica del cerebro. También hay bioseñales que se pueden medir 
mediante técnicas de imagenología, como la resonancia magnética (RM) y la tomografía por emisión de positrones (PET).

En resumen, una bioseñal es cualquier señal que se origina en un organismo vivo y que puede ser medida y analizada para obtener información sobre su 
funcionamiento y estado de salud.

<p align="center"> 
<img src="https://media.springernature.com/lw685/springer-static/image/chp%3A10.1007%2F978-3-030-43395-6_2/MediaObjects/107245_3_En_2_Fig1_HTML.png" align="center">
</p>


**ECG:**
Un electrocardiograma (ECG) es una bioseñal que se utiliza para medir la actividad eléctrica del corazón a lo largo del tiempo y se puede utilizar para detectar trastornos cardíacos y evaluar la función cardíaca.

Es una señal eléctrica débil que se origina en las células del músculo cardíaco. Durante cada ciclo cardíaco, se produce una serie de cambios eléctricos que son detectados por los electrodos del ECG colocados en la piel del paciente. Dicha señal está compuesta por varias ondas distintas que representan diferentes fases del ciclo cardíaco. La onda P representa la activación de las aurículas, el complejo QRS representa la activación de los ventrículos y la onda T representa la repolarización ventricular. Estas ondas pueden ser utilizadas para detectar problemas cardíacos como arritmias, enfermedad coronaria y otras afecciones cardíacas.

En resumen, es una bioseñal valiosa que se utiliza en una variedad de aplicaciones médicas, incluyendo la evaluación de la función cardíaca, la detección de trastornos cardíacos y el monitoreo del ritmo cardíaco durante la cirugía y otros procedimientos médicos. También se utiliza en la investigación médica para estudiar la actividad eléctrica del corazón y desarrollar nuevos tratamientos para enfermedades cardíacas.


<p align="center"> 
<img src="https://content.healthwise.net/resources/13.6/es-us/media/medical/hw/s_h9991262_001_2.jpg" align="center">
</p>


</p>

---
### **Materiales**
<p align="justify"> 

| Material   | Imagen Referencial  |
|:-------------: |:---------------:| 
| Arduino Nano 33 loT es una placa de desarrollo de tamaño reducido que integra capacidades de conectividad inalámbrica, procesamiento de datos y sensores, diseñada para proyectos de internet de las casas (loT) que requieren baja potencia y alta eficiencia energética          | ![lot](https://cdn.shopify.com/s/files/1/0506/1689/3647/products/ABX00027_03.front_860x645.jpg?v=1626445295)          |
| Fluke ProSim 4 Vital Signs Patient Simulator es un simulador de paciente que imita los signos vitales del paciente, como la presión arterial, la frecuencia cardiaca y la respiración, para ayudar en el entrenamiento y prueba de equipos médicos          | ![m](https://www.flukebiomedical.com/sites/default/files/styles/slideshow_image/public/prosim4front_0.png)          |
| BITalino es un kit de herramientas de prototipado rápido para proyectos de salud y bienestar personal. Incluye sensores inalámbricos y una plataforma de software para adquirir, procesar y visualizar datos biomédicos          | ![bi](https://cdn.sparkfun.com//assets/parts/1/1/8/2/8/14022-01a.jpg)          |
| El Arduino Tiny Machine Learning Kit es un paquete de hardware y software que permite a los usuarios implementar aprendizaje automático en dispositivos pequeños y de bajo consumo de energía, utilizando la plataforma Arduino y Edge Impulse          | ![a](https://www.aprendercreando.com.pe/wp-content/uploads/2021/04/AKX00028_00.default.jpg)         |


</p>

---
### **Metodología**
<p align="justify"> 

### VDI 2221

El modelo VDI 2221 centra sus actividades en la búsqueda de soluciones, con el fin de obtener información precisa para el desarrollo de un diseño eficaz que permita un prototipo que satisfaga en su totalidad las necesidades requeridas. El diseño de detalle contiene una participación importante según el diseño final.

Consta de los siguientes pasos:
1.  Tabla de requerimientos
2. Identificar entradas y salidas.
3. Esquema de funciones.
4. Matriz morfológica
5. Evaluación de conceptos de solución.
6. Proyectos preliminares.
7. Matrices de evaluación.
8. Proyecto óptimo. 

![](https://i0.wp.com/myengineerings.com/wp-content/uploads/2020/04/image-5.png?resize=723%2C485&ssl=1)

</p>

---
### **Temática del proyecto**
<p align="justify"> 

### Tema central

El tema central del proyecto será realizar un dipositivo o procedimiento que sea capaz de adquirir y procesar bioseñales como ECG, EEG, EMG, EOG, entre otras. Para el final del curso se realizara un prototipo de baja/mediana fidelidad.

### Adquisición de la señal médica

En todos los casos, una o más magnitudes físicas son convertidas en una señal mediante un dispositivo llamado transductor. 

El transductor es apoyado por un sistema de representación de la señal ya sea en el dominio del tiempo, espacio, frecuencia, etc. 

### Presentación de la señal médica
Está basada en la sensorialidad humana, es decir, apunta a la capacidad del humano de adquirir información mediante sus sentidos.
- Es principalmente visual
- Se usan sistemas coordenados, información por posición
- Se usan colores o matices, información por coloración

</p>

---
### **Contenido del curso**
<p align="justify"> 

El curso "Introducción a Señales Biomédicas" tiene por objetivo dar al estudiante una formación básica y sólida en los sistemas de adquisición y procesamiento de señales biomédicas. Abordaremos las diferentes materias que están presentes en los procesos de análisis de señales biomédicas, tales como: la fisiología, electrónica, informática médica y procesamiento de señales. Asimismo, se desarrollará un proyecto de investigación que esté basado en el procesamiento de señales biomédicas. Se dan las bases para que el alumno pueda profundizar en temas más avanzados en los tópicos presentes en los procesos de análisis de señales biomédicas.

### Proceso de aprendizaje
<p align="center"> 
<img src="https://upchlabib.com/wp-content/uploads/2023/03/contenidos-1.png" width="250" height="400" align="center">
</p>
</p>

---
### **Participantes**
<p align="justify"> 


### Sebastian Chion 
###### sebastian.chion@upch.pe
**Área de interés:** Ingeniería Clínica

<p align="center"> 
<img align="center" width="150" height="200" src="https://i.postimg.cc/fbDQq1Mg/IMG-1667.jpg">
</p>

### Juan Mena 
###### juan.mena@upch.pe
**Área de interés:** Señales e Imagenes Médicas

<p align="center"> 
<img src="https://i.postimg.cc/j2z2SHbj/Whats-App-Image-2021-09-06-at-5-42-25-PM.jpg"  width="150" height="200" align="center">
</p>

### Valeria Zavaleta
###### valeria.zavaleta@upch.pe
**Área de interés:** ingeniería clínica

<p align="center"> 
<img src="https://i.postimg.cc/90t9n5z1/val.jpg"  width="150" height="200" align="center">
</p>

### Sofia Franco
###### sofia.franco@upch.pe
**Área de interés:** Biomecánica y rehabilitación

<p align="center"> 
<img src="https://i.postimg.cc/XYts153H/SOFI3.jpg"  width="150" height="200" align="center">
</p>

### Rosaura Astete 
###### rosaura.astete@upch.pe
**Área de interés:** Tejidos y Biomateriales

<p align="center"> 
<img src="https://i.postimg.cc/tJ15zRwQ/ddfb4b44-02d5-43ad-b78d-ce0036390d6d.jpg"  width="150" height="200" align="center">
</p>

### Ariana Figueroa
###### ariana.figueroa@upch.pe
Tengo un interés por la investigación, desarrollo de prototipos y dispositivos biomedicina y por la impresión en 3D

<p align="center"> 
<img src="https://i.postimg.cc/tJtRj93Z/IMG-20220105-180620-01-2-1-preview-rev-1.png"  width="150" height="200" align="center">
</p>


</p>

---
### **Docentes del curso**
<p align="justify"> 

## Lewis De La Cruz
###### umbert.delacruz@upch.pe
Magíster en Informática Biomédica en Salud Global con mención en Informática en Salud de la Universidad Peruana Cayetano Heredia. Es un entusiasta por la investigación y el desarrollo tecnológico. Fue director y fundador del Centro de Capacitación en tecnologías de la industria 4.0 de Data Science Research Perú. Fue coordinador de laboratorios especializados en la UTP Piura. Mentor en programas de Ingeniería Biomédica por la IEEE EMBS UTP Y UNMSM. En la actualidad se desempeña como docente e investigador de la Escuela de Ingeniería de UPCH.

<p align="center"> 
<img src="https://upchlabib.com/wp-content/uploads/2023/02/l1.jpg"  width="300" height="300" align="center">
</p>

## Moises Meza
###### moises.meza@upch.pe
Ingeniero Electrónico con maestria en informática Biomédica en Salud Global, cuenta con experiencia 
en programación de sistemas embebidos, machine learning e informpatica en salud. Actualmente es el Lider de la Concentración de Señales e Imagenes Biomédica y docente de la Universidad Peruana Cayetano Heredia. Sumado a ello, esta liderando la comunidad peruana de TinyML(Machine Learning Embebido) donde promueve el desarrollo de proyectos electrónicos usando machine learning y edge computing.

<p align="center"> 
<img src="https://upchlabib.com/wp-content/uploads/2023/02/Screenshot-at-2023-02-23-18-40-03.png"  width="300" height="300" align="center">
</p>

## José Alonso Cáceres
###### jo.alonsok@gmail.com
Graduado de la Carrera de Ciencias Biomédicas de la Universidad Tecnológica de Sydney (Australia), cuenta además con un Diplomado en Ciencias de Datos de la Universidad Tecnológica de Monterrey (México). En la actualidad, se desempeña como analista de investigación científica y coordinador del área de investigación del Laboratorio Clinico ROE. Es uno de los fundadores y actual director de Tecnología e Información del emprendimiento social APPNEMIA. Sus principales intereses como investigador se encuentran dentro de las áreas de patología, inmunología y tecnología aplicada a ciencias de la salud. 

<p align="center"> 
<img src="https://upchlabib.com/wp-content/uploads/2023/02/alonso.jpg"  width="400" height="300" align="center">
</p>

## Julissa Vennacio
###### julissa.venancio@upch.pe
Ingeniera Mecatrónica, candidata a Magíster en Ingeniería Biomédica de la Pontificia Universidad Católica del Perú. Cuenta con diplomaturas en Salud Pública, Gestión de la Tecnología y la Innovación y Gestión de Proyectos basados en PMBOK. Especialista en equipamiento biomédico, evaluación de tecnologías en salud e instrumentación biomédica. Docente de la Diplomatura de Especialización de Hospitales BIM-PUCP. Investigadora del Laboratorio Bioingeniería PUCP. Cofundadora del proyecto My Oxygen System (MOSY). Becada por el programa de Innovación Médica 2022 dirigido por el Massachusetts Institute of Technology (MIT), Institute for Medical Engineering & Science (iMES) & MIT Innovation Initiative. Miembto del Comité Internacional Estudiantil Student & Recent Graduates Working Group (S&RG-WG) - International Federation of Medical and Biological Engineering (IFMBE). Principales intereses en investigación en ingeniería clínica, señales e imágenes biomédicas, evaluación de tecnologías sanitarias e instrumentación biomédica.

<p align="center">
<img src="https://upchlabib.com/wp-content/uploads/2023/03/Juliss-1.jpg"  width="300" height="300" align="center">
</p>


</p>