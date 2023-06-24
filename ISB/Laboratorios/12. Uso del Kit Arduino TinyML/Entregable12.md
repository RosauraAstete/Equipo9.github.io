# Uso del Kit Arduino TinyML

## Objetivos del laboratorio

* Conocer los aspectos básicos del TinyML con el Arduino 33 BLE Sense.
* Explorar la plataforma Edge Impulse. 
* Conectar el Arduino nano 33 BLE Sense con Arduino y explorar ejemplos de TinyML.

## Materiales

| Modelo | Descripción | Cantidad |
|:--------:|:--------:|:--------:|
| TinyML Kit   | EL Kit incluye: Arduino nano 33 BLE, CámaraOV7675, Tiny ML Shield y cable USB   | 1   |
| -    | Laptop o PC   | 1   |

## Fundamentos

1. Tiny ML kit

    1.1. Arduino nano 33 BLE [1]:

    <p align="center">
        <img src="https://i.ebayimg.com/images/g/ADcAAOSwBTlduETz/s-l1600.jpg" alt="Texto alternativo" width="300px">
    </p>
   
      Comparte su configuración de pines con el Arduino Nano clásico, pero se basa en el microcontrolador nRF52840 con memoria flash de CPU de 1 MB. Con una unidad de medición inercial de 9 ejes y la posibilidad de conectividad Bluetooth Low Energy. 
      Algunas especificaciones técnicas:
      - Pin LED incorporado: 13
      - Pines de E/S digitales: 14
      - Pines de entrada lógica: 8
      - Pines PWM: 5
      - Interrupciones externas: Todos los pines digitales
      - Bluetooth: NINA-B306
      - Microcontrolador : nRF52840
      - Tensión de funcionamiento : 3.3 V
      - Voltaje de entrada (límite) : 21 V 
      - Velocidad de reloj : 64 MHz 
      - Memoria flash de la CPU : 1MB (nRF52840) 
      - SRAM : 256 KB (nRF52840)
        
  
      1.2. Cámara OV7675:

    <p align="center">
    <img src="https://www.uctronics.com/media/catalog/product/cache/a932a38b0e312591d2537bcc81c3c0e5/6/4/640x480_0.3_mp_mega_pixel_lens_ov7675_cmos_camera_module_with_adapter_board_side_view_1.jpg" alt="Texto alternativo" width="300px">
    </p>

    Este es un sensor de obturador rodante, que captura una columna (o fila) completa simultáneamente y compila la imagen al escanear a través (o hacia abajo). Cuenta con el sensor de color OV7675 (U6037) de OmniVision. El sensor tiene un formato óptico de 1/9,0″, que combinado con el tamaño de píxel de 2,5 µm x 2,5 µm, proporciona una imagen VGA de 0,3 MP (640 x 480) [2]. 
    Algunas especificaciones técnicas son:
    - Tamaño de matriz activa: 640 × 480
    - Fuente de alimentación:
      - Analógica: 2,6 ~ 3,0 V
      - Núcleo: 1,5 V CC + 5 % (regulador interno)
      - E/S: 1,71 ~ 3,0 V
    - Requisitos de energía:
      - Activo: 98 mW
      - En espera: 60 μW
    - Rango de temperatura:
      - Funcionamiento: -30°C a 70°C 
      - Imagen estable: 0°C a 50°C
    - Tamaño de lente: 1/9″
    - Frecuencia de reloj de entrada: 1,5 ~ 27 MHz
    - Relación señal/ruido: 38dB
    - Tamaño de píxel: 2,5 μm x 2,5 μm
    - Área de imagen: 1640 μm x 1220 μm [3]
  
3. Edge impulse

<p align="center">
  <img src="https://files.seeedstudio.com/wiki/Wio-Terminal-Edge-Impulse/banner.png" alt="Texto alternativo" width="500px">
</p>


Es una plataforma de machine learning diseñada específicamente para la creación y despliegue de modelos de inteligencia artificial en edge devices.
Permite entrenar modelos de aprendizaje automático y crear soluciones de inteligencia artificial que se ejecutan directamente en estos dispositivos de borde, sin necesidad de depender de una conexión a Internet o de una infraestructura de nube. Asimismo, proporciona herramientas y recursos para adquirir datos, etiquetarlos, entrenar modelos de aprendizaje automático y realizar pruebas en tiempo real [4].

3. Reconocimiento de imágenes

La identificación de objetos o características en imágenes o videos es conocida como reconocimiento de imágenes. Este proceso se emplea en diversas aplicaciones, como la detección de fallas, el manejo de imágenes médicas y la vigilancia de seguridad.

Algunas aplicaciones:

- Inspección visual: Proceso de detectar piezas defectuosas o no defectuosas durante la fabricación. Permite examinar de manera eficiente miles de piezas en una cadena de producción.

<p align="center">
    <img src="https://www.vibrant-rna.com/wp-content/uploads/2019/01/VInspection-and-QualityCtrol.607x406.jpg" alt="Texto alternativo" width="500px">
