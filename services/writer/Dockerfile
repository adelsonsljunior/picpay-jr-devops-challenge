FROM python:3.12-alpine

WORKDIR /app

COPY requirements.txt .

COPY main.py .

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8080

ENTRYPOINT ["python"]

CMD ["main.py"]