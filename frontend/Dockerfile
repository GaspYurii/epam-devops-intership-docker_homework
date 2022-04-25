# syntax=docker/dockerfile:1

FROM node:16 AS builder

WORKDIR /app

COPY package* ./
RUN npm install
# RUN npm run clean
COPY . .
RUN npm run build


FROM nginx as release

WORKDIR /usr/share/nginx/html

COPY --from=builder /app/build ./