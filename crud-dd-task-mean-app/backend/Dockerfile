# backend/Dockerfile
# Build stage (optional if you use TypeScript/build step)
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
# If you have a build step (e.g. TypeScript): RUN npm run build

# Runtime stage
FROM node:18-alpine
WORKDIR /app
# only copy needed files (or copy from build)
COPY --from=build /app /app
ENV NODE_ENV=production
# expose app port (ensure matches backend code)
EXPOSE 3000
# Use your app's actual start command
CMD ["node", "server.js"]
