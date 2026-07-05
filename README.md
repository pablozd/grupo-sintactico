# Grupo Sintáctico

Sitio inicial para un grupo de lecturas sobre sintaxis dirigido a estudiantes de Letras.

El sitio está pensado para publicarse con **GitHub Pages** usando el tema **Minimal Mistakes**.

## Estructura

```text
grupo-sintactico/
├── .github/workflows/deploy.yml
├── _config.yml
├── _data/
│   └── navigation.yml
├── _includes/
│   └── masthead.html
├── _layouts/
│   └── default.html
├── index.md          (es)
├── index.en.md        (en)
├── actividades.md / actividades.en.md
├── calendario.md / calendario.en.md
├── integrantes.md / integrantes.en.md
├── bibliografia.md / bibliografia.en.md
├── _posts/
│   ├── 2026-07-15-primer-encuentro.md      (es)
│   └── 2026-07-15-primer-encuentro-en.md   (en)
└── assets/
```

## Idiomas (español / inglés)

El sitio usa [jekyll-polyglot](https://github.com/untra/polyglot) para publicar cada página en español (idioma por defecto, sin prefijo) e inglés (con prefijo `/en/`). El selector ES/EN aparece en el header de todas las páginas.

Para agregar o editar contenido:

- Cada página tiene dos archivos: uno con `lang: es` y otro con `lang: en` y el mismo `permalink`.
- Ambos archivos de una misma página comparten el mismo `page_id` (solo por prolijidad, no lo usa esta versión del plugin).
- Los enlaces de navegación en inglés están en `_data/navigation.yml`, bajo la clave `en:`.
- `_includes/masthead.html` y `_layouts/default.html` son copias locales del tema (con el selector de idioma agregado) que sobrescriben las del tema remoto.

## Despliegue

El sitio se construye y publica automáticamente con GitHub Actions (`.github/workflows/deploy.yml`) cada vez que se hace push a `main`. Esto es necesario porque `jekyll-polyglot` no está en la lista de plugins permitidos por el build clásico de GitHub Pages ("Deploy from a branch").

Para activarlo en un repositorio nuevo:

1. Crear un repositorio en GitHub y subir estos archivos.
2. Ir a **Settings > Pages**.
3. En **Build and deployment**, elegir **Source: GitHub Actions**.
4. Hacer push a `main`; el workflow se encarga del resto.

El sitio debería quedar disponible en:

```text
https://USUARIO.github.io/NOMBRE-DEL-REPO/
```

## Importante

Si el repositorio no se llama `USUARIO.github.io`, hay que editar `_config.yml` y completar:

```yaml
url: "https://USUARIO.github.io"
baseurl: "/NOMBRE-DEL-REPO"
```

Si el repositorio sí se llama `USUARIO.github.io`, dejar `baseurl: ""`.

## Desarrollo local

```bash
bundle install
bundle exec jekyll serve
```

## Edición de contenido

Cada página está escrita en Markdown, en español e inglés:

- `index.md` / `index.en.md`: descripción general del grupo.
- `actividades.md` / `actividades.en.md`: actividades realizadas.
- `calendario.md` / `calendario.en.md`: próximos encuentros.
- `integrantes.md` / `integrantes.en.md`: participantes.
- `bibliografia.md` / `bibliografia.en.md`: textos y lecturas.

Para agregar una entrada nueva, crear dos archivos en `_posts/` (uno en español y otro en inglés) con el mismo `permalink` en el front matter, `lang: es` / `lang: en` respectivamente:

```text
AAAA-MM-DD-titulo-del-encuentro.md
AAAA-MM-DD-titulo-del-encuentro-en.md
```

Ejemplo:

```text
2026-08-12-sujetos-nulos.md
2026-08-12-sujetos-nulos-en.md
```

