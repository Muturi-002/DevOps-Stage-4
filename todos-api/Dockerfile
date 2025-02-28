FROM node:14-alpine

# Set the working directory
WORKDIR /todos-api

# Copy package.json and package-lock.json 
COPY package*.json ./

# Install dependencies
RUN npm install

COPY . .

# Expose the port the app runs on
EXPOSE 8082

# Run the app
CMD ["npm", "start"]