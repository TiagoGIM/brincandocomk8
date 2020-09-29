FROM node:carbon

WORKDIR /usr/src/nodeapp

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8081

CMD ["npm", "start"]