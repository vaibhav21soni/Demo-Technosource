# Build stage
FROM node:18-alpine AS builder

ARG REACT_APP_API_URL=http://localhost:3001
ENV REACT_APP_API_URL=${REACT_APP_API_URL}

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

RUN npm install -g serve

EXPOSE 4200

CMD ["serve", "-s", "build", "-l", "4200"]