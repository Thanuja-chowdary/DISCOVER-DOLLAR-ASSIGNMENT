# Step 1: Build Angular App
FROM node:20-alpine AS build

WORKDIR /app
COPY package*.json ./

RUN npm install

COPY . .
RUN npm run build --prod

# Step 2: Run with Nginx
FROM nginx:alpine

# Remove default Nginx config
RUN rm /etc/nginx/conf.d/default.conf

# Copy custom Nginx config for Angular SPA routing
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy build files from Step 1
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

