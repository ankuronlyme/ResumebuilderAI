# Build Stage
FROM node:18 AS build
WORKDIR /app
COPY . .

# Installation of all dependencies
RUN npm install --force
RUN npm install -g @angular/cli
RUN npm install -g angular-http-server

# Creation of dist folder
RUN npm run build

# Deployment Process
FROM nginx:alpine
COPY --from=build /app/dist/resumebuilder /usr/share/nginx/html
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;" ]

