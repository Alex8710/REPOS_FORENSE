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

## 2. Guarde la metadata en diferentes formatos (HTML, txt y csv ) para su futuro análisis.

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

**Descripción:**

Estos comandos guardarán la metadata en archivos con las extensiones correspondientes para su análisis futuro.


## 3. Modifique los datos de geo-posición con las coordenadas del Planetario de Bogotá.

### Paso 1: Verificar Metadatos Iniciales

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\imagenExifTool.jpeg"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : imagenExifTool.jpeg
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 257 kB
Zone Identifier                 : Exists
File Modification Date/Time     : 2024:08:28 15:28:31-05:00
File Access Date/Time           : 2024:08:28 15:28:32-05:00
File Creation Date/Time         : 2024:08:28 15:28:31-05:00
File Permissions                : -rw-rw-rw-
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Image Width                     : 3840
Image Height                    : 2160
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 3840x2160
Megapixels                      : 8.3
```

### Paso 2: insertar los datos de ubicacion en la imágen

**Comando usado:**

```shell
.\exiftool.exe -GPSLatitude=4.6097 -GPSLongitude=-74.0817 -GPSLatitudeRef=N -GPSLongitudeRef=W "C:\Users\CDTi Laboratorios\Downloads\imagenExifTool.jpg"
```
### Paso 3: Verificar Metadatos

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\imagenExifTool.jpeg"
```
**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : imagenExifTool.jpeg
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 257 kB
File Modification Date/Time     : 2024:08:28 15:31:21-05:00
File Access Date/Time           : 2024:08:28 15:31:21-05:00
File Creation Date/Time         : 2024:08:28 15:28:31-05:00
File Permissions                : -rw-rw-rw-
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
X Resolution                    : 1
Y Resolution                    : 1
Resolution Unit                 : None
Y Cb Cr Positioning             : Centered
GPS Version ID                  : 2.3.0.0
GPS Latitude Ref                : North
GPS Longitude Ref               : West
Image Width                     : 3840
Image Height                    : 2160
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 3840x2160
Megapixels                      : 8.3
GPS Latitude                    : 4 deg 0' 0.00" N
GPS Longitude                   : 74 deg 0' 0.00" W
GPS Position                    : 4 deg 0' 0.00" N, 74 deg 0' 0.00" W
```

**Descripción:**

Estos comandos permitiran observar el estado previo del archivo de imagen, luego insertarán la metadata de ubicacion y finalmente se validaran los metadatos insertados.

## 4. Cambie el copyrigth como propiedad para el Pato Donald.

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

### Paso2: Insertar los metadatos de Copyright

**Comando Usado:**

```shell
.\exiftool.exe -Copyright="Pato Donald" "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf"
```

### Paso 3: Verificar Metadatos

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\Lboratorio_METADATA_JON.pdf"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : Lboratorio_METADATA_JON.pdf
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 309 kB
File Modification Date/Time     : 2024:08:28 15:46:52-05:00
File Access Date/Time           : 2024:08:28 15:46:53-05:00
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
XMP Toolkit                     : Image::ExifTool 12.93
Copyright                       : Pato Donald
```

**Descripción:**

Estos comandos permitiran observar el estado previo del archivo del archivo para luego insertar la metadata de copyright.


## 5. Extraer la miniatura de una imagen (esto debe estar habilitado en la captura de la misma, caso contrario no es posible).

