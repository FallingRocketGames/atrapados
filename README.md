# Atrapados en la Zona — Assets & Data

Repositorio de recursos estáticos y datos de contenido para la app móvil **Atrapados en la Zona**.

> ⚠️ Este repositorio debe permanecer **público** para que la app pueda acceder a los archivos sin autenticación.

---

## Estructura de carpetas

```
atrapados/
├── 📁 data/
│   ├── banners.json          # Banners del carrusel publicitario
│   ├── eventos.json          # Próximos eventos
│   └── sponsors.json         # Patrocinadores
│
└── 📁 images/
    ├── 📁 banners/           # Imágenes del carrusel de inicio y radio
    ├── 📁 eventos/           # Thumbnails de eventos
    └── 📁 sponsors/          # Logos de patrocinadores
```

---

## URLs base

Todos los archivos se acceden mediante la URL raw de GitHub:

```
https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/
```

Ejemplos:
```
https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/data/eventos.json
https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/images/eventos/roadrunner.jpg
```

---

## Formato de los archivos JSON

### `data/banners.json`
Banners del carrusel publicitario. Se usan en la página de Inicio y en la página de Radio. Cada página puede tener su propia lista.

```json
{
  "home": [
    {
      "id": "banner_001",
      "imagen": "https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/images/banners/banner_001.jpg",
      "titulo": "Nombre del Sponsor",
      "subtitulo": "Tagline del sponsor",
      "url": "https://www.sitiowebdelsponsor.com"
    }
  ],
  "radio": [
    {
      "id": "banner_r001",
      "imagen": "https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/images/banners/banner_r001.jpg",
      "titulo": "Nombre del Sponsor",
      "subtitulo": "Tagline del sponsor",
      "url": "https://www.sitiowebdelsponsor.com"
    }
  ]
}
```

---

### `data/eventos.json`
Lista de próximos eventos. La fecha de inicio y fin se usan para agregar el evento al calendario del teléfono.

```json
{
  "eventos": [
    {
      "id": "evento_001",
      "imagen": "https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/images/eventos/evento_001.jpg",
      "titulo": "Nombre del Evento",
      "fecha": "MAYO 17",
      "lugar": "Nombre del lugar, Ciudad",
      "descripcion": "Descripción del evento.",
      "fechaInicio": "2026-05-17T18:00:00",
      "fechaFin": "2026-05-17T22:00:00"
    }
  ]
}
```

---

### `data/sponsors.json`
Lista de patrocinadores con información de contacto y redes sociales.

```json
{
  "sponsors": [
    {
      "id": "sponsor_001",
      "imagen": "https://raw.githubusercontent.com/fallingrocketgames/atrapados/main/images/sponsors/sponsor_001.svg",
      "nombre": "Nombre del Sponsor",
      "descripcion": "Descripción del sponsor.",
      "sitioWeb": "https://www.sitiowebdelsponsor.com",
      "facebook": "https://facebook.com/paginadelsponsor",
      "instagram": "https://instagram.com/paginadelsponsor",
      "tiktok": "https://tiktok.com/@paginadelsponsor",
      "whatsapp": "526641234567"
    }
  ]
}
```

> El campo `whatsapp` lleva el número en formato internacional sin `+` ni espacios. Ejemplo: `526641234567` para un número de Mexicali con lada 664.

---

## Especificaciones de imágenes

| Carpeta | Uso | Tamaño recomendado | Formato |
|---|---|---|---|
| `images/banners/` | Carrusel Hero (Inicio y Radio) | 1200 x 600 px | JPG o PNG |
| `images/eventos/` | Thumbnail de evento | 400 x 220 px | JPG o PNG |
| `images/sponsors/` | Logo de patrocinador | 400 x 200 px | SVG o PNG transparente |

---

## Cómo actualizar el contenido

### Agregar un nuevo evento
1. Sube la imagen del evento a `images/eventos/`
2. Abre `data/eventos.json`
3. Agrega un nuevo objeto al array `eventos` siguiendo el formato indicado
4. Haz commit con el mensaje: `feat: agregar evento [nombre del evento]`

### Agregar un nuevo banner
1. Sube la imagen del banner a `images/banners/`
2. Abre `data/banners.json`
3. Agrega el banner en `home`, `radio` o ambos según corresponda
4. Haz commit con el mensaje: `feat: agregar banner [nombre del sponsor]`

### Agregar un nuevo patrocinador
1. Sube el logo a `images/sponsors/`
2. Abre `data/sponsors.json`
3. Agrega el nuevo objeto al array `sponsors`
4. Haz commit con el mensaje: `feat: agregar sponsor [nombre]`

### Eliminar contenido
Simplemente elimina el objeto del JSON correspondiente. No es necesario borrar la imagen inmediatamente, pero se recomienda mantener el repositorio limpio.

---

## Notas importantes

- Los cambios en los JSON se reflejan en la app **sin necesidad de actualizar la app** en Play Store.
- Las imágenes deben ser optimizadas antes de subirse para no afectar los tiempos de carga. Se recomienda un tamaño máximo de **500KB por imagen**.
- Los campos de redes sociales y `url` pueden dejarse como cadena vacía `""` si no aplican.
- El campo `id` debe ser único en cada lista.

---

## Tecnología

- **App:** .NET MAUI — Android
- **Desarrollador:** [Falling Rocket Games](https://fallingrocketgames.github.io)
- **Estación:** [Atrapados en la Zona](https://www.atrapadosenlazona.com)
