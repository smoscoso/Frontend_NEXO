# NEXO ODC — Versión final

**Del texto al conocimiento: análisis semántico con IA**  
Universidad de Cundinamarca · Especialización en Inteligencia Artificial · 2026

Este proyecto integra **Angular + FastAPI + modelos supervisados de PLN**. Los videos de NEXO son **archivos estáticos aportados por el autor**: la aplicación **no descarga, sintetiza ni genera voces o videos**, ni durante la instalación ni al iniciar.

## Requisitos

- **Node.js 22** y npm.
- **Python 3.11, 3.12 o 3.13**, con pip y soporte de entornos virtuales.
- Conexión a internet únicamente para instalar inicialmente las dependencias npm y Python, si todavía no están presentes.

## Iniciar el proyecto

En una terminal abierta en la carpeta principal:

```bash
npm install
npm start
```

Abre **http://localhost:4200**.

`npm start` inicia **FastAPI y Angular automáticamente**. En la primera ejecución puede crear el entorno virtual del backend e instalar dependencias de Python. **En ningún momento genera ni convierte videos.**


## Estructura

```text
.
├── src/                     Frontend Angular, módulos, evaluaciones y guiones
├── public/assets/nexo/      Imágenes y tus videos MP4 (con subtítulos opcionales)
├── backend/app/             API FastAPI y servicios de PLN
├── backend/model_artifacts/ Modelos supervisados ya entrenados
├── backend/dataset/         Conjunto de datos y ejemplos reservados
├── backend/training/        Código académico de entrenamiento PLN (no se ejecuta al iniciar)
├── scripts/start.cjs        Inicia frontend y backend (sin síntesis de voz)
├── package.json
└── README.md
```

## Funcionalidad

- 17 pantallas, 8 módulos, actividades interactivas, simulador de texto libre y evaluación final.
- 20 referencias académicas seleccionadas.
- Extracción lingüística con spaCy y tres clasificadores previamente entrenados para analizar tema, tipo y carácter de las necesidades.
- La interpretación de un texto puede ser incierta. La interfaz permite revisar evidencia y abstenerse de presentar una necesidad no suficientemente respaldada.
- No utiliza una base de datos de servidor.

## API y pruebas

Con el proyecto iniciado, la documentación Swagger se encuentra en **http://127.0.0.1:8765/docs**. El frontend se conecta a la API mediante `proxy.conf.json`.

Pruebas del backend:

```bash
npm run test:backend
```

Comprobaciones estáticas:

```bash
npm run check:content
npm run check:assets
```
