# --------------------------
# Stage 1: Build the frontend
# --------------------------
FROM node:18-alpine AS build

# Set working directory
WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy source code
COPY . .

# Build the frontend
RUN npm run build

# --------------------------
# Stage 2: Serve with Nginx
# --------------------------
FROM nginx:alpine AS production

# Copy the build from the previous stage
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
