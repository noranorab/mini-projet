FROM node:18-alpine as builder

LABEL version="1.0"
LABEL description="Application Angular dans une image Nginx"

WORKDIR /usr/src/app

COPY ./ /usr/src/app

RUN npm install 

RUN npm run build

FROM nginx:latest

COPY --from=builder /usr/src/app/dist/angular-16-crud /usr/share/nginx/html

EXPOSE 80

