# Use an official node image as a base image
FROM node:14

# Set the working directory
WORKDIR /app


# Copy package.json and package-lock.json files to the working directory
COPY package.json ./


# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . ./

# Build the app for production
RUN npm run build

# Expose the port the app will run on
EXPOSE 3000

# Serve the built app using a simple HTTP server
RUN npm install -g serve

# Start the app using the 'serve' command, serving the build folder
CMD ["serve", "-s", "build"]
