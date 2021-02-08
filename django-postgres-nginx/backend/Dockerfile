# Pull official base image
FROM python:3.8-alpine

# Set work directory
WORKDIR /backend

# Set environment variables
# Prevents Python from writing pyc files to disc
ENV PYTHONDONTWRITEBYTECODE 1
# Prevents Python from buffering stdout and stder
ENV PYTHONUNBUFFERED 1

# Install psycopg2 dependencies
RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev

# Install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt /backend/requirements.txt
RUN pip install -r requirements.txt

# Copy project
COPY . /backend

# Run entrypoint.sh
ENTRYPOINT ["/backend/entrypoint.sh"]