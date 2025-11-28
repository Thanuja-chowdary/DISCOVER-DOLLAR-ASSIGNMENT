# backend/Dockerfile
# Build stage (optional if you use TypeScript/build step)
FROM node:18-alpine AS build
WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install --production

# Copy project files
COPY . .

# Expose backend port (default: 3000 or 8080 — adjust if needed)
EXPOSE 3000

# Start backend server
CMD ["node", "server.js"]
