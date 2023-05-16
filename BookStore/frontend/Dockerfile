# Base image
FROM node:16-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Set environment variables
ENV PORT=3001

# Build the React app
RUN npm run build

# Expose the specified port
EXPOSE 3001

# Start the application
CMD ["npm", "start"]