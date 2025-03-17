# Étape 1 : build (construire l’application Angular)
FROM node:20-alpine as build

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build --configuration=production

# Étape 2 : serveur NGINX pour exécuter l’application construite
FROM nginx:latest
COPY --from=build /app/dist/angular-app-kubernetes /usr/share/nginx/html
EXPOSE 80
