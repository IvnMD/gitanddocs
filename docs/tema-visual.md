# Tema visual

Zensical permite personalizar la apariencia del sitio generado: colores, tipografías, idioma, logo, favicon, cabecera y pie de página. Toda la configuración se hace en `zensical.toml`, dentro de la sección `[project.theme]`.

## Colores

```toml
[project.theme.palette]
scheme = "default"
primary = "indigo"
accent = "indigo"
```

- `scheme`: `"default"` para modo claro, `"slate"` para modo oscuro.
- `primary`: color de los enlaces y la cabecera/barra lateral. Acepta nombres de color predefinidos (`red`, `blue`, `indigo`, `green`...) o `"custom"` para un color de marca propio.
- `accent`: color de los elementos interactivos (enlaces al pasar el ratón, botones, scrollbar).

### Alternar entre claro y oscuro

Para ofrecer un botón que alterne entre ambos modos (y que respete la preferencia del sistema operativo), se usan varios bloques `[[project.theme.palette]]`:

```toml
[[project.theme.palette]]
media = "(prefers-color-scheme)"
toggle.icon = "lucide/sun-moon"
toggle.name = "Switch to light mode"

[[project.theme.palette]]
media = "(prefers-color-scheme: light)"
scheme = "default"
toggle.icon = "lucide/sun"
toggle.name = "Switch to dark mode"

[[project.theme.palette]]
media = "(prefers-color-scheme: dark)"
scheme = "slate"
toggle.icon = "lucide/moon"
toggle.name = "Switch to system preference"
```

## Tipografías

```toml
[project.theme.font]
text = "Inter"
code = "Jetbrains Mono"
```

- `text`: tipografía del cuerpo de texto.
- `code`: tipografía monoespaciada para bloques de código.

Ambas aceptan cualquier fuente de Google Fonts. Para no cargar fuentes externas (por ejemplo, por privacidad de datos) y usar las del sistema:

```toml
[project.theme]
font = false
```

## Idioma

```toml
[project.theme]
language = "en"
```

Cambia `"en"` por el código del idioma deseado (Zensical soporta más de 60).

## Logo e iconos

```toml
[project.theme]
logo = "images/logo.png"
favicon = "images/favicon.png"
```

- `logo`: imagen propia dentro de la carpeta `docs/` (`.png`, `.svg`, etc.).
- `favicon`: igual, imagen dentro de `docs/`.

También se puede usar un icono del propio paquete de iconos del tema en lugar de una imagen:

```toml
[project.theme.icon]
logo = "lucide/smile"
```

## Cabecera (header)

```toml
[project.theme]
features = [
  "header.autohide",
  "announce.dismiss",
]
```