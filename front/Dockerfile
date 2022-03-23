FROM node:lts as builder
WORKDIR /usr/src/tlcAppTmp
COPY . .
RUN npm install
RUN npm run build --prod

FROM nginx
COPY ../server-conf/api.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /usr/src/tlcAppTmp/dist/tlcfront /usr/share/nginx/html
EXPOSE 8081
