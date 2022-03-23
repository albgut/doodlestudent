FROM node:lts as builder
WORKDIR /usr/src/tlcAppTmp
COPY . .
RUN npm install
RUN npm run build --prod

FROM nginx
COPY --from=builder /usr/src/tlcAppTmp/dist/tlcfront /usr/share/nginx/html

