FROM node:24-alpine

WORKDIR /app

COPY . .

RUN corepack enable pnpm

RUN pnpm install

RUN pnpm run build

RUN mkdir /dist/
RUN cp -r ./dist/* /dist/
RUN rm -r ./*

WORKDIR /dist/

COPY http /dist/

RUN chmod +x ./http

EXPOSE 8000

CMD ["./http", "-i", "-p", "8000"]