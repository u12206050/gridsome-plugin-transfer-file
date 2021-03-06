# gridsome-plugin-transfer-file

> Download additional files before building your Gridsome site

## Install

- `yarn add gridsome-plugin-transfer-file`
- `npm install gridsome-plugin-transfer-file --save`

## Usage

Add as many files as you want to download in the `files` array in options.

Existing files **WILL BE** replaced as it is assumed the latest file is always downloaded.

```js
module.exports = {
  plugins: [
    {
      use: 'gridsome-plugin-transfer-file',
      options: {
        files: [
          {
            url: 'https://server.com/strings.json',
            dest: 'src/strings.json'
          },
          // Make use of env variable
          {
            url: `https://server.com/${process.env.GRIDSOME_LOCALE}.json`,
            dest: 'src/lang.json'
          }
        ]
      }
    }
  ]
}
```

### Options

#### files

- Type: `array<file>`
- Default `null`

#### file

- Type: `object`

```js
{
  url: 'https://...',
  dest: 'path',
  // Optional advanced request
  request: {
    method: 'POST' // default GET
    headers: {
      Authentication: 'Bearer 123456'
    }
  }
}
```
