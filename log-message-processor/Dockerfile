# Use an official Python runtime as a parent image
FROM python:3.10

# Set the working directory in the container
WORKDIR /log-processor

#avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Copy and install any needed packages specified in requirements.txt
COPY requirements.txt .

RUN pip install --upgrade pip setuptools wheel

RUN pip install -r requirements.txt

# Copy the rest of the application code
COPY . .

# Expose the port the application runs on
EXPOSE 6379

# Run main.py when the container launches
CMD ["python", "./main.py"]