# Guía de contribución

## Ramas

- `main`: código estable, listo para entregar.
- `develop`: integración del trabajo en curso. **Todos los PR apuntan aquí.**
- `feat/<nombre>/<tarea>`: una rama por tarea, de vida corta (por ejemplo `feat/moni/setup-ci`).

No se hacen commits directos a `main` ni a `develop`.

## Flujo de trabajo

1. Parte de una issue con un criterio claro de "terminado".
2. Actualiza `develop` y crea tu rama:
   ```bash
   git switch develop
   git pull --rebase
   git switch -c feat/<nombre>/<tarea>
   ```
3. Haz commits pequeños y atómicos.
4. Antes de subir, comprueba que todo pasa en local (ver [Comprobaciones](#comprobaciones)).
5. Mantén tu rama al día con `develop` usando **rebase**, nunca merge:
   ```bash
   git fetch origin
   git rebase origin/develop
   ```
6. Sube la rama y abre un PR hacia `develop`, con la plantilla rellena y la issue enlazada (`Closes #N`).
7. Espera a que el CI esté en verde y a la revisión. Basta con la aprobación de **una** persona del equipo
   (ver `.github/CODEOWNERS`). Responde a los comentarios con nuevos commits.
8. Tras el merge, borra la rama.

**No se usa `git push --force`.** Si necesitas corregir algo ya subido, añade un commit nuevo.

## Mensajes de commit

Seguimos [Conventional Commits](https://www.conventionalcommits.org/es/):

```
<tipo>(<ámbito opcional>): <descripción en imperativo>
```

| Tipo | Uso |
| --- | --- |
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de un error |
| `docs` | Solo documentación |
| `test` | Añadir o corregir tests |
| `refactor` | Cambio de código sin cambiar el comportamiento |
| `chore` | Configuración, dependencias, CI |

Ejemplo: `feat(backend): añadir métrica de tiempo de habla`.

## Comprobaciones

Backend (desde `backend/`):

```bash
uv sync
uv run ruff check src/ tests/ scripts/
uv run python -m pytest tests -q
```

Frontend (desde `frontend/`, cuando exista el proyecto):

```bash
pnpm install
pnpm lint
pnpm test
pnpm build
```

## Pull requests

- Pequeños y centrados en una sola cosa (idealmente menos de 400 líneas).
- Con tests para el código nuevo.
- Con el checklist de la plantilla completado.

## Seguridad

- Nunca subas secretos: `.env`, tokens ni credenciales. Usa variables de entorno o GitHub Secrets.
- No subas cachés ni dependencias (`.venv`, `__pycache__`, `node_modules`). El `.gitignore` ya los excluye.
- Si subes un secreto por error, avisa al equipo y revócalo de inmediato: borrarlo del historial no basta.
