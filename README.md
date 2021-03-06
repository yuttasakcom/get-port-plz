# get-port-plz

> Get an available TCP port to listen

[![npm](https://img.shields.io/npm/dt/get-port-plz.svg?style=flat-square)](https://npmjs.com/package/get-port-plz)
[![npm (scoped with tag)](https://img.shields.io/npm/v/get-port-plz/latest.svg?style=flat-square)](https://npmjs.com/package/get-port-plz)

## Usage

Install package:

```bash
yarn add get-port-plz
# or
or npm install get-port-plz
```

```js
const getPort = require('get-port-plz')
// or
import getPort from 'get-port-plz'
```

```ts
function getPort(options?: GetPortOptions): Promise<number>
```

Try sequence is: port > ports > memo > random

## Options

```ts
interface GetPortOptions {
  name?: string

  random?: boolean
  port?: number
  ports?: number[]

  memoDir?: string
  memoName?: string
}
```

### `name`

Unique name for port memorizing. Default is `default`.

### `random`

If enabled, `port` and `ports` will be ignored. Default is `false`.

### `port`

First port to check. Default is `process.env.PORT || 3000`

### `ports`

Alternative ports to check. Default is `[4000, 5000, 6000, 7000]`

### `memoDir` / `memoName`

Options passed to [fs-memo](https://github.com/nuxt-contrib/fs-memo)

- Default dir: `node_modules/get-port/dist`
- Defalt name: `.get-port`

## License

MIT
