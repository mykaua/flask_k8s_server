FROM python:3.10-alpine
WORKDIR /app
COPY requirements.txt /app/requirements.txt
RUN pip install -r requirements.txt
COPY server.py /app/
EXPOSE 5000
CMD ["python3", "server.py"]
