FROM python:3.9-slim-buster

WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt .
RUN pip install -r requirements.txt
RUN pip install gunicorn

# Copy the rest of the application code
COPY . /app


ENV FLASK_APP=api.py 
ENV FLASK_DEBUG=0
ENV FLASK_ENV=production

EXPOSE 5000

CMD [ "gunicorn", "--bind", "0.0.0.0:5000", "api:app", "--timeout 1000", "--workers 1"]





