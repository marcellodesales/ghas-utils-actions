# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Install system dependencies and clean up
RUN apt-get update && apt-get install -y \
    && rm -rf /var/lib/apt/lists/*

# Copy the Python script
COPY requirements.txt /app/requirements.txt

# Install any needed packages 
RUN pip install --no-cache-dir -r requirements.txt

# Copy the Python script
COPY ghas-settings.py /app/

# Make the script executable
RUN chmod +x /app/tenable_deletion_script.py

# Set the entrypoint to run the Python script
ENTRYPOINT ["python", "/app/ghas-settings.py"]
