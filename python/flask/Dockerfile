FROM python:slim AS builder

WORKDIR /workspace

#Criptography module´s dependencies 
RUN apt update &&  apt-get -y install rustc cargo

# Copy the project and install Python dependencies from requirements.txt if it exists
COPY requirements.txt .
RUN pip install --user -r requirements.txt

FROM python:slim


#Configure path and python environment
WORKDIR /workspace
COPY app.py .

# Create a user to run the application with bash shell and home directory
RUN useradd -ms /bin/bash apiuser 
USER apiuser

# Copy the Python dependencies from the builder image and set the PATH
COPY --chown=apiuser --from=builder /root/.local /home/apiuser/.local
ENV PATH=/home/apiuser/.local/bin:$PATH

# Run the flask application
EXPOSE 80
ENTRYPOINT ["python3","app.py"]

