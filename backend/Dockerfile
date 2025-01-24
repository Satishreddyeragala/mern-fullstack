
# Use official Node.js image as a base
FROM node:16

WORKDIR /app

# Install dependencies
COPY backend/package.json backend/package-lock.json ./
RUN npm install

# Copy the rest of the application code
COPY backend ./

# Expose the backend port (e.g., 5000)
EXPOSE 5000

# Start the Express server
CMD ["npm", "start"]