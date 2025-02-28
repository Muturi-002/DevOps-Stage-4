FROM node:12

WORKDIR /frontend

# Copy package.json and package-lock.json to the working directory
COPY package.json package-lock.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 8080 to allow external access to the application
EXPOSE 8080

CMD ["npm", "run", "dev"]