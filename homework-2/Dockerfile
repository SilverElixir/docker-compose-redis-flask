# Base image
FROM alpine:latest

# Commands to run to install dependencies
RUN apk update \
   && apk add python3 py3-pip

# Install 'flask' lib via pip
RUN pip install flask

# When you pass commands to the container, what should interpret them
ENTRYPOINT ["python3"]

# Command to run when the containers starts
CMD ["app.py"]

# Create working directory
WORKDIR /app

# Copy apps from the local folder to Docker container
COPY app.py app.py
COPY index.html templates/index.html

# Make below port available
EXPOSE 5000

# python app.py is a run command
CMD ["python","app.py"]

