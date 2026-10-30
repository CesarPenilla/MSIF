# MSIF
Modelo de Susceptibilidad a Incendios Forestales RFR-AHP

# ZONIFICACIÓN DE LA SUSCEPTIBILIDAD A INCENDIOS FORESTALES EN VICHADA (COLOMBIA), EMPLEANDO MODELACIÓN MULTICRITERIO Y APRENDIZAJE AUTOMÁTICO BAJO ENTORNOS SIG

Este repositorio contiene el código fuente completo, los flujos metodológicos y las instrucciones necesarias para la replicación del entorno computacional utilizado en esta investigación. Todo el procesamiento geoespacial se centraliza mediante la API de Python de **Google Earth Engine (GEE)** y se ejecuta sobre entornos **Google Colab**.

---

## 📋 Requisitos Previos para Evaluadores y Jurados

Para garantizar la ejecución exitosa del código sin depender de configuraciones locales o del autor, los revisores deben cumplir con un único requisito:

*   **Cuenta activa en Google Earth Engine:** Debe contar con una cuenta de Google con permisos activos para usar Earth Engine. Si no dispone de una, puede dar de alta su cuenta institucional o personal de forma gratuita e inmediata en [earthengine.google.com](https://google.com).

---

## 🚀 Instrucciones de Ejecución (Paso a Paso)

El flujo de trabajo ha sido diseñado para ser completamente autónomo y no requiere la descarga de archivos locales a su computadora.

1.  **Abrir el Entorno de Ejecución:**
    Haga clic en el siguiente botón digital oficial para desplegar el cuaderno de código directamente en la plataforma en la nube:
    
    [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://google.comCesarPenilla/MSIF/blob/main/TesisMSIF.ipynb)

2.  **Ejecución Completa del Algoritmo:**
    Una vez abierto el cuaderno en Google Colab, diríjase al menú superior y seleccione:
    **Entorno de ejecución** > **Ejecutar todas** (o presione `Ctrl + F9`).

3.  **Flujo de Autenticación de Terceros (OAuth):**
    Cuando el algoritmo ejecute la función `inicializar_entorno_gee()`, Google Colab desplegará una interfaz nativa pidiendo autorización. 
    *   Haga clic en el enlace de inicio de sesión provisto en la celda.
    *   Seleccione su cuenta de Google habilitada en GEE.
    *   Copie el token de acceso generado y péguelo en la casilla de Colab (o acepte la ventana de diálogo según la versión de su navegador).

---

## 📦 Insumos y Datos del Proyecto (Assets Públicos)

En cumplimiento de los principios de transparencia de la investigación, los **4 Shapefiles oficiales** para la delimitación espacial del área de estudio han sido configurados con **permisos de lectura pública globales ("Anyone can read")**. 

El script consumirá estos vectores de forma directa desde los servidores de Google mediante las siguientes direcciones de almacenamiento virtual:

*   **Límite Departamental (Dominio Ω):** `projects/tesismsif/assets/Departamento_Vichada_IGAC`
*   **Límite Municipal (Sub-Dominios):** `projects/tesismsif/assets/Municipios_Vichada_IGAC`
*   **Distancia a vías:** `projects/tesismsif/assets/GRIP4_Vias_Vichada`
*   **Distancia a ríos:** `projects/tesismsif/assets/HydroSHEDS_Rios_Vichada`

---

## 🛠️ Arquitectura del Código y Mitigación de Bloqueos

El código fuente incluye adaptaciones estructurales específicas para procesos de auditoría y revisión académica:

*   **Procesamiento y Renderizado Inmediato (Al Vuelo):** Las colecciones e imágenes satelitales (como el histórico de áreas quemadas `MODIS/061/MCD64A1`) se filtran, enmascaran por calidad (`QA == 3`) y se proyectan directamente en memoria virtual sobre mapas interactivos de `geemap`.
*   **Modo de Revisión Protegido:** El parámetro `GENERAR_ARCHIVOS_FISICOS` está configurado por defecto en `False`. Esto previene fallos o detenciones del código por la falta de carpetas o permisos de escritura en las cuentas de los jurados, permitiendo que el lienzo cartográfico interactivo se genere en tiempo real de manera limpia.

---

## 📂 Estructura del Repositorio

```text
├── TesisMSIF.ipynb        # Código fuente estructurado y documentado en Python.
├── README.md              # Este archivo de instrucciones de réplica.
```
