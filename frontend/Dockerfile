FROM ubuntu:focal
RUN apt update && apt install -y curl
RUN curl -sL https://deb.nodesource.com/setup_20.x | bash && apt install -y nodejs
WORKDIR /home/project
COPY ./package.json .
RUN npm install
COPY . .
EXPOSE 5173
ENTRYPOINT [ "npm", "run", "dev" ]