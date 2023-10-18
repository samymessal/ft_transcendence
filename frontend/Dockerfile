# frontend/Dockerfile

# Use official Node.js image as a base
FROM node:latest as build

# Set working directory
WORKDIR /usr/src/app

# Copy local files to container
COPY . .
# # Copy package.json and package-lock.json
# COPY package*.json ./

# Install dependencies
RUN npm install


# Build the React app
RUN npm run build

# Setup Nginx
FROM nginx:alpine

# Copy the built app to Nginx directory
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# Expose port 80 for Nginx
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
