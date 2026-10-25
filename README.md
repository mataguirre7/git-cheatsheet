# Git Cheatsheets

Cheatsheets de Git en español, pensadas para quien lo usa por primera vez: cada término se explica y hay una guía completa para pasar de cero a un proyecto publicado en GitHub.
Sitio 100 % estático (HTML + CSS + JS, sin build ni dependencias), con buscador, botón copiar y tema claro/oscuro.

| Hoja | Contenido |
|---|---|
| `index.html` | Portada, orden recomendado, buscador “Quiero…” y descargas en PNG |
| `01-conceptos.html` | Repositorio, commit, área de preparación, estados de un archivo, ramas, remotos, Git vs GitHub |
| `02-primeros-pasos.html` | Guía en Windows: instalar, configurar, primer commit, `.gitignore`, crear el repo en GitHub, subir y clonar |
| `03-uso-diario.html` | `status`, `add`, `commit`, `log`, `diff`, mover y borrar, `stash`, tags |
| `04-ramas.html` | Crear y cambiar de rama, merge, conflictos paso a paso, rebase, flujo de trabajo |
| `05-github.html` | `fetch`/`pull`/`push`, pull requests, forks, autenticación (navegador, token, SSH), publicar en Netlify |
| `06-deshacer.html` | Tabla de decisión, `restore`, `amend`, `reset`, `revert`, `reflog` |
| `07-problemas.html` | Errores comunes con qué significan y cómo arreglarlos |

## Verlo en local

Doble clic en `index.html` funciona. Para probarlo igual que en Netlify:

```bash
python -m http.server 8080
```

y abrí <http://localhost:8080>.

## Subir a GitHub

1. Creá un repositorio **vacío** en <https://github.com/new> (sin README ni .gitignore), por ejemplo `git-cheatsheets`.
2. Desde esta carpeta:

```bash
git remote add origin https://github.com/<tu-usuario>/git-cheatsheets.git
git push -u origin main
```

## Publicar en Netlify

1. <https://app.netlify.com> → **Add new site → Import an existing project → GitHub**.
2. Elegí el repo, dejá **Build command** vacío y **Publish directory** en `.` (ya lo define `netlify.toml`).
3. **Deploy**. Cada `git push` a `main` vuelve a publicar solo.

## Editar contenido

- Cada página es HTML plano. Los términos de cada página están en el bloque `<section class="terms-box">` del principio.
- Los bloques `<pre><code>` se resaltan y reciben el botón copiar solos. Para mostrar la salida de un comando usá `<pre class="out">`.
- Los valores a reemplazar se escriben como `&lt;nombre&gt;`.
- Las imágenes de `img/` no se regeneran solas: si cambiás una hoja, volvé a exportarla.
