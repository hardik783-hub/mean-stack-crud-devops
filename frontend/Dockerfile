FROM node:18 AS build 

WORKDIR /app

COPY package*.json ./
RUN npm install 

COPY . .

RUN npm run build -- --configuration production 

# 2 stage - serve with nginx

FROM nginx:alpine 

COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
COPY ../nginx.conf /etc/nginx/nginx.conf
EXPOSE 80



