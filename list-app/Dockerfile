# Use an official Node.js runtime as a base image
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /usr/src/app

# Copy package.json (and package-lock.json if present)
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy all app files
COPY . .

# Expose the port your app listens on (update if different)
EXPOSE 3000

# Start the app
CMD ["node", "app.js"]


