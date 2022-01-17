FROM node:14.18.3-alpine
RUN npm install -g json-server
WORKDIR /data
COPY ./data.json /data/
EXPOSE 4000
CMD [ "json-server", "--watch", "data.json", "--port", "4000", "-H", "0.0.0.0" ]