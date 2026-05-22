FROM node:18-alpine

WORKDIR /app

COPY packaje.json package.json
RUN npm install

COPY server.js .

EXPOSE 3000

CMD ["npm", "start"]