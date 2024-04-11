FROM node:16

WORKDIR /app

COPY package*.json ./

RUN npm install

RUN npm install serve

COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm run build

EXPOSE 5000

CMD ["npx", "serve", "-s", "-l", "5000", "build"]
