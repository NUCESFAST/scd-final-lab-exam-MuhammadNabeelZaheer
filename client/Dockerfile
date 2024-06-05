# 20i-0999_frontend
FROM node:14

WORKDIR /20i-0999_frontend

COPY package.json package-lock.json ./
RUN npm install

COPY . ./
RUN npm run build

EXPOSE 0999

CMD ["npm", "start"]
