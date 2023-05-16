# Use an official Node.js runtime as a parent image
FROM node:14-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the dependencies
RUN npm install --only=production

# Copy the rest of the application code to the working directory
COPY . .

# Set the environment variables
ENV URL_DB_CONNECTION 'mongodb+srv://<replace-user>:<replace-pwd>@<cluster-name>.mongodb.net/<collection-name>?retryWrites=true&w=majority'
ENV PORT 3000

# Expose the port that the application listens on
EXPOSE $PORT

# Start the application
CMD ["npm", "start"]
