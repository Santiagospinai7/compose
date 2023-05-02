FROM node AS production

ENV NODE_ENV=production

WORKDIR /server

COPY package.json /server
COPY package-lock.json /server

RUN npm install

COPY . /server

RUN npm run build

EXPOSE 3001
CMD ["sh", "-c", "npm run start"]
