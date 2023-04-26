# Laboratorio 2: Adquisición de Señales y Graficación en Arduino

## Señal Sinusoidal


| Señal  | Imagen  |
|:-------------: |:---------------:|
|      Señal originada mediante el Generador de señales         |    ![sinu](Archivos/SinusoidalGenerador.PNG)    |
| Señal obtenida en el Osciloscopio         | ![sinu](Archivos/SinusoidalOsciloscopio.PNG)          |
| Señal obtenida y graficada en Arduino        | ![sinu](Archivos/SinusoidalArduino.jpeg)          |
| Señal graficada en Python y Código en [Google Collab](https://colab.research.google.com/drive/1fOutGNwRVHa_bOO49fnBsoD3h91hk9yZ?usp=sharing)| ![sinu](Archivos/SinusoidalPython.png)          |

## Señal Triangular



| Señal  | Imagen  |
|:-------------: |:---------------:|
|      Señal originada mediante el Generador de señales         | ![sinu](Archivos/TriangularGenerador.PNG)          |
| Señal obtenida en el Osciloscopio         | ![sinu](Archivos/TriangularOsciloscopio.PNG)          |
| Señal obtenida y graficada en Arduino        | ![sinu](Archivos/TriangularArduino.jpeg)          |
| Señal graficada en Python y Código en [Google Collab](https://colab.research.google.com/drive/12_nSBH1koHt02jyglJE-G3P-omtsNi12?usp=sharing)       | ![sinu](Archivos/TriangularPython.png)          |

## Señal Cuadrada



| Señal  | Imagen  |
|:-------------: |:---------------:|
|      Señal originada mediante el Generador de señales         | ![sinu](Archivos/CuadradaGenerador.PNG)          |
| Señal obtenida en el Osciloscopio         | ![sinu](Archivos/CuadradaOsciloscopio.PNG)          |
| Señal obtenida y graficada en Arduino        | ![sinu](Archivos/CuadradaArduino.jpeg)          |
| Señal graficada en Python y Código en [Google Collab](https://colab.research.google.com/drive/13uO8DAhqXYyyNppZi5XEAAY37xugvTKT?usp=sharing)       | ![sinu](Archivos/CuadradaPython.png)          |


## Código en Arduino 

```Arduino
unsigned long lastMsg = 0;
float  Fmax=20;                      // 1 hz
double  Fs = 10*Fmax;               // 10 hz
double Ts_ms = (1/Fs)*1000;     //  100 ms  

void setup() {
  Serial.begin(9600);
  while (!Serial);
  analogReadResolution(10);
  //Serial.println("R1:,R2:,");
}

void loop() {

  unsigned long now = millis();

  if (now - lastMsg > Ts_ms) {
    
    lastMsg = now;

    int r1 = analogRead(A0);
    float voltage = r1*3.3/1023.0;
    //int r2 = random(10);

    Serial.print("Señal1:");
    Serial.print(voltage);
    Serial.println(",");
    //Serial.print("Señal2:");
    //Serial.println(r2);
  }

}
```
