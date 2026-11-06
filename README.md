# Laboratorio · Reglas de asociación con Apriori

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Xen-04/Portafolio_Mineria_de-_datos/blob/main/2.6_reglas_de_asociacion/lab_apriori_bakery.ipynb)

Análisis de canasta de mercado sobre las ventas de una panadería-cafetería, usando el algoritmo **Apriori** (`mlxtend.frequent_patterns`).

## Dataset

- **Fuente:** Kaggle, [`akashdeepkuila/bakery`](https://www.kaggle.com/datasets/akashdeepkuila/bakery)
- **Contexto:** ventas de una panadería-cafetería (Edimburgo, 2016-2017).
- **Transacción:** una compra de un cliente (`TransactionNo`).
- **Ítem:** un producto dentro de esa compra (`Items`).
- **Tamaño:** 20.507 filas, 9.465 transacciones y 94 ítems distintos, sin valores nulos.

## Qué hace el notebook

| Sección | Contenido |
|---|---|
| 1 | Descarga del dataset con `kagglehub` y Colab Secrets |
| 2 | Descripción y limpieza (espacios en nombres, filas que no son productos, ítems repetidos por boleta) |
| 3 | Codificación binaria (una fila por transacción, una columna por ítem) |
| 4 | Itemsets frecuentes con soporte mínimo justificado por la distribución de frecuencias |
| 5 | Reglas de asociación ordenadas por lift (soporte, confianza y lift visibles) |
| 6 | Experimento: comparación de 5 configuraciones de soporte y confianza mínimos |
| 7 | Interpretación en lenguaje de negocio: 5 reglas valiosas, 1 regla descartada y una decisión para el administrador |
| 8 | Verificación manual de una regla contando sobre una muestra |
| 9 | Reflexión final |

## Resultados principales

- El café aparece en cerca de la mitad de las compras, por lo que casi todas las reglas lo tienen como consecuente.
- **Tostadas → Café:** confianza ≈ 70 % y lift ≈ 1,47, la combinación más sólida con volumen.
- **Regla descartada: Té → Café.** Supera los umbrales, pero su lift es ≈ 0,73 (< 1): los clientes de té compran café menos que el promedio.
- **Decisión sugerida:** combo "desayuno" de tostadas con café, con el mostrador de café junto a tostadas y medialunas.

> Las cifras exactas están en las salidas del notebook.

## Cómo ejecutarlo

1. Abre el notebook con la insignia de arriba.
2. En Colab, crea el *Secret* `KAGGLE_API_TOKEN` con tu token de Kaggle y activa **Notebook access**.
3. Ejecuta todas las celdas en orden (*Entorno de ejecución → Ejecutar todo*).

## Seguridad

El token de Kaggle no está en el repositorio ni en el notebook. Se lee únicamente desde Colab Secrets.

## Alcance

Las reglas de asociación describen **co-ocurrencias**, no causas. No son un modelo de predicción ni de clasificación, por lo que no se calculan métricas de exactitud (accuracy).

## Tecnologías

Python · pandas · mlxtend · matplotlib · kagglehub · Google Colab
