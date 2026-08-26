# El impacto de la IA en la fuerza laboral

> **Mentoría M09** · Diplomatura en Ciencia de Datos · FAMAF – UNC

La Inteligencia Artificial promete revolucionarlo todo. Todos los días aparecen noticias sobre empresas que automatizan procesos, disparan su productividad o redefinen por completo la forma en que trabajan. Al mismo tiempo abundan las predicciones sobre empleos que desaparecerán, profesiones que cambiarán de raíz y habilidades que serán indispensables.

**Más allá del hype: ¿qué muestran los datos?**

---

## El equipo

| Integrante | Contacto |
|---|---|
| **Basel Abdel Masih** | [basel.masih@mi.unc.edu.ar](mailto:basel.masih@mi.unc.edu.ar) |
| **Juan Pablo Listte** | [juanpilistte@gmail.com](mailto:juanpilistte@gmail.com) |
| **Mario Lanteri** | [mario.lanteri@mi.unc.edu.ar](mailto:mario.lanteri@mi.unc.edu.ar) |
| **Franco Cippitelli** | [frann_cippi@hotmail.com](mailto:frann_cippi@hotmail.com) |

Somos cuatro estudiantes de la Diplomatura en Ciencia de Datos de FAMAF. Este repositorio reúne el trabajo que vamos desarrollando a lo largo de los prácticos de la mentoría: desde la exploración inicial del dataset hasta los modelos predictivos, incluyendo el código, las visualizaciones y las decisiones metodológicas que tomamos en el camino.

---

## De qué se trata el proyecto

Trabajamos sobre un dataset de aproximadamente **150.000 registros** que combina, en un mismo lugar, cuatro dimensiones que rara vez se miran juntas:

- **Adopción de IA** — cuánto, cómo y hace cuánto la usan las organizaciones
- **Características organizacionales** — tamaño, antigüedad, industria, país
- **Indicadores económicos** — productividad, ingresos, reducción de costos
- **Impacto laboral** — empleos desplazados, empleos creados, personas reentrenadas

> El dataset fue construido a partir de patrones observados en reportes y estudios sobre adopción tecnológica, transformación digital, productividad e impacto laboral. Es decir: **son datos sintéticos diseñados para representar escenarios organizacionales realistas a escala global**, no un relevamiento empírico. Lo tenemos presente al momento de interpretar resultados y de sacar conclusiones sobre el mundo real.

Lo interesante del proyecto es que **no hay una única pregunta ni una única respuesta correcta**. El dataset es lo suficientemente rico como para sostener varias líneas de investigación en paralelo, y buena parte del desafío está en formular buenas preguntas, encontrar evidencia sólida y construir argumentos que se sostengan con datos.

---

## El dataset

Tres archivos que se articulan entre sí por `industry` y por `country`:

| Archivo | Filas × Cols | Granularidad | Qué contiene |
|---|---|---|---|
| `ai_company_adoption.csv` | 150.025 × 43 | Una fila por **empresa y trimestre** | Núcleo del análisis: encuestas con adopción de IA, estructura de la empresa, gobernanza, resultados económicos e impacto laboral |
| `ai_industry_summary.csv` | 9 × 8 | Una fila por **industria** | Promedios sectoriales de adopción, madurez, fallas, empleo y satisfacción |
| `country_ai_index.csv` | 30 × 8 | Una fila por **país** | Contexto macro: PBI per cápita, penetración de internet, madurez digital, patentes de IA, investigadores y política regulatoria |

**Estructura del archivo principal:** 10.025 empresas distintas, seguidas a lo largo de hasta 16 trimestres (2023–2026, Q1 a Q4), repartidas en **9 industrias**, **30 países** y **6 regiones**. De las 43 columnas, 29 son numéricas y 14 categóricas.

Las variables del archivo principal las agrupamos en siete bloques según su rol: identificación, contexto geográfico/sectorial, estructura de la empresa, adopción de IA, gobernanza y riesgo, impacto en las personas e impacto en el negocio. El detalle está en la sección 1.4 de la notebook.

