# INDICESDEDIVERSIDADBIOLOGIA
INDICES PARA BIOLOGOS DE CAMPO

PRIMER IDICE ES EL DE BRAY CURTIS - LEE POR FAVOR COMO APLICARLO Y QUE SIGNIFICA ESTE ANALISIS.

# PASO1-PRIMERO REALIZAREMOS LA DATAFRAME, EN ESTE CASO SERAN DIFERENTES ESPECIES RECOLECTADAS EN DIFERENTES NIVELES ALTITUDINALES - UNA MONTAÑA- 

# Paso 1: Crear el data frame con los datos
datos <- matrix(c(
  12, 12, 23, 51, 31, 1, 23, 43,
  31, 31, 3, 1, 2, 2, 32, 21,
  1, 12, 14, 2, 2, 5, 3, 23,
  2, 34, 31, 31, 12, 24, 34, 34
), nrow = 4, byrow = TRUE)

especies <- c("Especie 1", "Especie 2", "Especie 3", "Especie 4", "Especie 5", "Especie 6", "Especie 7", "Especie 8")
altitudes <- c("Altitud 231", "Altitud 355", "Altitud 443", "Altitud 544")

datos_df <- data.frame(especies, datos)
colnames(datos_df)[-1] <- altitudes

# Paso 3: Calcular la matriz de distancia de Bray-Curtis
distancia_bray <- vegdist(t(datos_df[, -1]), method = "bray")

# Paso 4: Realizar el clustering con la matriz de distancia de Bray-Curtis
cluster_bray <- hclust(distancia_bray, method = "complete")

# Paso 5: Crear el dendrograma del clustering
dendrograma <- as.dendrogram(cluster_bray)

# Paso 6: Mostrar el dendrograma
plot(dendrograma)












