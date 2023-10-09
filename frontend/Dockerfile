FROM ubuntu

WORKDIR /app

# Update the package list and install required packages (including Node.js, npm, and Git)
RUN apt-get update -y && \
    apt-get install -y nodejs npm git && \
    npm install -g serve

# Copy the application files into the container
COPY . /app/

# Install Node.js dependencies
RUN npm install

# Build your Node.js application
RUN npm run build

# Expose port 3000 for the application
EXPOSE 3000

# Define the command to run your application
CMD ["serve", "-s", "build"]
