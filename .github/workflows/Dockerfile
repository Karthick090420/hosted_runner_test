# Use official Python base image
FROM python:3.11-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

# Install Claude CLI (replace with actual install steps if different)
RUN pip install --no-cache-dir claude-cli

# Install claude-skill command (assuming it's a Python package)
RUN pip install --no-cache-dir claude-skill

# Copy project dependencies if needed
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Set working directory
WORKDIR /app

# Default command (can be overridden in workflow)
CMD ["python3"]
