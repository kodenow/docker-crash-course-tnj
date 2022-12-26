FROM node:17-alpine

RUN npm install -g nodemon

WORKDIR /app

#copy first the package.json file before npm install so npm install sees the file
COPY package.json .

#previously, this line was after line 11 "COPY . .", but we move it above 
#so if we don't have changes in dependency, it will just pull from the cache
RUN npm install

COPY . .

EXPOSE 4000
# required for docker desktop port mapping

CMD ["npm", "run", "dev"]