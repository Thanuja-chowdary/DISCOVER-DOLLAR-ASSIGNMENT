
FROM node:20-alpine

# Create app directory
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
