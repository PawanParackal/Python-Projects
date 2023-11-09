# Dockerfile for the Django container

# Use the official Python image as a parent image
FROM python:3.11.6-alpine

# Install system dependencies
RUN apk add --no-cache mariadb-connector-c-dev mariadb-client build-base git
# Add 'build-base' to install gcc and other build tools, and 'git' to clone files

# Set the working directory in the container
WORKDIR /app

# Clone files from your GitHub repository
RUN git clone https://github.com/PawanParackal/Python-Projects.git .

# Copy the requirements file into the container
COPY ecom/requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Specify the command to run your application
CMD ["gunicorn", "ecom.wsgi:application", "--bind", "0.0.0.0:8000"]
