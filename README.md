# Mejora de Calidad de Videos con IA.

Este proyecto utiliza inteligencia artificial para mejorar la calidad de videos, enfocándose en la restauración y superresolución de imágenes dentro de los fotogramas. El proceso se basa en el modelo GFPGAN (Generative Facial Prior Generative Adversarial Network), desarrollado por TencentARC, junto con otras herramientas como Real-ESRGAN para la mejora de la calidad general del video.

El flujo de trabajo incluye la clonación del repositorio GFPGAN, la instalación de dependencias necesarias, la descarga de modelos preentrenados, y la aplicación de técnicas de mejora de calidad a los videos cargados. El resultado final es un video con una calidad significativamente mejorada, especialmente en la nitidez y detalles de las caras.

---
# **Características Principales**
**Restauración de Caras con GFPGAN:**
- Utiliza un modelo preentrenado de GFPGAN para mejorar la calidad de las caras en los fotogramas del video.
- Aplica técnicas de superresolución para aumentar la nitidez y detalles.

**Mejora General del Video con Real-ESRGAN:**
- Mejora la calidad general del video mediante el uso de Real-ESRGAN, un modelo de superresolución que funciona bien para todo tipo de contenido.

**Procesamiento Automático:**
- Convierte videos en fotogramas, aplica la mejora de calidad a cada fotograma, y luego recompone el video en formato MP4.
- Elimina archivos temporales automáticamente para optimizar el uso de espacio.

**Compatibilidad con Google Colab:**
- El código está diseñado para ejecutarse en Google Colab, lo que permite aprovechar la potencia de las GPUs gratuitas para acelerar el procesamiento.
---
# **Requisitos**
- Python 3.x

**Dependencias:**
- basicsr
- facexlib
- realesrgan
- opencv-python
- ffmpeg (para la conversión de formatos de video)

**Modelo Preentrenado:**
- GFPGANCleanv1-NoCE-C2.pth (descargado automáticamente en el script).

---

# **Instrucciones de Uso**
**Clonar el Repositorio:**
 - Clona el repositorio GFPGAN y navega al directorio del proyecto.
```bash
!git clone https://github.com/TencentARC/GFPGAN.git
%cd GFPGAN
```
**Instalar Dependencias:**
- Instala las bibliotecas necesarias y configura el entorno.
```bash
!pip install basicsr facexlib realesrgan
!pip install -r requirements.txt
!python setup.py develop
```
**Descargar el Modelo Preentrenado:**
- Descarga el modelo GFPGAN preentrenado.
```bash
!wget https://github.com/TencentARC/GFPGAN/releases/download/v0.2.0/GFPGANCleanv1-NoCE-C2.pth -P experiments/pretrained_models
```
**Cargar y Procesar Videos:**
- Sube tus videos a la carpeta videos y ejecuta el script para mejorar su calidad.
- El script convierte el video en fotogramas, aplica la mejora de calidad, y recompone el video en formato MP4.

**Resultados:**
- Los videos mejorados se guardan en la carpeta results_mp4_videos.
---
# **Estructura del Proyecto**
- **upload/:** Carpeta temporal para almacenar fotogramas extraídos del video.
- **results/:** Carpeta para almacenar fotogramas mejorados.
- **videos/:** Carpeta para cargar los videos originales.
- **results_videos/:** Carpeta para videos mejorados en formato AVI.
- **results_mp4_videos/:** Carpeta final para videos mejorados en formato MP4.
---
# **Ejemplo de Uso**
- Sube un video a la carpeta videos.
- Ejecuta el script principal.
- El video mejorado estará disponible en results_mp4_videos.
---
# **Tecnologías Utilizadas**
- **GFPGAN:** Para la restauración de caras.
- **Real-ESRGAN:** Para la superresolución general del video.
- **OpenCV:** Para la manipulación de fotogramas y conversión de videos.
- **FFmpeg:** Para la conversión de formatos de video.
---
**Contribuciones**
- ¡Las contribuciones son bienvenidas! Si deseas mejorar el proyecto, por favor abre un issue o envía un pull request.
---
**Licencia**
- Este proyecto está bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.
