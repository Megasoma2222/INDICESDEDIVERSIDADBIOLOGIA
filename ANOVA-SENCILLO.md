#En este ejemplo cargaremos una base de datos en excel

#EJEMPLO: IMAGINEMOSNO QUE TENEMOS DOS PRODUCTOS A PRUEBA VEREMOS COMO INFLUEYEN SOBRE LA TEMPERATURA Y HUMEDAD 
-EN OTRO CASO PODRIAS APLICARLO SI FUESEN INSECTOS QUE ATACAN UN CULTIVO- TEMPERATURA Y HUMEDAD PODRIAS CAMBIARLO POR EL NOMBRE DEL INSECTO--- BUENO EL PRINCIPIO SERIA EL MISMO.

#PRODUCTO	TEMPERATURA	HUMEDAD

![image](https://github.com/Megasoma2222/INDICESDEDIVERSIDADBIOLOGIA/assets/137216764/f64dc171-ad72-407a-afab-52dfb7bd6df4)


#ESTA TABLA CONTIENE.... MAS DATOS

#EN ESTE CASO CARGUE EL EXCELL DESDE EXPORTAR, Y LUEGO LO TRANSFORME EN UN DATAFRAME LE LLAME "ANOVA"
df <-ANOVA

#ESPERA CABALLERO--- ANTES DE SEGUIR RECUERDA DESCARGAR UFFFF

library(ggpubr)
library(mlbench)
library(gridExtra)
library(ggpubr)
library(ggplot2)
 
 AHORA SÌ!!


# Realiza el ANOVA
anova_result <- aov(TEMPERATURA ~ PRODUCTO, data = df)

# Realiza el ANOVA EN ESTE CASO PARA TEMPERATURA- REALIZALO PARA AMBAS VARIABLE- MI CASO HUMEDAD Y TEMPERATURA.
anova_result <- aov(TEMPERATURA ~ PRODUCTO, data = df)

# Imprime los resultados del ANOVA
summary(anova_result)


# Realiza las pruebas post hoc de Tukey
posthoc_result <- TukeyHSD(anova_result)

# Imprime los resultados de las pruebas post hoc
print(posthoc_result)


 library(ggpubr)

# Gráfico de caja y bigote con puntos de dispersión por temperatura
p <- ggboxplot(df, x = "PRODUCTO", y = "TEMPERATURA",
               color = "PRODUCTO", palette = "jco",
               add = "jitter")

# Añadir valor p de la prueba de comparación de medias
p + stat_compare_means()

# Cambiar el método de prueba
p + stat_compare_means(method = "t.test")
 
 
Reucerda realizar el grafico con ambas varianbles -Humedad y temperatura-
 
RESULTADO:

![humedad](https://github.com/Megasoma2222/INDICESDEDIVERSIDADBIOLOGIA/assets/137216764/70652122-3278-4f02-b254-a2d147bb35c7)


![temperatura](https://github.com/Megasoma2222/INDICESDEDIVERSIDADBIOLOGIA/assets/137216764/02915bb4-9109-4e54-9d90-e871198ce300)



Saludos y que la fuerza los acompañe!


 
 

