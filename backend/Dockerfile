FROM ubuntu:focal
WORKDIR /usr/src/app
COPY ./app/ ./entrypoint.sh ./

ENV DEBIAN_FRONTEND noninteractive
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV FLASK_APP __main__

RUN apt update && \
  apt install -y netcat wkhtmltopdf python3 python3-pip && \
  apt remove -y python3-blinker

RUN pip install --upgrade pip && \
  pip install -r requirements.txt

EXPOSE 5000
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
CMD ["flask", "run", "--host=0.0.0.0"]



# # https://github.dev/testdrivenio/flask-on-docker
# # https://stackoverflow.com/questions/38905135/why-wont-my-docker-entrypoint-sh-execute
# # https://stackoverflow.com/questions/29882642/how-to-run-a-flask-application
# # https://github.com/JazzCore/python-pdfkit/wiki/Installing-wkhtmltopdf
# FROM python:3.11.3-slim-buster
# WORKDIR /usr/src/app

# ENV PYTHONDONTWRITEBYTECODE 1
# ENV PYTHONUNBUFFERED 1
# ENV SQL_HOST db
# ENV SQL_PORT 5432
# ENV DATABASE postgres
# ENV FLASK_APP=__main__

# RUN apt-get update && apt-get install -y netcat wkhtmltopdf
# RUN pip install --upgrade pip

# COPY ./app/requirements.txt /usr/src/app/requirements.txt

# RUN pip install -r requirements.txt

# COPY ./app/ /usr/src/app/
# COPY ./entrypoint.sh /usr/src/app/entrypoint.sh

# EXPOSE 5000
# ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
# CMD ["flask", "run", "--host=0.0.0.0"]