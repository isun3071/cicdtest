FROM python:3.11-slim
WORKDIR /app

COPY app/requirements.txt .                           # layer 1: only changes when deps change
RUN pip install --no-cache-dir -r requirements.txt    # layer 2: cached as long as layer 1 is unchanged

COPY app/ ./app                                        # layer 3: changes on every code edit
EXPOSE 8080
CMD ["python", "app/main.py"]
