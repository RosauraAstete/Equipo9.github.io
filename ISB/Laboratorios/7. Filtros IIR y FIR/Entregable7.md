# **LABORATORIO 7: Filtros IIR y FIR**

## **Objetivos**

- Diseñar un IIR eligiendo si es Bessel, Butterworth, Chebyshev o Eliptico.
- Elegir 2 métodos de ventana para diseñar un filtro FIR
- Filtrar el Dataset de las señales ECG realizado en el laboratorio anterior.

***
## **Introducción**

### ¿Qué son los filtros?
Un filtro es un sistema que realiza un proceso de discriminación de una señal de entrada obteniendo variaciones en su salida, esto depende de algunos parámetros.
Los filtros digitales tienen como entrada una señal analógica o una señal digital y su salida es otra señal analógica o digital pero con variaciones como en su amplitud, frecuencia o fase dependiendo de las características del filtro [1]. Asimismo, el uso de filtros digitales es muy amplio hoy en día debido a la fácil disponibilidad de las computadoras.

**Ventajas:**
* Un filtro digital es altamente inmune al ruido debido a la forma en que se implementa.
* La precisión depende únicamente del error de redondeo que está directamente determinado por el número de bits que el diseñador elige para representar las variables en el filtro.
* Es fácil y económico cambiar las características operativas de un filtro.
* El rendimiento no depende de factores como el envejecimiento de los componentes, la variación de temperatura y tensión de alimentación, esto es muy importante en aplicaciones médicas, ya que la mayoría de señales tienen frecuencias bajas que pueden distorsionarse [2].


### Filtros IIR

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/gJ1jndvB/fir.png">
<p align="center">   
Fig x. Esquema de funcionamiento de un filtro IIR.
</p>

Es un tipo de filtro digital que establece que la respuesta a una entrada impulso (delta de Kronecker) existe indefinidamente con un número infinito de valores no nulos, por lo que nunca vuelve al reposo y se caracterizan por tener una retroalimentación de la señal de salida [3]. Debido a su diseño de retroalimentación, los filtros IIR pueden ser más eficientes en términos de uso de recursos computacionales en comparación con los filtros FIR. Los filtros IIR se utilizan comúnmente en aplicaciones de procesamiento de señales, como la eliminación de ruido, la ecualización de audio y la implementación de efectos de audio.

* Bessel: Este tipo de filtro tiene una respuesta de fase lineal, lo que significa que todas las frecuencias de la señal de entrada se retrasan por el mismo tiempo. Esto hace que sea útil en aplicaciones donde la distorsión de la fase es crítica, como en la señalización de datos o en la transmisión de señales de audio y vídeo [4].

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/xjy42Dz0/bessel.png">
<p align="center">   
Fig x. Filtro Bessel.
</p>

* Butterworth: Tiene una respuesta de amplitud plana en la banda pasante y una caída uniforme en la banda de rechazo. Esto significa que atenúa las frecuencias no deseadas de manera uniforme en toda la banda de rechazo. El filtro Butterworth se utiliza comúnmente en aplicaciones de audio y en la eliminación de ruido de señales de baja frecuencia [4]. Además, tienen como característica una atenuación de 3dB en el punto de corte. 

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/0jxXwZLR/butter.png">
<p align="center">   
Fig x. Filtro Butterworth.
</p>

* Chevyshev: Tiene una respuesta de amplitud de paso de banda irregular. Es capaz de proporcionar una atenuación más pronunciada en la banda de rechazo que el filtro Butterworth, a costa de una mayor irregularidad en la banda de paso. Esto lo hace útil en aplicaciones donde se requiere una mayor atenuación en la banda de rechazo, como en la eliminación de interferencias de radiofrecuencia [4].

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/gJ3Bj1tH/chev.png">
<p align="center">   
Fig x. Filtro Chevyshev.
</p>

* Elíptico: También conocido como filtro de Cauer, tiene una respuesta de amplitud de paso de banda y una banda de rechazo muy selectiva. Es útil en aplicaciones donde se requiere una alta selectividad en la banda de rechazo y en la banda de paso, como en la eliminación de interferencias de radiofrecuencia en sistemas de telecomunicaciones y en la separación de señales en el procesamiento de señales biomédicas [4].

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/KjNqrB2K/cauer.png">
<p align="center">   
Fig x. Filtro de Cauer (elíptico).
</p>


### Filtros FIR

<p align="center"> 
<img align="center" width="400" src="https://i.postimg.cc/fLVkzk09/iir.png">
<p align="center">   
Fig x. Esquema de funcionamiento de un filtro FIR.
</p>

Un filtro de respuesta de impulso finito posee un número limitado de términos. Este tipo de filtro es causal, lo que significa que solo depende de entradas presentes y pasadas. Entre otras de sus propiedades tenemos que es lineal, es decir, tiene un retardo de tiempo puro como respuesta de fase, y que es estable, por lo que siempre que la entrada del filtro esté acotada, la salida de este también lo estará. Estas propiedades ayudan al diseño de filtros FIR para que cumplan con ciertas especificaciones necesarias.

## **Tabla resumen**
### Filtros IIR
info

### Filtros FIR
info

### Tabla

| Campo  | Señal Cruda  | Filtro IIR | Filtro FIR |
|:-------------: |:---------------:| :-------------:| :-------------: |
| Basal        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)  | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)       | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg) |
| Inhalación Profunda        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)          |![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg) |
| Basal Post Inhalación        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)          | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg) |
| Post Ejercicio        | ![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)       |![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)       |![sinu](https://github.com/RosauraAstete/Equipo9.github.io/blob/main/ISB/Laboratorios/6.%20Ploteo%20de%20se%C3%B1al%20ECG%20en%20python/Archivos/basalc.jpg)     |



***
## **Creación del Dataset en Python**

### Link to GoogleColab
En el siguiente link, encontrará el código utilizado para la elaboración del Dataset de las señales con python. 
`<link>` : https://colab.research.google.com/drive/1S2x6B_OGGop9mRUyJigUtoExle4sktkw?usp=sharing

***

## Conclusiones

- 1
- 2
- 3

***

## Referencias
[1] J. Cedillo et al., “IMPLEMENTATION OF DIGITAL FILTERS OF FIR TYPE IN FPGA Implementación de Filtros Digitales Tipo FIR en FPGA,” vol. 37, 2008, Available: https://www.scielo.org.mx/pdf/poli/n37/n37a12.pdf

‌[2] Willis J. Tompkins. Biomedical digital signal procesing.Prentice Hall, may, 1993. 

[3] I. Grout, “Introduction to Digital Signal Processing,” Digital Systems Design with FPGAs and CPLDs, pp. 475–536, 2008, doi: https://doi.org/10.1016/b978-0-7506-8397-5.00007-6.

‌[4] D. Filtros, L. Martínez, A. Gómez, J. Serrano, J. Vila, and Gómez, “2.1,” 2009. Available: http://ocw.uv.es/ingenieria-y-arquitectura/filtros-digitales/tema_2._revision_de_los_tipos_de_filtros_analogicos_mas_comunes.pdf

‌

‌
***




