FROM node:alpine as builder

# set the working direction
WORKDIR /App

# install app dependencies
COPY . .

RUN npm install

RUN npm run build

FROM nginx

COPY --from=builder /App/build /usr/share/nginx/html