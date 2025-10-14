# Imagen base moderna (3.11 o 3.10)
FROM python:3.11-slim

WORKDIR /app

# (Opcional) paquetes nativos si tus deps lo requieren
# RUN apt-get update && apt-get install -y --no-install-recommends build-essential && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000
# Para dev; en prod quita --reload
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
