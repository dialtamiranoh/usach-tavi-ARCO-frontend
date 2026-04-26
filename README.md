# ARCO-frontend

Frontend del proyecto ARCO.

## Requisitos

Antes de ejecutar este frontend, el backend debe estar corriendo correctamente.

Backend esperado:
- URL: `http://127.0.0.1:8000`
- Endpoint principal: `POST /ask`

## Cómo ejecutar el frontend

### 1. Entrar a la carpeta del frontend

```bash
cd ~/ARCO-frontend
```

### 2. Levantar servidor local

```bash
python3 -m http.server 5500
```

### 3. Abrir en el navegador

```text
http://127.0.0.1:5500
```

## Importante

Este frontend se conecta al backend en:

```text
http://127.0.0.1:8000/ask
```

Por eso, antes de usar el frontend, el backend debe estar levantado.

## Cómo ejecutar el backend antes del frontend

Ir a la carpeta del backend:

```bash
cd ~/ARCO-backend
source .venv/bin/activate
uvicorn main:app --reload
```

Luego verificar que el backend quede disponible en:

```text
http://127.0.0.1:8000
```

## Flujo recomendado de ejecución

### Terminal 1: modelo local

Levantar `llama-cpp-python` con el modelo `.gguf`.

### Terminal 2: backend

```bash
cd ~/ARCO-backend
source .venv/bin/activate
uvicorn main:app --reload
```

### Terminal 3: frontend

```bash
cd ~/ARCO-frontend
python3 -m http.server 5500
```

## Si aparece error al consultar

Revisar lo siguiente:

- que el modelo local siga corriendo
- que el backend siga corriendo en `127.0.0.1:8000`
- que el frontend esté abierto en `127.0.0.1:5500`
- que CORS esté habilitado en el backend

## Archivos principales

- `index.html`: interfaz del frontend
- `.gitignore`: archivos ignorados por Git