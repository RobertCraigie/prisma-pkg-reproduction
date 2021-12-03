# Reproduction for [10564](https://github.com/prisma/prisma/issues/10564)

Reproduction repository for https://github.com/prisma/prisma/issues/10564

## Usage

Install dependencies

```
$ npm install
```

Package the CLI, replace `darwin` with either `linux` or `win`

```
$ npx pkg -t node12-darwin node_modules/prisma
```

Generate the client using the node CLI

```
$ npx prisma generate
Prisma schema loaded from schema.prisma

✔ Generated Prisma Client (3.6.0 | library) to ./node_modules/@prisma/client in 1.91s
You can now start using Prisma Client in your code. Reference: https://pris.ly/d/client

import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()
```

Generate the client using the packaged CLI

```
$ ./prisma generate

Error: ENOENT: no such file or directory, copyfile '/Users/robert/.cache/prisma/master/dc520b92b1ebb2d28dc3161f9f82e875bd35d727/darwin/prisma-fmt' -> '/snapshot/node_modules/@prisma/engines/prisma-fmt-darwin'
```
