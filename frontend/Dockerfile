FROM node:12 AS build

WORKDIR /frontend

# Copy package.json and package-lock.json to the working directory
COPY package.json package-lock.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the application for production
RUN npm run build

#the instructions below are meant to be able to display the contents of the custom html file

# Use the official Nginx image based on Alpine Linux for the final stage
FROM nginx:alpine

# Copy the build output from the build stage to the Nginx HTML directory
COPY --from=build /frontend/build /usr/share/nginx/html

# Expose port 8080 to allow external access to the application
EXPOSE 8080

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]