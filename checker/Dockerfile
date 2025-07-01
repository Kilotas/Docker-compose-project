FROM python:3.10-slim

WORKDIR /usr/src/myapp

COPY . .

RUN pip install -r requirements.txt

CMD ["python", "app.py"]