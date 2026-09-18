# Código para Validación de Registros de BioModelos

Este repositorio contiene herramientas para la validación y revisión de registros de especies en BioModelos, facilitando la identificación y corrección de posibles inconsistencias en los datos.

## Contenido del Repositorio

- **`codigo_validar_registros.R`**: Script en R que automatiza la validación de registros de especies, verificando la consistencia y calidad de los datos. Este script realiza las siguientes funciones:

  - **Carga de Datos**: Importa los registros desde un archivo CSV especificado por el usuario.
  - **Validación de Campos**: Verifica la presencia y el formato correcto de los campos requeridos, como nombres científicos, coordenadas geográficas y fechas de recolección.
  - **Detección de Duplicados**: Identifica registros duplicados basados en criterios como coordenadas y fecha de recolección.
  - **Verificación de Coordenadas**: Comprueba que las coordenadas geográficas estén dentro de los límites permitidos y no correspondan a ubicaciones improbables.
  - **Generación de Informe**: Produce un informe detallado en formato Excel con los hallazgos de la validación, indicando los registros que requieren corrección.

- **`Plantilla_registros.xlsx`**: Plantilla en Excel que define los campos requeridos y su formato para los registros de especies en BioModelos. Se recomienda usar esta plantilla para estructurar los datos antes de la validación.

## Requisitos

- **R**: Se requiere tener instalado R 4.3.3 o superior para ejecutar el script de validación. Puedes descargarlo desde [CRAN](https://cran.r-project.org/).

- **Paquetes de R**: Asegúrate de tener instalados los siguientes paquetes necesarios para la ejecución del script:

  ```r
  tidyverse >= 2.0.0
  readxl >= 1.4.0
  stringr >= 1.5.0
  lubridate >= 1.9.0
  CoordinateCleaner >= 2.0-20
  sf >= 1.0-0
  janitor >= 2.2.0
  here >= 1.0.0

  ```

## Uso

1. **Preparación de Datos**:  
   - Descargue y llene la plantilla `Plantilla_campos_registros_BioModelos.xlsx`. Complete los datos asegurándose de seguir el formato especificado. Guarde el archivo en **formato CSV, TXT, TSV, XLS o XLSX** para que el script pueda leerlo correctamente.
   - Descargue los registros de GBIF.
   - Al exportar el o los archivos, asegúrese de utilizar la codificación **UTF-8**.
     
2. **Ejecución del Script**:  
   - Abra R o RStudio.  
   - Establezca el directorio de trabajo como aquel que contiene el script `codigo_validar_registros.R` y el archivo con los datos.  
   - Adapte las rutas de archivos, directorio de salida, nombre del grupo temático o taxonómico, nombre del experto (si corresponde) y el valor de la variable GBIF según el origen de los datos.
   - Ejecute el script `codigo_validar_registros.R`.

3. **Revisión de Resultados**:
   - Se generará un informe en formato XLSX que reporta los errores a nivel de campo y nivel de registro, realizando gráficas descriptivas para una mejor comprensión de los errores.
   - Se generará un archivo con los registros originales, y con una única corrección asociada a errores en el campo `occurrenceID`, sobre el cual generar las correcciones necesarias presentadas en el reporte
   - Corrija los errores en la plantilla original y vuelve a ejecutar el script si es necesario.  

## Errores y soluciones

| Error | Causa | Solución |
|-------|-------------|---------|
| Formato de archivo no compatible. Use archivos .csv, .txt, .tsv, .xls o .xlsx. | El archivo ingresado tiene una extensión que no es compatible con el script. | Guarde el archivo como CSV, TXT, TSV, XLS o XLSX y verifique que la extensión corresponda al formato del archivo. |

## 📜 Licencia

Este proyecto está licenciado bajo **MIT License**.  
Consulta [LICENSE](./LICENSE) para más información.

---

## 📖 Citación
El detalle de las citas utilizadas en el proyecto está en el siguiente archivo:

- [CITATION.cff](./CITATION.cff)

Si usa este software en su investigación, por favor cítelo así:

```bibtex
@software{validacion_registros_biomodelos,
  author       = {Otero, Nathalia and Leuro, Nerieth},
  title        = {Código para la validación de registros BioModelos},
  year         = {2026},
  publisher    = {GitHub},
  version      = {2.0.0},
  url          = {https://github.com/Laur8629/codigo-revision-registros},
  note         = {Archivo principal: codigo_validar_registros.R}
}

```

## Autores
Gerencia de Información Científica - Dirección de conocimiento - Instituto de Investigación de Recursos Biológicos Alexander von Humboldt - Colombia

Nathalia Otero Santamaría - [nathalia-otero](./https://github.com/nathalia-otero)

Nerieth Goretti Leuro Robles - [goreleuro94](./(https://github.com/goreleuro94))
