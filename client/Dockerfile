FROM node AS production

# Install simple http server for serving static content
# RUN npm install -g http-server

ENV NODE_ENV=production

# Make the 'client' folder the current working directory
WORKDIR /client

# Copy both 'package.json' and 'package-lock.json' (if available)
COPY package.json /client/
COPY package-lock.json /client/

# Install project dependencies
RUN npm install

# Copy project files and folders to the current working directory (i.e. 'client' folder)
COPY . /client/

# Build app for production with minification
RUN npm run build

EXPOSE 3000
CMD ["sh", "-c", "npm run start"]