</p>

- Clasificación de imágenes: Consiste en organizar imágenes en diferentes categorías según su contenido. Es especialmente valiosa en aplicaciones como la recuperación de imágenes y los sistemas de recomendación en el comercio electrónico.

<p align="center">
    <img src="https://fiverr-res.cloudinary.com/images/t_main1,q_auto,f_auto,q_auto,f_auto/gigs/311631437/original/2ca654a24adf4b5dd5014092ae931d2607de85f1/object-detection-with-deep-learning.jpg" alt="Texto alternativo" width="500px">
</p>

- Conducción autónoma: Implica la capacidad de reconocer señales de alto o peatones en imágenes, lo cual es crucial en las aplicaciones de conducción autónoma.

<p align="center">
    <img src="https://www.diariomotor.com/imagenes/picscache/1440x655c/Tesla-conducci%C3%B3n-aut%C3%B3noma_visi%C3%B3n-c%C3%A1maras-sensores_1440x655c.jpg" alt="Texto alternativo" width="500px">
</p>

- En robótica: Se utiliza para mejorar la navegación autónoma de los robots, así como para identificar ubicaciones y objetos en su trayectoria.

<p align="center">
    <img src="https://i.blogs.es/314b66/robot-escritura/1366_2000.jpg" alt="Texto alternativo" width="500px">
</p>

Hay diversos enfoques para el reconocimiento de imágenes, que abarcan técnicas de aprendizaje automático (Machine Learning) y aprendizaje profundo (Deep Learning). La elección de la técnica a emplear depende de la aplicación en cuestión. Sin embargo, en términos generales, cuanto más complejo sea el problema, es más probable que se utilicen técnicas de Deep Learning [5].

## 1. Creación de proyecto en EdgeImpulse y el DataSet 

Crea un proyecto en EdgeImpulse y recopila el conjunto de datos para la aplicación de TinyML utilizando Arduino 33 BLE y la cámara OV7675.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/1DS.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>


> Fig 1. Creación del DataSet

## 2. Imagenes de para el entrenamiento

Captura imágenes utilizando la cámara OV7675 y agrégalas al conjunto de datos para entrenar tu modelo de TinyML.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/2_1DSB.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 2. Data traning, máscara blanca

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/2_2DSN.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 3. Data traning, máscara naranja

## 3. Modelo de entrenamiento

Utiliza EdgeImpulse para entrenar un modelo de aprendizaje automático con las imágenes recopiladas y configura los parámetros de entrenamiento.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/3ME.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 4. Entrenamiento 

## 4. Resultados del entrenamiento

Análisis de los resultados del entrenamiento, como la precisión y la pérdida, para evaluar el rendimiento del modelo de TinyML.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/4MER.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 5. Reporte del modelo

## 5. Prueba en vivo

Realiza pruebas en vivo utilizando el Arduino 33 BLE y la cámara OV7675 para capturar imágenes y utilizar el modelo entrenado para inferir y clasificar en tiempo real.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/5_1LVB.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 6. Pruebas con máscara blanca

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/5_2LVN.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 7. Pruebas con máscara naranja

## 6. Creación del modelo para Arduino

 Exporta el modelo entrenado desde EdgeImpulse en un formato compatible con Arduino y realiza la integración en tu proyecto de Arduino 33 BLE para su despliegue en el dispositivo.

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/6_1MArEG.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 8. Exportación del modelo

<p align="center">
  <img src="https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/12.%20Uso%20del%20Kit%20Arduino%20TinyML/Archivos/6_2MAr.PNG?raw=true" alt="Texto alternativo" width="700px">
</p>

> Fig 9. Visualización en el IDLE de Arduino

---
## Video Explicativo

[![Texto alternativo](https://img.youtube.com/vi/78Lp1fxr7tk/0.jpg)](https://www.youtube.com/watch?v=78Lp1fxr7tk)

Link: https://youtu.be/78Lp1fxr7tk

## Referencias
[1] “Nano 33 BLE | Arduino Documentation,” Arduino.cc, 2023. https://docs.arduino.cc/hardware/nano-33-ble.

[2] “OV7675 - 0.3 MP Camera Module w/ Stock Lens • dlscorp,” dlscorp, Jul. 23, 2022. 

[3] “0.3MP: OV7675 CMOS VGA Camera Module,” Arducam, Aug. 22, 2021. https://www.arducam.com/products/camera-breakout-board/0-3mp-ov7675/

[4] “Edge Impulse,” Edgeimpulse.com, 2023. https://www.edgeimpulse.com/ 

[5] “¿Qué es el reconocimiento de imágenes?,” Mathworks.com, 2023. https://es.mathworks.com/discovery/image-recognition matlab.html#:~:text=El%20reconocimiento%20de%20im%C3%A1genes%20es,y%20vigilancia%20de%20la%20seguridad.
