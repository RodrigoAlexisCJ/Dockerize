#stage 1
# Use official node image as the base image
FROM node:latest as build

#set the working directory
WORKDIR /app

#
COPY . .

RUN npm install

RUN npm run build --prod
#stage 2
FROM nginx:latest

COPY --from=build /app/dist/demo-app /usr/share/nginx/html

EXPOSE 80