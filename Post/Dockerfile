# 20i-0999_post
FROM node:14

WORKDIR /20i-0999_post

COPY package.json package-lock.json ./
RUN npm install

COPY . ./
EXPOSE 0999

CMD ["node", "index.js"]
