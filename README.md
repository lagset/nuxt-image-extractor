# nuxt-image-extractor

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]

> Nuxt image extractor for full static generated sites

This module is based on this [gist](https://gist.github.com/emiliobondioli/5ce8ece783e7256fc7530738a2968ea9) from [emiliobondioli](https://github.com/emiliobondioli). 

It parses each generated page, downloads its images from your CMS API, stores them in a folder inside `/dist` and finally replace the HTML sources with the local paths.

- Works with both `nuxt generate` and `nuxt export` commands.

- Supports image url params like `?itok=gmJP5AbR`.

- It replaces payload image links as well, although this is not fully tested yet. So use with caution!

## Setup

1. Add `nuxt-image-extractor` dependency to your project

```bash
yarn add nuxt-image-extractor # or npm install nuxt-image-extractor
```

or directly add this github repo (not thorougly tested!)
```bash
npm install lagset/nuxt-image-extractor
```


2. Add `nuxt-image-extractor` to the `modules` section of `nuxt.config.js`

```js
{
  modules: [
    [
      'nuxt-image-extractor',
      {
      	// (Required) CMS url
    	baseUrl: process.env.BASE_URL,

    	// (Optional) Dir where downloaded images will be stored
    	path: '/_images',

    	// (Optional) Array containing image formats
    	extensions: ['jpg', 'jpeg', 'gif', 'png', 'webp', 'svg'],
      }
      // (Optional) Whether to download media files only appearing in payload.js/state.js files
      downloadPayloadMedia: true
    ]
  ]
}
```

## License

[MIT License](./LICENSE)

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/v/nuxt-image-extractor/latest.svg
[npm-version-href]: https://npmjs.com/package/nuxt-image-extractor

[npm-downloads-src]: https://img.shields.io/npm/dt/nuxt-image-extractor.svg
[npm-downloads-href]: https://npmjs.com/package/nuxt-image-extractor
