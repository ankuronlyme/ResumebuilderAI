# Build Stage
FROM node:18
WORKDIR /app
COPY . .

# Installation of dependencies
RUN npm install --force
RUN npm install -g typescript

# Creation of dist folder
RUN tsc --build

# Deployment
EXPOSE 3000
CMD [ "npm", "run", "start" ]
