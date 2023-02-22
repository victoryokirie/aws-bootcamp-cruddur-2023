FROM python:3.10-slim-buster


# inside container
# make a new folder inside container
WORKDIR /backend-flask

#outside container -> inside container
#this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

#inside container
# install the python libraries used for the app
RUN pip3 install -r requirements.txt

#outside container -> inside container
# copy everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flask (insider container)
COPY . .

# set environment variables (Env Vars)
# inside container and will remain set when the container is run 
ENV FLASK_ENV=development

EXPOSE ${PORT}

# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]