### Paso 1: Verificar Metadatos Iniciales

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\SampleImage.jpg"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : SampleImage.jpg
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 51 kB
Zone Identifier                 : Exists
File Modification Date/Time     : 2024:08:28 17:13:24-05:00
File Access Date/Time           : 2024:08:28 17:13:46-05:00
File Creation Date/Time         : 2024:08:28 17:13:23-05:00
File Permissions                : -rw-rw-rw-
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Exif Byte Order                 : Big-endian (Motorola, MM)
Orientation                     : Horizontal (normal)
X Resolution                    : 300
Y Resolution                    : 300
Resolution Unit                 : inches
Software                        : Adobe Photoshop CS5 (12.0x20100115 [20100115.m.998 2010/01/15:02:00:00 cutoff; m branch])  Windows
Modify Date                     : 2017:09:11 22:15:46
Color Space                     : Uncalibrated
Exif Image Width                : 300
Exif Image Height               : 300
Compression                     : JPEG (old-style)
Thumbnail Offset                : 386
Thumbnail Length                : 4083
Current IPTC Digest             : f39bf9c2ed9ba38e7734dce08cff959a
Coded Character Set             : UTF8
Application Record Version      : 57540
IPTC Digest                     : f39bf9c2ed9ba38e7734dce08cff959a
Displayed Units X               : inches
Displayed Units Y               : inches
Print Style                     : Centered
Print Position                  : 0 0
Print Scale                     : 1
Global Angle                    : 30
Global Altitude                 : 30
URL List                        :
Slices Group Name               : background-2739196 - Copy
Num Slices                      : 1
Pixel Aspect Ratio              : 1
Photoshop Thumbnail             : (Binary data 4083 bytes, use -b option to extract)
Has Real Merged Data            : Yes
Writer Name                     : Adobe Photoshop
Reader Name                     : Adobe Photoshop CS5
Photoshop Quality               : 11
Photoshop Format                : Standard
XMP Toolkit                     : Adobe XMP Core 5.0-c060 61.134342, 2010/01/10-18:06:43
Creator Tool                    : Adobe Photoshop CS5 (12.0x20100115 [20100115.m.998 2010/01/15:02:00:00 cutoff; m branch])  Windows
Create Date                     : 2017:09:11 16:40:06+05:30
Metadata Date                   : 2017:09:11 22:15:46+05:30
Format                          : image/jpeg
Color Mode                      : RGB
Instance ID                     : xmp.iid:2CA293A81097E7118A54A5FD56B2552F
Document ID                     : xmp.did:2CA293A81097E7118A54A5FD56B2552F
Original Document ID            : xmp.did:2CA293A81097E7118A54A5FD56B2552F
History Action                  : saved
History Instance ID             : xmp.iid:2CA293A81097E7118A54A5FD56B2552F
History When                    : 2017:09:11 22:15:46+05:30
History Software Agent          : Adobe Photoshop CS5 (12.0x20100115 [20100115.m.998 2010/01/15:02:00:00 cutoff; m branch])  Windows
History Changed                 : /
DCT Encode Version              : 100
APP14 Flags 0                   : [14]
APP14 Flags 1                   : (none)
Color Transform                 : YCbCr
Image Width                     : 300
Image Height                    : 300
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:4 (1 1)
Image Size                      : 300x300
Megapixels                      : 0.090
Thumbnail Image                 : (Binary data 4083 bytes, use -b option to extract)
```

### Paso 2: Extraer Imagen

**Comando Usado:**

```shell
.\exiftool.exe -b -ThumbnailImage "C:\Users\CDTi Laboratorios\Downloads\SampleImage.jpg" > "C:\Users\CDTi Laboratorios\Downloads\ExtractedImage.jpg"
```

### Paso 3: Verificar Imagen Extraida

**Comando Usado:**

```shell
.\exiftool.exe "C:\Users\CDTi Laboratorios\Downloads\ExtractedImage.jpg"
```

**Resultado:**

```plaintext
ExifTool Version Number         : 12.93
File Name                       : ExtractedImage.jpg
Directory                       : C:/Users/CDTi Laboratorios/Downloads
File Size                       : 8.3 kB
File Modification Date/Time     : 2024:08:28 17:15:13-05:00
File Access Date/Time           : 2024:08:28 17:15:19-05:00
File Creation Date/Time         : 2024:08:28 17:15:13-05:00
File Permissions                : -rw-rw-rw-
File Type                       : TXT
File Type Extension             : txt
MIME Type                       : text/plain
MIME Encoding                   : utf-16le
Byte Order Mark                 : Yes
Newlines                        : Windows CRLF
```

