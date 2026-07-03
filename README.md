# Grupo Sintáctico

Sitio inicial para un grupo de lecturas sobre sintaxis dirigido a estudiantes de Letras.

El sitio está pensado para publicarse con **GitHub Pages** usando el tema **Minimal Mistakes**.

## Estructura

```text
grupo-sintactico/
├── _config.yml
├── _data/
│   └── navigation.yml
├── index.md
├── actividades.md
├── calendario.md
├── integrantes.md
├── bibliografia.md
├── _posts/
│   └── 2026-07-15-primer-encuentro.md
└── assets/
```

## Cómo usarlo

1. Crear un repositorio en GitHub.
2. Subir estos archivos al repositorio.
3. Ir a **Settings > Pages**.
4. En **Build and deployment**, elegir:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Guardar.

El sitio debería quedar disponible en:

```text
https://USUARIO.github.io/NOMBRE-DEL-REPO/
```

## Importante

Si el repositorio no se llama `USUARIO.github.io`, hay que editar `_config.yml` y completar:

```yaml
baseurl: "/NOMBRE-DEL-REPO"
```

Por ejemplo:

```yaml
baseurl: "/grupo-sintactico"
```

Si el repositorio sí se llama `USUARIO.github.io`, dejar:

```yaml
baseurl: ""
```

## Edición de contenido

Cada página está escrita en Markdown:

- `index.md`: descripción general del grupo.
- `actividades.md`: actividades realizadas.
- `calendario.md`: próximos encuentros.
- `integrantes.md`: participantes.
- `bibliografia.md`: textos y lecturas.

Para agregar una entrada nueva, crear un archivo en `_posts/` con este formato:

```text
AAAA-MM-DD-titulo-del-encuentro.md
```

Ejemplo:

```text
2026-08-12-sujetos-nulos.md
```

