# TP Especial – Fundamentos de la Ciencia de Datos: Inside Airbnb Buenos Aires 2026

Análisis exploratorio, limpieza de datos y validación de hipótesis sobre los anuncios de Airbnb en la Ciudad Autónoma de Buenos Aires, a partir de los datos públicos de [Inside Airbnb](https://insideairbnb.com/get-the-data/).

## Integrantes (Grupo 6)
- Galvan, Juan Bautista
- Pourtau, Jeronimo
- Ramallo, Franco

## Contenido del repositorio
| Archivo | Descripción |
|---|---|
| `entrega.ipynb` | Notebook con todo el análisis, organizada en secciones |
| `informe.pdf` | Informe con los principales hallazgos y conclusiones |
| `listings.csv.gz` | Datos de Inside Airbnb (listings de Buenos Aires, 23 de septiembre de 2026), sin descomprimir |
| `requirements.txt` | Dependencias de Python con sus versiones |
| `README.md` | Este archivo |

## Requisitos
- Python 3.11 o superior (desarrollado y probado con 3.12.3)
- pip

## Instalación
1. Clonar el repositorio y entrar a la carpeta:
   ```
   git clone https://github.com/Jeronit1/AnalisisDeDatos.git
   cd AnalisisDeDatos
   ```
2. Crear y activar un entorno virtual:
   - Windows (PowerShell):
     ```
     python -m venv .venv
     .venv\Scripts\Activate.ps1
     ```
   - macOS / Linux:
     ```
     python3 -m venv .venv
     source .venv/bin/activate
     ```
3. Instalar las dependencias:
   ```
   pip install -r requirements.txt
   ```

## Ejecución
1. Con el entorno activado, abrir la notebook:
   ```
   jupyter notebook entrega.ipynb
   ```
   (También puede abrirse desde VS Code, eligiendo el kernel del entorno `.venv`.)
2. Ejecutar todas las celdas en orden: menú **Kernel → Restart Kernel and Run All Cells…**

Notas:
- El archivo `listings.csv.gz` debe estar en la misma carpeta que la notebook. No hace falta descomprimirlo: `pandas` lo lee directamente.
- Los resultados son reproducibles: las muestras aleatorias usan `random_state=42`.

## Estructura de la notebook
| Sección | Contenido |
|---|---|
| 1. Análisis exploratorio inicial | Origen de los datos, selección de variables y descripción |
| 2. Limpieza y preparación | Variables binarias, valores faltantes, `amenities`, precio y valores atípicos |
| 3. Distribución de variables | Histogramas (3.1 a 3.4) y correlaciones (3.5) |
| 4. Validación de hipótesis | Hipótesis H1 a H6 (ver tabla) |

| Hipótesis | Enunciado | Técnica |
|---|---|---|
| H1 | La ocupación media anual es inferior al 45 % del año | t para una media |
| H2 | Los Superhost tienen mayor mediana de ocupación | Prueba de la mediana |
| H3 | A igual capacidad, Superhost y servicios se asocian con mayor ingreso | Regresión lineal múltiple |
| H4 (a) | Más del 60 % de la oferta es de anfitriones con varias propiedades | t para una media (proporción) |
| H5 (b) | Un espacio entero cuesta más del doble que una habitación privada | t de Welch |
| H6 (c) | A igual capacidad, más independencia se asocia con mayor precio | Regresión lineal múltiple |