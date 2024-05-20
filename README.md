# Planning-tpFinal
Repositorio creado para resolver el trabajo final de la materia Planning de la MAIE. En el cual se realiza el enmascaramiento con MNDWI de agua/no-agua en el Dique Los Molinos para una fecha dada, luego con dicho recorte se genera un polígono, se recortan las bandas y se calcula en NDVI para el recorte, se utilizan las siguientes fórmulas para Landsat 8:

\[
MNDWI = \frac{Banda 3 \;\;–\;\;Banda 6}{Banda 3 \;\;+\;\; Banda 6}
\]

\[
NDVI = \frac{Banda 5 \;\;–\;\; Banda 4}{Banda 5 \;\;+\;\; Banda 4}
\]

Previo se realiza un preprocesamiento de los datos, según la tabla de la banda de calidad **QA_PIXEL**, dicha tabla se encuentra en la página 13 del manual: https://d9-wret.s3.us-west-2.amazonaws.com/assets/palladium/production/s3fs-public/media/files/LSDS-1619_Landsat8-9-Collection2-Level2-Science-Product-Guide-v5.pdf

Quedándonos con los datos que no son rellenados, y no poseen ningún tipo de nubes, es decir:

+ Bit 0 = 0 $\to$ Sin datos rellenados
+ Bit 2 = 0 $\to$ Sin nubes Cirrus
+ Bit 3 = 0 $\to$ Sin nubes
+ Bit 4 = 0 $\to$ Sin sombras de nubes

## 1) Instalar environment
A partir del archivo MAIE-Escobares-env.yml instalar el ambiente de trabajo (1.1 GB de descarga), para ello utilizar:

```bash
# En Conda:
conda env create --name MAIE-Escobares-env --file=MAIE-Escobares-env.yml

# En Micromamba:
micromamba env create -n MAIE-Escobares-env -f MAIE-Escobares-env.yaml
```

## 2) Abrir Notebook
Abrir notebook en VS Code (o cualquier IDE) y abrir el ambiente creado anteriormente


## Autor
Escobares Cristhian Daniel $\to$ cristhian.escobares@ig.edu.ar