FROM node:18-alpine as builder

WORKDIR /app

COPY package*.json /app/

RUN npm ci --only=production

COPY . /app/

RUN npm run build

FROM node:18-alpine as runner

COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/dist ./dist

CMD ["npm", "run", "start"]
