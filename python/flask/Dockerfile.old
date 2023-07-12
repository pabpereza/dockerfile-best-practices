FROM python:3-slim-bullseye 

WORKDIR /workspace

RUN apt-get update && apt-get -y install gcc musl-dev libffi-dev python3-dev openssl 

#Criptography module´s dependencies 
RUN apt-get -y install rustc cargo

# Copy the project and install Python dependencies from requirements.txt if it exists
COPY requirements.txt . 
RUN pip install -r requirements.txt

# Copy code into the container
COPY app.py .

# Run the application
CMD ["python", "app.py"]

