FROM debian:bullseye

# 1. Instalar dependencias del sistema y Python + pip
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 2. Crear directorio de trabajo
WORKDIR /app

# 3. Copiar solo requirements.txt e instalar dependencias
COPY requirements.txt .
RUN pip3 install --no-cache-dir -r requirements.txt

# 4. Comando por defecto para ejecutar la app
CMD ["python3", "app.py"]
