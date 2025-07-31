Teknikal Test MuatMuat NextJS

**Langkah Instalasi**
Git clone Reponya: https://github.com/MochammadIndraM/Managemen-Produk.git

Atur Env : DATABASE_URL="mysql://root:root@localhost:3306/manajemen_produk"

**Setup DB NEXTJS**
npm install prisma @prisma/client
npx prisma init

contoh schema.prima
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}

model User {
  id    Int    @id @default(autoincrement())
  name  String
  email String @unique
}


**migrate prisma**
npx prisma migrate dev --name init

**buat folder lib/prisma.jsx**
import { PrismaClient } from '@prisma/client'

let prisma

if (!global.prisma) {
  global.prisma = new PrismaClient()
}
prisma = global.prisma

export { prisma }

**install sweetalert**
npm install sweetalert2

**Jalankan Aplikasi**
Buka Terminal
  $ npm run dev
