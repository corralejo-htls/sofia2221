Notas:
Todos los campos son opcionales. Puedes enviar solo los que desees actualizar. Los campos que no se incluyan no se verán afectados.
Si no deseas actualizar un campo, simplemente elimínalo del objeto data.
Los valores dentro de los objetos que contienen varias traducciones (name, address, longDescription, etc.) deben tener el idioma en como primero.



| **Campo**               | **Tipo**                | **Obligatorio** | **Descripción**                                                                             |
| ----------------------- | ----------------------- | --------------- | ------------------------------------------------------------------------------------------- |
| `name`                  | object (i18n)           | No              | Nombre del alojamiento en varios idiomas.                                                   |
| `address`               | object (i18n)           | No              | Dirección del alojamiento en varios idiomas.                                                |
| `rating`                | number                  | No              | Puntuación del alojamiento (0 - 10).                                                        |
| `geoPosition.latitude`  | number                  | No              | Latitud geográfica.                                                                         |
| `geoPosition.longitude` | number                  | No              | Longitud geográfica.                                                                        |
| `services`              | object → array → object | No              | Servicios ofrecidos por el alojamiento, en varios idiomas.                                  |
| `conditions`            | object → array          | No              | Condiciones para el alojamiento (ej. check-in, check-out), en varios idiomas.               |
| `toConsider`            | object (i18n)           | No              | Información adicional a considerar por los huéspedes, en varios idiomas.                    |
| `images`                | array[string]           | No              | URLs de las imágenes del alojamiento.                                                       |
| `scoreReview`           | number                  | No              | Promedio de puntuación de los comentarios.                                                  |
| `scoreReviewBasedOn`    | number | null           | No              | Número de comentarios utilizados para calcular la puntuación.                               |
| `roomsQuantity`         | number                  | No              | Cantidad de habitaciones disponibles.                                                       |
| `accommodationType`     | string                  | No              | Tipo de alojamiento (e.g. Hotel, Villa, Hostal).                                            |
| `priceRange`            | string | null           | No              | Rango de precios.                                                                           |
| `extraInfo`             | string | null           | No              | Información adicional, si es necesario.                                                     |
| `longDescription`       | object (i18n)           | No              | Descripción larga del alojamiento, en varios idiomas.                                       |
| `reviews`               | object (i18n)           | No              | Comentarios de los huéspedes, en varios idiomas.                                            |
| `categoryScoreReview`   | object (i18n)           | No              | Puntuación detallada por categorías (ej. limpieza, confort, ubicación), en varios idiomas.  |
| `rooms`                 | object (i18n)           | No              | Detalles de las habitaciones (nombre, capacidad, descripción, imágenes), en varios idiomas. |
| `nearbyPlaces`          | object (i18n)           | No              | Lugares cercanos y su distancia, en varios idiomas.                                         |
| `guestValues`           | object (i18n)           | No              | Preguntas frecuentes de los huéspedes, en varios idiomas.                                   |
| `seoDescription`        | object (i18n)           | No              | Descripción SEO del alojamiento, en varios idiomas.                                         |
| `keywords`              | object (i18n)           | No              | Palabras clave SEO, en varios idiomas.                                                      |

