FROM node:14-alpine as builder
WORKDIR /app
COPY ./package*.json /app
RUN npm install
COPY . /app
RUN npm run build 

FROM nginx:1.21.0-alpine
COPY --from=builder /app/build /usr/share/nginx/html
COPY  nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]