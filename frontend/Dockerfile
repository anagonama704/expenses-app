# ビルドステージ
FROM node as build-stage
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .
RUN npm run build

# プロダクションステージ
FROM nginx:alpine
COPY --from=build-stage /app/build /usr/share/nginx/html
