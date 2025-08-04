# Análisis de Datos del Titanic con Pandas y Seaborn

Este cuaderno realiza un análisis exploratorio de los datos del Titanic utilizando Python, Pandas y Seaborn. El objetivo es entender las características de los pasajeros y explorar factores relacionados con la supervivencia.

## Estructura del análisis

1. **Carga de datos**
   - Se utiliza `pandas` para leer el archivo `titanic.csv` y cargarlo en un DataFrame llamado `df0`.

2. **Exploración inicial**
   - Visualización de las primeras filas con `df0.head()`.
   - Inspección de la forma del DataFrame (`df0.shape`) y tipos de datos (`df0.info()`).

3. **Selección y filtrado de columnas**
   - Extracción de columnas relevantes: Edad (`Age`), Género (`Sex`), Clase (`Pclass`).
   - Creación de un DataFrame filtrado: `df_age_sex_pclass`.

4. **Estadísticas descriptivas**
   - Resumen estadístico de las columnas seleccionadas con `describe()`.

5. **Filtrado avanzado**
   - Pasajeros mujeres mayores de 30 años.
   - Pasajeros de las clases 1 y 2.
   - Pasajeros con edad no nula.
   - Nombres de los pasajeros mayores de 35 años.

6. **Transformaciones**
   - Creación de una nueva columna con el doble de la edad (`Age_x2`).
   - Copia del DataFrame original para análisis adicionales.

7. **Visualización**
   - Histogramas y gráficos de conteo para analizar la supervivencia y su relación con el género.

## Principales comandos utilizados

- Carga de datos:
  ```python
  df0 = pd.read_csv('titanic.csv')
  ```
- Selección de columnas:
  ```python
  df0[['Age', 'Sex', 'Pclass']]
  ```
- Filtrado por condiciones:
  ```python
  df0[df0['Age'] > 35]['Name']
  df0[df0['Pclass'].isin([1, 2])]
  ```
- Estadísticas descriptivas:
  ```python
  df_age_sex_pclass.describe()
  ```
- Visualización:
  ```python
  sns.histplot(df1['Survived'], kde=False, bins=2)
  sns.countplot(x='Survived', data=df1)
  sns.catplot(x='Sex', col='Survived', data=df1, kind='count')
  ```

## Requisitos

- Python 3.12+
- Pandas
- NumPy
- Matplotlib
- Seaborn

Instala los requisitos con:
```sh
pip install -r requirements.txt
```

## Uso

1. Descarga el archivo `titanic.csv` y colócalo en la misma carpeta que el cuaderno.
2. Abre el cuaderno `titanic.ipynb` en VSCode o Jupyter.
3. Ejecuta las celdas para reproducir el análisis y las visualizaciones.

---

Este análisis te permitirá explorar los datos del Titanic y entender mejor los factores que influyeron en la supervivencia de los pasajeros.