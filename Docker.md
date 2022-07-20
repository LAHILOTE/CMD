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

- Command Build Docker Image
```
docker build -t nama/namaapp:versi .
```

- Command Melihat Image Docker yang sudah di build
```
docker image ls
```

- Command Run Docker Image
```
docker run -d -p <port digunakan>:<port expose> --name <nama container> <nama:namaapp:versi>
```
