FROM python:3.10

# Set the working directory in the container
WORKDIR /log-processor

#avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Copy and install any needed packages specified in requirements.txt
COPY requirements.txt .

#installing dependencies for thriftpy2
RUN apt-get update && apt-get install -y gcc python3-dev

RUN pip install -r requirements.txt

COPY . .

EXPOSE 6379

# Run main.py when the container launches
CMD ["python", "./main.py"]