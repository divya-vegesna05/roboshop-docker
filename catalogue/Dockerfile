FROM node:18.20.2-alpine3.19
# FROM node:18
EXPOSE 8080
ENV MONGO=true
WORKDIR /opt/server
COPY package.json /opt/server
COPY server.js /opt/server
RUN npm install
CMD ["node","server.js"]
