# Use official Python base image
FROM python:3.11-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN pip install anthropic


# Copy project dependencies if needed
COPY claude /usr/local/bin/claude
RUN chmod +x /usr/local/bin/claude



# Set working directory
WORKDIR /app

# Default command (can be overridden in workflow)
CMD ["python3"]
