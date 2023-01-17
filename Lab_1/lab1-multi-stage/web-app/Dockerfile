# Build stage
FROM node:14 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# Production stage
FROM node:14-alpine
WORKDIR /app
COPY --from=build /app/node_modules node_modules
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]

