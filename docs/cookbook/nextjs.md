---
sidebar_position: 10
---

# Nextjs Dockerfile

Following is a Great Dockerfile for Next.js, optimized for production environments that serves Nextjs at port 3000.

`Dockerfile`
```Dockerfile

FROM node:16-alpine

COPY package.json .

# Optional: Use --legacy-peer-deps to resolve potential dependency conflicts which are common in Complex Nextjs Applications.
RUN npm install --legacy-peer-deps 

COPY . .

RUN npm run build

CMD ["npm", "run", "start"]
```