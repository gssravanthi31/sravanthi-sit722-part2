# Dockerfile for book_catalog microservice
# Use an official Python runtime as a parent image
FROM python:3.10-slim

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
ENV DATABASE_URL=postgresql://user:password@db.example.com:5432/library

# Set the working directory in the container
WORKDIR /app

# Install dependencies
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY bookcatalog /app/bookcatalog
COPY scripts /app/scripts

# Expose the port the app runs on
EXPOSE 8000

# Run the FastAPI application with uvicorn
CMD ["uvicorn", "bookcatalog.main:app", "--host", "0.0.0.0", "--port", "8000"]
