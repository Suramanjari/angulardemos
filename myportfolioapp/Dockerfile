FROM node:16.14.0-alpine AS build
RUN npm i -g @angular/cli@13.1.0
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN ng build
FROM nginx 
COPY --from=build /app/dist/myportfolioapp/ /usr/share/nginx/html/