Fuente original de los datos: [carolinapepe/diplodatos-ai-impact-workforce](https://github.com/carolinapepe/diplodatos-ai-impact-workforce)

---

## Preguntas que queremos responder

**Sobre el mapa de la adopción**
- ¿Qué industrias están ganando la carrera de la IA?
- ¿Podemos identificar distintos perfiles de adopción tecnológica?
- ¿Qué impulsa (o frena) la transformación tecnológica?

**Sobre el retorno económico**
- ¿La IA realmente aumenta la productividad?
- ¿Alcanza con invertir millones en IA para tener éxito?
- ¿Qué tienen en común las organizaciones que mejor aprovechan la IA?
- ¿Existen recetas para una adopción exitosa de IA?

**Sobre el impacto en el empleo**
- ¿La IA elimina empleos o crea nuevas oportunidades?
- ¿Quiénes corren más riesgo de ser automatizados?

**Sobre la capacidad predictiva**
- ¿Podemos predecir quiénes serán los ganadores de la revolución de la IA?

---

## Hoja de ruta

**1 · Análisis exploratorio y visualización**
Identificar tendencias, relaciones inesperadas y posibles explicaciones detrás de los distintos comportamientos. Visualizaciones, agregaciones, métricas diseñadas ad hoc y storytelling basado en datos.

**2 · Limpieza y preparación**
Tratar los outliers y los valores sin sentido económico que detectamos en la exploración, normalizar las variables de empleo por tamaño de empresa y dejar un dataset a nivel empresa listo para modelar.

**3 · Aprendizaje no supervisado**
Descubrir perfiles ocultos de organizaciones: empresas que lideran la adopción, industrias en plena transformación, sectores donde la IA todavía tiene presencia limitada. ¿Existen distintos caminos hacia una adopción exitosa? ¿Podemos identificar "personalidades" tecnológicas a partir de los datos?

**4 · Modelos predictivos**
Estimar distintos niveles de impacto de la IA y analizar qué variables tienen mayor capacidad explicativa. Feature engineering, selección de variables, validación, interpretabilidad y análisis crítico de resultados.

---

## Estructura del repositorio

```
.
├── notebooks/
│   ├── 01_analisis_exploratorio.ipynb      # Práctico 1 ✅
│   ├── 02_limpieza_y_preparacion.ipynb     # Práctico 2
│   ├── 03_aprendizaje_no_supervisado.ipynb # Práctico 3
│   └── 04_modelos_predictivos.ipynb        # Práctico 4
├── practicos/           # consignas de cada entrega
├── data/
│   ├── raw/             # los 3 CSV originales — NUNCA se modifican
│   └── processed/       # salida de cada notebook (parquet)
├── docs/                # glosario de datos
└── README.md
```

Los notebooks se nombran por **contenido** y no por número de entrega. El prefijo numérico ya da el orden, y el nombre te dice qué hay adentro sin abrirlo; la correspondencia con cada práctico está anotada en el árbol.

**No hay módulos de código aparte.** Todo vive en los notebooks, que son el entregable. Cuando una función se repita dentro de un notebook, se define en una celda de ese mismo notebook: así la decisión queda a la vista de quien lo lee, que es justamente lo que se evalúa.

---

## Puesta en marcha

**Desde Colab** —como trabaja la mayoría del equipo— no hace falta instalar nada: las librerías que usamos ya vienen incluidas. Alcanza con abrir el notebook y correr esta celda primero, para que el repo y los datos procesados estén disponibles:

```python
!git clone https://github.com/Franncippi/Proyecto-mentoria-M09.git
%cd Proyecto-mentoria-M09/notebooks
```

El clon trae **los datos incluidos** (unos 44 MB, mayormente el CSV principal), así que no hay que bajar nada aparte. A partir de ahí todas las rutas relativas funcionan igual que en local.

**En local**, además del clon hace falta tener `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`, `plotly` y `pyarrow`:

```bash
git clone https://github.com/Franncippi/Proyecto-mentoria-M09.git
cd Proyecto-mentoria-M09
pip install pandas numpy scipy matplotlib seaborn plotly pyarrow
```

Y listo: los datos ya vienen en `data/raw/`.

> Los notebooks viven en `notebooks/`, así que las rutas a los datos van con `../`:
> `pd.read_parquet("../data/processed/empresas.parquet")`

---

## Cómo trabajamos

**Cada notebook lee un archivo y escribe un archivo.** Nunca depende de que hayas corrido el anterior en la misma sesión:

```
data/raw/*.csv ──► 01_analisis_exploratorio    (solo lee)
data/raw/*.csv ──► 02_limpieza_y_preparacion ──► data/processed/empresas.parquet
                                                        │
       ┌────────────────────────────────────────────────┘
       ├──► 03_aprendizaje_no_supervisado ──► data/processed/empresas_con_cluster.parquet
       └──► 04_modelos_predictivos
```

Si cambia un criterio de limpieza, se re-corre **solo** el notebook 02 y los demás levantan el archivo nuevo:

```python
# al final del notebook que produce los datos
df.to_parquet("../data/processed/empresas.parquet", index=False)

# al principio del que los consume
df = pd.read_parquet("../data/processed/empresas.parquet")
```

Parquet y no CSV porque conserva los tipos: si no, `survey_year` vuelve como `float64` en cada lectura y hay que arreglarlo de nuevo.

### Qué vive en `data/processed/`

Los datos **derivados**: lo que cada notebook produce después de transformar el crudo. Hoy la carpeta está vacía, y está bien — el notebook 01 solo lee y explora, no genera ningún dataset. Se empieza a llenar en el práctico 2.

---

## Estado actual

**Práctico 1 — Análisis exploratorio y visualización**

[`notebooks/01_analisis_exploratorio.ipynb`](notebooks/01_analisis_exploratorio.ipynb) está organizada siguiendo las cinco consignas del práctico: descripción general del dataset, análisis univariado, análisis bivariado y comparaciones, hipótesis de investigación y conclusiones parciales.

Hallazgos principales hasta acá:

- Las variables de **impacto laboral** son conteos absolutos fuertemente asimétricos a la derecha, y las de **retorno económico** presentan curtosis extremas. Hay depuración y normalización pendientes antes de modelar.
- Las variables económicas concentran entre el **70% y el 88%** de su varianza *dentro* de cada empresa a lo largo de los trimestres, mientras que las de empleo apenas varían un **8%–16%**. Por eso el análisis se agrega a nivel empresa promediando trimestres.
- La **inversión en IA se asocia positivamente** con productividad, reducción de costos y crecimiento de ingresos, tanto a nivel empresa como por industria y por país.
- La relación entre **automatización y empleo no es lineal**: a igual tasa de automatización conviven industrias con saldo neto de empleo positivo y negativo, lo que sugiere que pesa más el *tipo* de tarea automatizada que el volumen.
