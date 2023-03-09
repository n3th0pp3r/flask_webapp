FROM python:3.11

WORKDIR /app

COPY requirements.txt /app/
COPY main.py /app/

RUN pip install virtualenv && \ 
	virtualenv /app/venv && \ 
	/app/venv/bin/pip install --no-cache-dir -r /app/requirements.txt 

ENV FLASK_APP=app.py
ENV FLASK_DEBUG=1

EXPOSE 5000 

CMD ["/app/venv/bin/python", "-m", "flask", "--app", "main:app", "run", "--host=0.0.0.0"]
