FROM node:18-alpine

WORKDIR /app

COPY package*.json .

RUN npm install

COPY . .

# Use an environment variable for the port
ENV PORT=3003
 
# Document the port the container listens on
EXPOSE $PORT

CMD ["node", "server.js"]