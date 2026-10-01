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
