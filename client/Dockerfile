FROM node:alpine as builder

WORKDIR '/app'

COPY ./package*.json ./
RUN npm install
COPY ./ ./

CMD ["npm", "run", "start"]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/confd/default.conf
COPY --from=builder /app/build /usr/share/nginx/html