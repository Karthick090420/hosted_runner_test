FROM python:3.11-slim

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl unzip groff less \
    && rm -rf /var/lib/apt/lists/*

# Install AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip aws

# Copy your claude wrapper
COPY .github/workflows/claude /usr/local/bin/claude
RUN chmod +x /usr/local/bin/claude

# Install Python packages if needed
RUN pip install --no-cache-dir boto3
