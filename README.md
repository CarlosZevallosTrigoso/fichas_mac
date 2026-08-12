# Fichas MAC

Fichas de "objeto museal" de obras para el **Museo de Arte Contemporáneo de Lima (MAC-Lima)**. Cada ficha es un documento Word (`.docx`) en la carpeta [`fichas/`](fichas/) con una tabla de catalogación.

## Estructura de cada ficha

| Campo | Descripción |
|---|---|
| Título | Título de la obra |
| Autor/a | Artista |
| Año | Año o rango de años |
| Imagen(es) | Imagen(es) de la obra (embebidas en el documento) |
| Técnica/Materiales | Técnica y materiales |
| Medidas | Dimensiones |
| Colección | Colección a la que pertenece |
| Contacto (Para coordinaciones) | Datos de contacto |
| Observaciones (montaje u otros) | Notas de montaje u otras |

## Inventario

El archivo [`INVENTARIO.csv`](INVENTARIO.csv) es el índice de todas las fichas. Se genera a partir de los `.docx` e incluye, además de los campos de la tabla: número de imágenes, estado (derivado del nombre de archivo) y qué campos clave faltan por completar. Se abre directo en Excel o Google Sheets.

### Resumen (72 fichas)

**Por estado** (según la etiqueta en el nombre del archivo):

| Estado | Fichas |
|---|---|
| Aceptada | 31 |
| Sin estado en el nombre | 29 |
| Por buscar | 6 |
| Por definir | 2 |
| Por consultar | 1 |
| Contactar | 1 |
| Obra inédita | 1 |
| Por evaluar | 1 |

**Completitud:**

- **45 de 72** fichas tienen todos los campos clave (título, año, técnica, medidas y colección).
- **27 fichas** tienen algún campo clave pendiente — ver la columna *Campos faltantes* del inventario.
- **1 ficha sin imagen**: `Elvia Paucar_Mijail.docx`.

### Fichas con campos pendientes

Ordenadas por autor. La columna indica qué falta.

| Autor/a | Título | Campos faltantes |
|---|---|---|
| Agustina Valera y Oliver Agustín | Chomo | Año, Técnica, Medidas, Colección |
| Alberto Cassari | Tiras | Técnica, Medidas |
| Alberto Guzmán | — | Título, Año, Técnica, Medidas |
| Antonio Sulca | — | Título, Año, Técnica, Medidas, Colección |
| Chonon Bensho | — | Título, Año, Técnica, Medidas |
| Edilberto Mérida | — | Título, Año, Medidas |
| Elvia Paucar | — | Título, Año, Técnica, Medidas, Colección |
| Gastón Garreaud | Músico | Técnica |
| Gastón Garreaud | — | Título, Año, Medidas |
| Gedión Fernández | — | Título, Año, Técnica, Medidas, Colección |
| Gonzalo Hernández | — | Título, Año, Técnica |
| Iliana Scheggia | Nido | Año |
| Ivet Salazar | De la serie "Fósiles" | Medidas |
| Joaquín López Antay | — | Título, Técnica |
| Jorge Cabieses | — | Título |
| Juan Javier Salazar | — | Título, Año, Medidas |
| Mamerto Sánchez | — | Título, Año, Técnica, Medidas |
| Miguel Aguirre Vega | Te amo de más a veces | Medidas |
| Noris Vásquez Linares | — | Título, Año, Técnica |
| Olga Engelmann | — | Título, Año, Técnica, Medidas |
| Paloma Álvarez | Puriypa purinan – Avenida del caminar | Año, Técnica |
| Rocío Gómez | Una tierra exótica | Año |
| Santiago Rojas | — | Título, Año, Técnica, Medidas |
| Sonia Praguer | Grieta II | Medidas |
| Susana Torres | Autorretrato | Año, Técnica, Medidas |
| Teófilo Araujo | — | Título, Año, Técnica, Medidas |
| Víctor Delfín | — | Título, Año, Técnica, Medidas |

## Convención de nombres de archivo

Los nombres siguen el patrón `Autor_Nota.docx`, donde la nota suele indicar el estado o la colección (`_Aceptó`, `_BUSCAR`, `_Por definir`, `_Coleccion ...`). La convención no es del todo uniforme (acentos y espacios varían), por lo que el estado en el inventario se normaliza automáticamente.

## Regenerar el inventario

El inventario se puede regenerar leyendo las fichas con [`python-docx`](https://python-docx.readthedocs.io/). El script recorre cada `.docx`, extrae la tabla, cuenta las imágenes embebidas y deriva el estado a partir del nombre del archivo.
