# 📘 MANUAL DE USO – API DE ACTUALIZACIÓN DE CONTENIDO

## 1. Objetivo de la API

Esta API permite **actualizar completamente** la información de un alojamiento (hotel, villa, hostal, etc.), con soporte **multi-idioma**, SEO, caché y control de comportamiento mediante `args`.

---

## 2. Estructura general de la petición

```json
{
  "data": { ... },
  "args": { ... }
}
```

| Nodo   | Obligatorio | Descripción                                                             |
| ------ | ----------- | ----------------------------------------------------------------------- |
| `data` | ❌           | Contenido a actualizar (parcial o completo)                             |
| `args` | ❌*          | Parámetros de ejecución (*`locales` es obligatorio si se envía `args`*) |

---

## 3. 🔴 Reglas críticas de idioma (OBLIGATORIAS)

### 3.1 Idioma base obligatorio

✅ **Siempre debes actualizar Inglés (`"en"`)**
❌ No está permitido enviar solo otros idiomas sin `en`.

---

### 3.2 Orden de idiomas

Cuando un campo contiene varios idiomas:

* `"en"` **DEBE ir siempre primero**
* Luego pueden ir uno o más idiomas adicionales

✅ Correcto:

```json
"name": {
  "en": "Villa Dvor",
  "es": "Villa Cerro Verde"
}
```

❌ Incorrecto:

```json
"name": {
  "es": "Villa Cerro Verde"
}
```

❌ Incorrecto:

```json
"name": {
  "es": "Villa Cerro Verde",
  "en": "Villa Dvor"
}
```

---

### 3.3 Idiomas permitidos

Los idiomas enviados en `data` **deben existir** en:

```json
args.locales
```

---

## 4. Reglas de actualización de `data`

### 4.1 Actualización parcial (PATCH-like)

* **Todos los campos de `data` son opcionales**
* Puedes **eliminar cualquier campo que no quieras actualizar**
* Solo se modifican los campos enviados

✅ Ejemplo: actualizar solo nombre y descripción

```json
{
  "data": {
    "name": {
      "en": "Villa Dvor Renovated",
      "es": "Villa Cerro Verde Renovada"
    },
    "longDescription": {
      "en": "Updated description...",
      "es": "Descripción actualizada..."
    }
  }
}
```

---

### 4.2 Eliminación de contenido

* Enviar `null` **limpia el valor existente**
* Quitar el campo **no lo modifica**

```json
"priceRange": null
```

---

### 4.3 Reemplazo de arrays

* Los siguientes campos **reemplazan completamente** su contenido:

  * `images`
  * `services`
  * `conditions`
  * `rooms`
  * `reviews`
  * `nearbyPlaces`
  * `guestValues`

---

### 4.4 Ejemplo de actualización parcial de `rooms` (solo se reemplaza lo enviado)

```json
{
  "data": {
    "rooms": {
      "en": [
        {
          "name": "Double Room with Garden View",
          "adults": 2,
          "children": 1,
          "description": "This double room features a soundproofing. A flat-screen TV is provided.",
          "images": ["https://cf.bstatic.com/xdata/images/hotel/max1024x768/147158994.jpg"]
        }
      ],
      "es": [
        {
          "name": "Habitación Doble con Vista al Jardín",
          "adults": 2,
          "children": 1,
          "description": "Esta habitación doble está insonorizada y dispone de TV de pantalla plana.",
          "images": ["https://cf.bstatic.com/xdata/images/hotel/max1024x768/147158994.jpg"]
        }
      ]
    }
  }
}
```

---

## 5. Campos disponibles en `data`

### 5.1 Información básica

| Campo                   | Tipo          |
| ----------------------- | ------------- |
| `name`                  | object (i18n) |
| `address`               | object (i18n) |
| `rating`                | number        |
| `geoPosition.latitude`  | number        |
| `geoPosition.longitude` | number        |

---

### 5.2 Contenido descriptivo

| Campo             | Tipo          |
| ----------------- | ------------- |
| `longDescription` | object (i18n) |
| `toConsider`      | object (i18n) |
| `seoDescription`  | object (i18n) |
| `keywords`        | object (i18n) |

---

### 5.3 Servicios y políticas

| Campo        | Tipo                    |
| ------------ | ----------------------- |
| `services`   | object → array → object |
| `conditions` | object → array          |
| `extraInfo`  | string | null           |

---

### 5.4 Reviews y puntuaciones

| Campo                 | Tipo          |
| --------------------- | ------------- |
| `scoreReview`         | number        |
| `scoreReviewBasedOn`  | number | null |
| `categoryScoreReview` | object (i18n) |
| `reviews`             | object (i18n) |

---

### 5.5 Habitaciones

| Campo           | Tipo          |
| --------------- | ------------- |
| `roomsQuantity` | number        |
| `rooms`         | object (i18n) |

---

### 5.6 Ubicación y contexto

| Campo               | Tipo          |
| ------------------- | ------------- |
| `nearbyPlaces`      | object (i18n) |
| `accommodationType` | string        |

---

## 6. Uso de `args` (parámetros de ejecución)

### 6.1 Reglas generales

* Todos los valores de `args` son **opcionales**
* ❗ **`locales` es obligatorio si se envía `args`**

---

### 6.2 Campos disponibles

| Campo           | Tipo          | Descripción                   |
| --------------- | ------------- | ----------------------------- |
| `locales`       | array[string] | Idiomas activos (obligatorio) |
| `seoFormatKey`  | string        | Clave de plantilla SEO        |
| `onlyTitle`     | boolean       | Actualizar solo título        |
| `regenerateSeo` | boolean       | Recalcular SEO                |
| `append`        | boolean       | **NO soportado**              |
| `cache`         | boolean       | Control de caché              |

---

### 6.3 Ejemplo mínimo válido con `args`

```json
{
  "data": {
    "name": {
      "en": "Villa Dvor"
    }
  },
  "args": {
    "locales": ["en"]
  }
}
```

---

## 7. Ejemplos completos

### 7.1 Actualización multi-idioma correcta

```json
{
  "data": {
    "name": {
      "en": "Villa Dvor",
      "es": "Villa Cerro Verde"
    },
    "seoDescription": {
      "en": "Luxury stay in Ohrid",
      "es": "Alojamiento de lujo en Ohrid"
    }
  },
  "args": {
    "locales": ["en", "es"],
    "regenerateSeo": true,
    "cache": true
  }
}
```

---

### 7.2 Error común (❌ NO permitido)

```json
{
  "data": {
    "name": {
      "es": "Villa Cerro Verde"
    }
  }
}
```

📛 **Error:** Falta idioma base `"en"`

---

## 8. Buenas prácticas

✔ Mantén `en` como fuente de verdad
✔ Elimina campos no necesarios para evitar sobreescrituras
✔ Usa `null` solo cuando quieras borrar contenido
✔ Evita enviar campos vacíos o innecesarios

---

## 9. Resumen ejecutivo

* 🇬🇧 **Inglés (`en`) siempre obligatorio**
* 🔤 Orden de idiomas: `en` primero
* 🧩 Actualización completa: solo lo que se envía se actualiza
* ⚙ `args.locales` obligatorio
* 🧠 API diseñada para CMS y colas de actualización

