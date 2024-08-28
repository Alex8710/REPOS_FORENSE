# Guía de Gestión de Metadatos con ExifTool

## 1. Elimine toda la metadata.

### Paso 1: Verificar Metadatos Iniciales

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : Lboratorio_METADATA_JON.pdf
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 305 kB
Zone Identifier                 : Exists
File Modification Date/Time     : 2024:08:28 14:13:09-05:00
File Access Date/Time           : 2024:08:28 14:36:11-05:00
File Creation Date/Time         : 2024:08:28 14:13:06-05:00
File Permissions                : -rw-rw-rw-
File Type                       : PDF
File Type Extension             : pdf
MIME Type                       : application/pdf
PDF Version                     : 1.7
Linearized                      : No
Page Count                      : 3
Language                        : es
Tagged PDF                      : Yes
XMP Toolkit                     : 3.1-701
Producer                        : Microsoft« Word para Microsoft 365
Creator                         : DHC. JAIDER OSPINA NAVAS
Creator Tool                    : Microsoft« Word para Microsoft 365
Create Date                     : 2024:08:27 11:35:21-05:00
Modify Date                     : 2024:08:27 11:35:21-05:00
Document ID                     : uuid:214403B8-1F9F-4E5D-AF74-28AE1489D07D
Instance ID                     : uuid:214403B8-1F9F-4E5D-AF74-28AE1489D07D
Author                          : DHC. JAIDER OSPINA NAVAS
```

**Descripción:**

Este comando muestra los metadatos actuales del archivo PDF `Lboratorio_METADATA_JON.pdf`. Incluye detalles como la fecha de creación, el autor, y la versión de PDF.

### Paso2: Eliminar Todos los Metadatos

**Comando Usado:**

```shell
.\exiftool.exe -all= "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf"
```

**Resultado:**

```plaintext
Warning: [minor] ExifTool PDF edits are reversible. Deleted tags may be recovered! - C:/Users/CDTi Laboratorios/Downloads/Lboratorio_METADATA_JON.pdf
1 image files updated
```

**Descripción:**

Este comando elimina todos los metadatos del archivo PDF. La advertencia indica que algunos cambios pueden ser reversibles y los tags eliminados pueden ser recuperados.

### Paso 3: Verificar Metadatos Después de la Eliminación

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : Lboratorio_METADATA_JON.pdf
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 306 kB
File Modification Date/Time     : 2024:08:28 14:36:28-05:00
File Access Date/Time           : 2024:08:28 14:36:29-05:00
File Creation Date/Time         : 2024:08:28 14:13:06-05:00
File Permissions                : -rw-rw-rw-
File Type                       : PDF
File Type Extension             : pdf
MIME Type                       : application/pdf
PDF Version                     : 1.7
Linearized                      : No
Page Count                      : 3
Language                        : es
Tagged PDF                      : Yes
```

**Descripción:**

Después de eliminar los metadatos, el archivo PDF aún conserva información básica como el tipo de archivo, tamaño y número de páginas. Los detalles específicos como el autor y la fecha de creación han sido eliminados.

## Guarde la metadata en diferentes formatos (HTML, txt y csv ) para su futuro
análisis.

### Guardar la Metadata en Diferentes Formatos

Para guardar la metadata en diferentes formatos (HTML, TXT, y CSV), utiliza los siguientes comandos:

**TXT:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf" > "C:\Users\CDTi Laboratorios\Downloads\metadata.txt"
```

**HTML:**

```shell
.\exiftool.exe -htmldump "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf" > "C:\Users\CDTi Laboratorios\Downloads\metadata.html"
```

**CSV:**

```shell
.\exiftool.exe -csv "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf" > "C:\Users\CDTi Laboratorios\Downloads\metadata.csv"
```

Estos comandos guardarán la metadata en archivos con las extensiones correspondientes para su análisis futuro.
