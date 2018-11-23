
FROM alpine:3.3

RUN apk --no-cache add py-pip libpq python-dev curl

RUN pip install flask==0.10.1 python-consul gunicorn

ADD / /app

WORKDIR /app

HEALTHCHECK CMD curl --fail http://localhost:5000/health || exit 1

EXPOSE 5000
EXPOSE 7000

CMD gunicorn app.py & gunicorn admin.py
