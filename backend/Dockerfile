FROM python:3.14-slim-bookworm AS base
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
RUN adduser proj
WORKDIR /home/proj
RUN apt-get update
RUN apt-get install gettext pkg-config build-essential python3-dev default-libmysqlclient-dev curl -y --no-install-recommends 
COPY ./requirements.txt /home/proj/
RUN pip install -r requirements.txt
#RUN touch /home/proj/logs/django.log
COPY --chown=proj:proj . .
USER proj
RUN python manage.py compilemessages
ENTRYPOINT [ "/app/entrypoint.sh" ]
CMD ["python", "-m", "uvicorn"]