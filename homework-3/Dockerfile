# Base image
# https://hub.docker.com/r/redislabs/redis-py/
# FROM redis-py:latest
# Along with above line Python 3 and Redis DB (port - 6379) should be installed

COPY ./requirements.txt /requirements.txt
RUN pip install -r requirements.txt

# When you pass commands to the container, what should interpret them
ENTRYPOINT ["python3"]

# Create working directory
WORKDIR /app
WORKDIR /app/logs

# Copy apps from the local folder to Docker container
COPY hist/app.py app.py

# Make below port available (for Flask app)
EXPOSE 5000

# python app.py is a run command
CMD ["app.py"]

# Define default command for Redis Server
CMD ["sh", "redis-server", "/etc/redis/redis.conf"]

# Expose port for Redis to be run on
EXPOSE 6379
