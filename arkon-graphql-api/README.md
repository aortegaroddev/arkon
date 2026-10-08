# Arkon GraphQL API

API GraphQL en Flask para consultar y gestionar eventos y sus boletos. Los datos se almacenan en MongoDB mediante MongoEngine. El endpoint `/graphql` habilita GraphiQL para explorar las consultas y mutaciones.

## Requisitos

- Python
- MongoDB accesible desde la aplicacion
- Paquetes de `requirements.txt`

## Configuracion y ejecucion

Configura `HOST_MONGODB` y `DATABASE_MONGODB` en un archivo local `.env`, instala las dependencias y arranca Flask desde esta carpeta:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
FLASK_APP=app:app flask run --debug
```

En Windows, activa el entorno con `.venv\\Scripts\\activate`. La interfaz GraphiQL queda disponible en `http://127.0.0.1:5000/graphql`.

## Operaciones

- Consultas: `all_events` y `all_tickets`.
- Mutaciones: `create_event`, `delete_event` y `create_ticket`.

**Importante:** ejecutar `python app.py` llama a `init_db()`, que elimina y vuelve a crear las colecciones de eventos y boletos con datos de ejemplo. No ejecutes ese modo contra una base de datos con datos que quieras conservar.
