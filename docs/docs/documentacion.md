# Documentación del Proyecto

Este documento resume el contexto, tecnologías, dependencias, estructura del proyecto y cómo ejecutarlo localmente. También detalla variables de entorno, accesos y aplicaciones externas (si aplica).

## Contexto general
- **Propósito**: Proyecto base de documentación usando MkDocs con un ejemplo mínimo de script Python.
- **Alcance**: Mantener documentación técnica navegable y fácil de desplegar localmente.

## Tecnologías
- **Python**: 3.13+
- **MkDocs**: >= 1.6.1
- **Tema**: readthedocs (configurado en `docs/mkdocs.yml`)
- **Gestor opcional**: uv (para sincronizar dependencias vía `uv sync`), o pip/venv estándar.

## Dependencias
- Declaradas en `pyproject.toml`:
  - `mkdocs>=1.6.1`
- Lockfile: `uv.lock` (si usas uv).

Instalación sugerida:
- Con uv:
  ```bash
  uv sync
  ```
- Con pip (Windows):
  ```bash
  python -m venv .venv
  .venv\Scripts\activate
  pip install -U pip
  pip install mkdocs>=1.6.1
  ```

## Estructura
- **Árbol de carpetas:**
  ```text
  mkdocs-demo/
  ├─ pyproject.toml
  ├─ main.py
  ├─ users.py
  ├─ CHANGELOG.md
  ├─ README.md
  ├─ uv.lock
  ├─ docs/
  │  ├─ mkdocs.yml
  │  ├─ docs/
  │  │  ├─ index.md
  │  │  ├─ architecture.md
  │  │  ├─ tuya.md
  │  │  ├─ changelog.md
  │  │  └─ documentacion.md
  │  └─ site/   (salida generada por MkDocs)
  ```

- **Archivos relevantes:**
  - `pyproject.toml`: Metadatos del proyecto y dependencias.
  - `main.py`: Script de ejemplo (imprime "Hello from mkdocs-demo!").
  - `users.py`: Función `call_user()` imprime "Hello from call_user!".
  - `CHANGELOG.md`: Bitácora de cambios en la raíz del repositorio.
  - `docs/docs/changelog.md`: Página de changelog incluida en la documentación.
  - `docs/mkdocs.yml`: Configuración del sitio (navegación, tema, rutas de páginas).

Notas:
- `mkdocs.yml` dentro de `docs/` referencia archivos en `docs/docs/`.
- La salida estática se genera en `docs/site/`.

## Ejecución local
- Ejecutar script Python:
  ```bash
  python main.py
    |
    |--
  ```

- Servir documentación (desde carpeta `docs/`):
  ```bash
  mkdocs serve -f mkdocs.yml
  ```
  Abre la URL mostrada (por defecto http://127.0.0.1:8000/).

- Construir documentación estática (desde `docs/`):
  ```bash
  mkdocs build -f mkdocs.yml
  ```
  La salida queda en `docs/site/`.

## Variables de entorno
- No se requieren variables de entorno para la ejecución básica de este proyecto.

## Accesos
- No hay credenciales ni accesos especiales definidos en el repositorio. Si en el futuro se integran servicios, documentarlos aquí.

## Aplicaciones externas
- Actualmente no aplica. Si se integran servicios externos (APIs, analítica, CI/CD), especificar:
  - Nombre del servicio
  - Propósito
  - Configuración/variables necesarias
  - Enlaces de acceso y permisos
