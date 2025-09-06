# step_1-django-docker
This project shows how to Dockize a Django Project

## Running the Project with Docker

This project is built with **Django** and containerized using **Docker**.

### Dockerfile Configuration
The `Dockerfile` uses the official Python 3.10 slim image as the base and installs the required dependencies.

```dockerfile
FROM python:3.10-slim-bullseye

WORKDIR /app

COPY requirement.txt requirement.txt
RUN pip install -r requirement.txt

COPY . .

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]


Build the Docker Image

Run the following command to build the Docker image.
Here, python-django is the name of the image:

docker build --tag python-django .

Run the Docker Container

After building the image, start a container and expose the application on port 8000:

docker run --publish 8000:8000 python-django


The Django development server will now be accessible at:
👉 http://localhost:8000