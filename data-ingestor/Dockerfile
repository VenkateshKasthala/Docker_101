FROM python:3.11-slim
RUN apt-get update && apt-get install -y libpq-dev gcc
RUN pip install psycopg2-binary
WORKDIR /app
COPY ingestion.py .
CMD ["python", "ingestion.py"]