# Step 1: Build the React app
FROM node:16 AS build

WORKDIR /app

# Install dependencies and build the React app
COPY frontend/package.json frontend/package-lock.json ./
RUN npm install
COPY frontend ./
RUN npm run build

# Step 2: Serve the built app using a lightweight server (nginx)
FROM nginx:alpine

# Copy the build files from the previous stage to the Nginx HTML folder
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 to access the React app
EXPOSE 80

# Start Nginx to serve the React app
CMD ["nginx", "-g", "daemon off;"]