FROM python:3.11-slim

WORKDIR /app

# Install dependencies first (better layer caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY app/ ./app/

# Create data directory
RUN mkdir -p ./app/data

EXPOSE 8000

# Use --reload only in dev; remove for production
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]