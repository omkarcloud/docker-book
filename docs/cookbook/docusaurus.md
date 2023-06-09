---
sidebar_position: 20
---

# Docusaurus Dockerfile

Following is a Great Dockerfile for Docusaurus, optimized for production environments that serves Docusaurus at port 3000.

`Dockerfile`
```Dockerfile
FROM node:18-alpine

WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD npm run serve  --  --port 3000 --host 0.0.0.0
```