FROM node:alpine

ARG DATABASE_URL JWT_SECRET REDIRECT_URL FILES_URL CLIENT_ID CLIENT_SECRET
ENV DATABASE_URL=$DATABASE_URL
ENV JWT_SECRET=$JWT_SECRET
ENV REDIRECT_URL=$REDIRECT_URL
ENV FILES_URL=$FILES_URL
ENV CLIENT_ID=$CLIENT_ID
ENV CLIENT_SECRET=$CLIENT_SECRET

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

RUN npx prisma generate

RUN npm run build

CMD [ "npm", "run", "start:prod" ]