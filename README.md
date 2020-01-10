# phalcon-nuxt-demo

> Phalcon Demo with nuxt/vue

## Build Setup

``` bash
# install dependencies
$ npm run install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

## Docker setup
Clone repo and in root run:

```
docker run -it -p 3000:3000 -v $(pwd):/project node bash
cd /project
npm install
npm run dev
```
Goto http://localhost:3000 in your browser.

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
