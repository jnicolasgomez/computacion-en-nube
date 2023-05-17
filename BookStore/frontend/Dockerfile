# Base image
FROM node:16 AS build

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the React app
RUN npm run build

# Serve the built app using the `serve` package
FROM node:16-alpine

# Set working directory
WORKDIR /app

# Install the `serve` package globally
RUN npm install -g serve

# Copy the built app from the previous stage
COPY --from=build /app/build .

# Set environment variables
ENV PORT=3001
ENV REACT_APP_API_URL=<backend-ip>

# Expose the specified port
EXPOSE 3001

# Start the application
# CMD ["npm", "start"]
# Start the server using `serve` and specify the build directory as the content>
CMD ["serve", "-l", "3001", "."]

