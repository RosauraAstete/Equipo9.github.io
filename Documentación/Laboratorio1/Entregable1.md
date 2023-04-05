# Laboratorio 1

## Señal Sinusoidal


| Señal  | Imagen  |
|:-------------: |:---------------:|
|      Señal originada mediante el Generador de señales         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio1/Archivos/SinusoidalGenerador.PNG)          |
| Señal obtenida en el Osciloscopio         | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio1/Archivos/SinusoidalOsciloscopio.PNG)          |
| Señal obtenida y graficada en Arduino        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio1/Archivos/SinusoidalArduino.jpeg)          |
| Señal graficada en Python        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/Documentaci%C3%B3n/Laboratorio1/Archivos/SinusoidalPython.png)          |

## Señal Triangular



| Señal  | Imagen  |
|:-------------: |:---------------:|
| Señal originada mediante el Generador de señales         | Cell 2          |
| Señal obtenida en el Osciloscopio         | Cell 5          |
| Señal obtenida y graficada en Arduino        | Cell 8          |
| Señal graficada en Python        | Cell 8          |

## Señal Cuadrada



| Señal  | Imagen  |
|:-------------: |:---------------:|
| Señal originada mediante el Generador de señales         | Cell 2          |
| Señal obtenida en el Osciloscopio         | Cell 5          |
| Señal obtenida y graficada en Arduino        | Cell 8          |
| Señal graficada en Python        | Cell 8          |


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
