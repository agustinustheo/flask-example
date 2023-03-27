# Based on https://github.com/tiangolo/uwsgi-nginx-flask-docker/blob/master/docker-images/python3.10.dockerfile
FROM tiangolo/uwsgi-nginx-flask:python3.10

# Add demo app
COPY ./app.py /app/app.py
COPY ./.maintain/prestart.sh /app/prestart.sh
COPY ./.maintain/uwsgi.ini /app/uwsgi.ini
WORKDIR /app

# Run the start script provided by the parent image tiangolo/uwsgi-nginx.
# It will check for an /app/prestart.sh script (e.g. for migrations)
# And then will start Supervisor, which in turn will start Nginx and uWSGI
CMD ["/start.sh"]
