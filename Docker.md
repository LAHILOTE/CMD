# Docker CMD
- Isi Docker File
```
FROM node:18.6.0-alpine3.15
ENV DATABASE_URL="postgresql://postgres:1234567s@10.5.51.123:5432/pengurangandb?schema=public&connection_limit=5&pool_timeout=2"
ENV SESSION_SECRET=DASDKTPOTOPREIREKJFDGJFDGKGFOIWRUWNFKDSFKJSDMNSDFJDHSFDKSFHRI98
WORKDIR /app
COPY package.json /app
RUN npm install  --verbose
COPY . /app
RUN npm run build
CMD [“npm”, “start”]
EXPOSE 3000
```

- Isi .dockerignore
```
node_modules
npm-debug.log
Dockerfile
.dockerignore
.gitignore
.git
```

- Command Build Docker Image
```
docker build -t your_dockerhub_username/nodejs-image-demo .
```

- Command Melihat Image Docker yang sudah di build
```
docker images
```

- Command List all Images
```
docker images -a
```

- Command Build Container
```
docker run --name nodejs-image-demo -p 80:8080 -d your_dockerhub_username/nodejs-image-demo
```

- Command Check List Running Containers
```
docker ps
```
