FROM node:18-alpine

WORKDIR /app

COPY package*.json /app/

RUN npm ci --only=production

COPY . /app/

CMD ["npm", "run", "start"]