FROM node:alpine AS builder
COPY . /usr/app
WORKDIR /usr/app
RUN npm install && npm run build

FROM nginx
COPY --from=builder /usr/app/dist /usr/share/nginx/html

EXPOSE 5000