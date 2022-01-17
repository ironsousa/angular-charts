FROM node:14.18.3-alpine
RUN npm install -g @angular/cli
WORKDIR /home/app
COPY ./ /home/app/
RUN npm install
EXPOSE 4200
CMD ["ng", "serve", "--open", "--host", "0.0.0.0", "--disable-host-check"]