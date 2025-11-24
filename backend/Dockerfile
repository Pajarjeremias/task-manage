#Used source from: 
#https://www.docker.com/blog/how-to-dockerize-react-app/
FROM node:18-alpine AS build
WORKDIR /src
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM node:18-alpine AS prod
WORKDIR /src
# These are for local docker build
#ARG NODE_ENV
#ENV NODE_ENV=${NODE_ENV}
COPY --from=build /src ./
CMD ["npm", "run", "start"]
