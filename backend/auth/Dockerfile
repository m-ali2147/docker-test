FROM node:14-alpine 
WORKDIR /app
COPY ./package*.json ./
RUN npm install
COPY . .
EXPOSE 4000
CMD ["sh", "-c", "npm run migrate && npm run seed && npm start"]