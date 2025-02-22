FROM python:3.10-slim-buster

# Set the working directory in the container to /app
WORKDIR /app

# Install git
RUN apt-get update && apt-get install -y git

# Clone the repository
RUN git clone https://github.com/UrloMythus/UnHided.git .

# Can't use upstream cause an error with lxml library import with vercel
#RUN git clone https://github.com/mhdzumair/mediaflow-proxy.git .



# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt


EXPOSE 8888

# Run run.py when the container launches
CMD ["uvicorn", "run:main_app", "--host", "0.0.0.0", "--port", "8888", "--workers", "4"]
