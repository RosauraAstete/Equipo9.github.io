
# Uso del Kit Arduino TinyML

## ¿Qué es el balanceo de datos?

A menudo, los datos del mundo real no están disponibles según nuestras expectativas, tienen muchas irregularidades y es un desafío tratar con esos datos. Uno de los principales obstáculos en el manejo de tales datos es que están desequilibrados. El balanceo de datos, es una técnica utilizada en el procesamiento de datos, especialmente en el campo del aprendizaje automático (Machine Learning) y la minería de datos, para abordar el desequilibrio de clases en un conjunto de datos [1].

## Balanceo de Datos e Inteligencia Artificial

El rendimiento general de los modelos de Machine Learning basados en conjuntos de datos desequilibrados se verá limitado por su capacidad para predecir puntos raros y minoritarios. Los conjuntos de datos desequilibrados crean desafíos para el modelado predictivo. 

Equilibrar un conjunto de datos facilita el entrenamiento de un modelo, pues ayuda a evitar que este se sesgue hacia una clase. En otras palabras, el modelo ya no favorecerá a la clase mayoritaria solo por contener más datos [2].

El balanceo de datos busca corregir esta desproporción mediante diferentes técnicas. Algunas de las técnicas comunes utilizadas para equilibrar los datos incluyen [1][3]:

- Submuestreo (undersampling): Consiste en eliminar aleatoriamente ejemplos de la clase mayoritaria hasta alcanzar un equilibrio entre las clases. Es relativamente simple de implementar y puede mejorar el tiempo de ejecución del modelo y los costos de cómputo. Sin embargo, debe realizarse con cuidado, ya que la eliminación de muestras del conjunto de datos original podría provocar la pérdida de información útil.

- Sobremuestreo (oversampling): Implica replicar aleatoriamente ejemplos de la clase minoritaria para igualar la cantidad de muestras en ambas clases. Sin embargo, debido a que la clase minoritaria todavía se compone de una cantidad limitada de puntos de datos únicos, el modelo es susceptible de memorizar patrones de datos y sobreajuste. 

- Generación sintética de muestras: Se utilizan algoritmos para generar nuevas muestras sintéticas de la clase minoritaria, basadas en las muestras existentes. Esto aborda el desequilibrio sin duplicar directamente las muestras existentes y puede ser útil cuando el conjunto de datos es limitado. Ejemplo: método SMOTE [4]. 

---

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


# Referencias
[1] T. A. Team, “Imbalanced Data and How to Balance It – Towards AI,” towardsai.net. https://towardsai.net/p/l/imbalanced-data-and-how-to-balance-it

[2] “Balanced and Imbalanced Datasets in Machine Learning [Introduction],” encord.com. https://encord.com/blog/an-introduction-to-balanced-and-imbalanced-datasets-in-machine-learning/

[3] He, H., & Garcia, E. A. (2009). Learning from imbalanced data. IEEE Transactions on knowledge and data engineering, 21(9), 1263-1284.

[4] Chawla, N. V., Bowyer, K. W., Hall, L. O., & Kegelmeyer, W. P. (2002). SMOTE: Synthetic minority over-sampling technique. Journal of artificial intelligence research, 16, 321-357.

