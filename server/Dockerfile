# Use an official Python runtime as a parent image
FROM python:3.8

# Set the working directory to /app
WORKDIR /app

# Copy only the pyproject.toml and poetry.lock files to leverage Docker caching
COPY . /app
# Install Poetry
RUN pip install --trusted-host pypi.python.org poetry

# Install project dependencies using poetry
RUN poetry config virtualenvs.create false && \
    poetry install
RUN pip install gunicorn
# Copy the rest of the application code


# Make port 5000 available to the world outside this container
EXPOSE 13337
EXPOSE 13338

# Run fabric_api_server.py when the container launches

