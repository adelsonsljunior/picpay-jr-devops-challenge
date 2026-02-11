FROM cgr.dev/chainguard/python:latest-dev AS builder

WORKDIR /app

RUN python -m venv venv
COPY requirements.txt .
RUN ./venv/bin/pip install --no-cache-dir -r requirements.txt

FROM cgr.dev/chainguard/python:latest

WORKDIR /app

COPY --from=builder /app/venv ./venv
COPY main.py .

ENV PATH="/app/venv/bin:$PATH"

EXPOSE 8080

USER nonroot

ENTRYPOINT ["python", "main.py"]