Required tools: 
    - python
    - pip

Application dependencies:
    pip install flask

Image requirements:
- '/flask' is a working directory (workdir)
- app.py is in the workdir
- index.html is in the workdir/templates
- 5000 port has to be exposed
- python app.py is a run command

Check you image:
- run command (ctrl+c to exit): docker run -it --rm -p 5000:5000 <image name> 
- open 'http://localhost:5000' in your browser 


# Base image
FROM alpine:latest

# Commands to run to install dependencies
RUN 

RUN apk update \
	&& apk add python3 py3-pip \
	&& pip3 install --upgrade pip3 \
   	&& apk add flask

# When you pass commands to the container, what should interpret them
ENTRYPOINT ["python3"]

# Command to run when the containers starts
CMD ["app.py"] 

# Working directory
WORKDIR /app
WORKDIR /flask

# Copy apps from the local folder to Docker container
COPY app.py 
COPY index.html templates/index.html

# Make below port available
EXPOSE 5000

# python app.py is a run command
CMD ["python","app.py"]




