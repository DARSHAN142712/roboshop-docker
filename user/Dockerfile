# Use official Node.js image
FROM node:20

# Set working directory inside the container
WORKDIR /opt/server

# Copy package.json and install dependencies
COPY package.json .
RUN npm install

# Copy all JavaScript files to the container
COPY *.js .

# Environment variables
ENV MONGO="true" \
    REDIS_URL="redis://redis:6379" \
    MONGO_URL="mongodb://mongodb:27017/users"

# Start the Node.js app
CMD ["node", "server.js"]
