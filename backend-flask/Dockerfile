FROM python:3.10-slim-buster

# Inside Container
# make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this contains the libraries to install to run the app. ex. like package.json
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flask (inside container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside Container
# will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]