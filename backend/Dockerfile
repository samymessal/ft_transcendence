# backend/Dockerfile

# Use the official Node.js image as a base
FROM node:latest

# Set working directory
WORKDIR /usr/src/app

# Install NestJS CLI
RUN npm install -g @nestjs/cli

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy local files to container
COPY . .

# Build the NestJS app
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
