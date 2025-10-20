FROM node:18

# Install curl for healthcheck
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /workspace

# Install global npm packages
RUN npm install -g nodemon

# Keep container running
CMD ["sleep", "infinity"]
