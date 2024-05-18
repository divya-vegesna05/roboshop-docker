FROM node:18.20.2-alpine3.19
#FROM node:18
EXPOSE 8080
WORKDIR /opt/server
ENV MONGO=true
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown roboshop:roboshop /opt/server
USER roboshop
COPY package.json /opt/server
COPY server.js /opt/server
RUN npm install
CMD ["node","server.js"]