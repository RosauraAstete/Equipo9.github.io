
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
  
2. Edge impulse

Es una plataforma de machine learning diseñada específicamente para la creación y despliegue de modelos de inteligencia artificial en edge devices.
Permite entrenar modelos de aprendizaje automático y crear soluciones de inteligencia artificial que se ejecutan directamente en estos dispositivos de borde, sin necesidad de depender de una conexión a Internet o de una infraestructura de nube. Asimismo, proporciona herramientas y recursos para adquirir datos, etiquetarlos, entrenar modelos de aprendizaje automático y realizar pruebas en tiempo real [4].

3. Reconocimiento de imágenes

La identificación de objetos o características en imágenes o videos es conocida como reconocimiento de imágenes. Este proceso se emplea en diversas aplicaciones, como la detección de fallas, el manejo de imágenes médicas y la vigilancia de seguridad.

Algunas aplicaciones:

- Inspección visual: Proceso de detectar piezas defectuosas o no defectuosas durante la fabricación. Permite examinar de manera eficiente miles de piezas en una cadena de producción.

- Clasificación de imágenes: Consiste en organizar imágenes en diferentes categorías según su contenido. Es especialmente valiosa en aplicaciones como la recuperación de imágenes y los sistemas de recomendación en el comercio electrónico.

- Conducción autónoma: Implica la capacidad de reconocer señales de alto o peatones en imágenes, lo cual es crucial en las aplicaciones de conducción autónoma.

- En robótica: Se utiliza para mejorar la navegación autónoma de los robots, así como para identificar ubicaciones y objetos en su trayectoria.

Hay diversos enfoques para el reconocimiento de imágenes, que abarcan técnicas de aprendizaje automático (Machine Learning) y aprendizaje profundo (Deep Learning). La elección de la técnica a emplear depende de la aplicación en cuestión. Sin embargo, en términos generales, cuanto más complejo sea el problema, es más probable que se utilicen técnicas de Deep Learning [5].


## Código en Google Colab
El Balanceo de Datos fue realizado en Google Colab. En el siguiente enlace, podrá visualizar los resultados y el código utilizado.

`<link>` : https://colab.research.google.com/drive/1ETASNXJj_UIzZlZdq3cPj9Ov62ypebXz?usp=sharing


## 1. Leer el DataSet
Se analizará la base de datos de un ventilador mecánico con un analizador de gases y un pulmón artificial. 

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/11.%20Introducci%C3%B3n%20a%20la%20IA%20/Archivos/I1.PNG)
> Fig 1. DataSet

## 2. Desbalance de datos
Se evalualrá los datos de la presión ingresada y la presión que brinda el ventilador. Se puede apreciar que hay un desbalance, pues existe un error apreciable entre la presión ingresada y la presión del ventilador. En el grafico apreciamos el desbalance entre el error aceptable y el no aceptable. La diferencia es apreciable, por lo que relizar un oversampling es util para su entrenamiento con IA.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/11.%20Introducci%C3%B3n%20a%20la%20IA%20/Archivos/I2.png)
> Fig 2. Debalance

## 3. Reporte del modelo con el test
La diferencia entre precision y recall es muy distante.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/11.%20Introducci%C3%B3n%20a%20la%20IA%20/Archivos/I3.PNG)
> Fig 3. Reporte del modelo con el test

## 4. Reporte del modelo
La diferencia entre precision y recall disminuye.

![](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/11.%20Introducci%C3%B3n%20a%20la%20IA%20/Archivos/I5.PNG)
> Fig 4. Reporte del modelo

---
## Video Explicativo



## Referencias
[1] “Nano 33 BLE | Arduino Documentation,” Arduino.cc, 2023. https://docs.arduino.cc/hardware/nano-33-ble.

[2] “OV7675 - 0.3 MP Camera Module w/ Stock Lens • dlscorp,” dlscorp, Jul. 23, 2022. 

[3] “0.3MP: OV7675 CMOS VGA Camera Module,” Arducam, Aug. 22, 2021. https://www.arducam.com/products/camera-breakout-board/0-3mp-ov7675/

[4] “Edge Impulse,” Edgeimpulse.com, 2023. https://www.edgeimpulse.com/ 

[5] “¿Qué es el reconocimiento de imágenes?,” Mathworks.com, 2023. https://es.mathworks.com/discovery/image-recognition matlab.html#:~:text=El%20reconocimiento%20de%20im%C3%A1genes%20es,y%20vigilancia%20de%20la%20seguridad.
