FROM nginx
LABEL com.example.vendor="FrontEnd"
LABEL com.example.version="0.0.1-beta"
RUN apt-get update && apt-get install -y
WORKDIR /app
ADD . app
RUN ls -lh app
RUN apt-get install curl -y
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install nodejs -y
RUN npm install -g @angular/cli -y
RUN npm install
RUN ng build --prod
COPY ./dist /usr/share/nginx/html
EXPOSE 80
