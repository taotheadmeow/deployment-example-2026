FROM python:3.14-slim-bookworm AS base
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
RUN adduser proj
WORKDIR /home/proj
RUN apt-get update
RUN apt-get install gettext pkg-config build-essential python3-dev curl -y --no-install-recommends
COPY ./requirements.txt .
RUN pip install -r requirements.txt
COPY ./entrypoint.sh .
#RUN touch /home/proj/logs/django.log
COPY . .
RUN ["chown", "-R", "proj:proj", "/home/proj"]
RUN ["mkdir", "/home/proj/static"]
RUN ["chown", "-R", "proj:proj", "/home/proj/static"]

USER proj
#RUN python manage.py compilemessages
RUN ["chmod", "+x", "/home/proj/entrypoint.sh"]
RUN ["chmod", "+x", "/home/proj/start.sh"]
#ENTRYPOINT /home/proj/entrypoint.sh
CMD ./start.sh
