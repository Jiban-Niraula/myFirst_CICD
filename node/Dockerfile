# -------- Build Stage --------
FROM node:24-alpine AS build

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm clean-install

COPY . .

# -------- Run Stage --------
FROM node:24-alpine

WORKDIR /usr/src/app

COPY --from=build /usr/src/app .

EXPOSE 3000

CMD ["node", "app.js"]