# Stage 1: Build
FROM node:14 as build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .


FROM node:14-slim
WORKDIR /app
COPY --from=build-stage /app .
EXPOSE 3000
ENV NODE_ENV=production
CMD ["node", "server.js"]
