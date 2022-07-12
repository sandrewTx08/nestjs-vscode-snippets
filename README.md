# Prisma

## Prisma Service

```
{
  "NestJS Prisma Service": {
    "body": [
      "import { INestApplication, Injectable, OnModuleInit } from '@nestjs/common';\nimport { PrismaClient } from '@prisma/client';\n\n@Injectable()\nexport class PrismaService extends PrismaClient implements OnModuleInit {\n  async onModuleInit() {\n    await this.$connect();\n  }\n\n  async enableShutdownHooks(app: INestApplication) {\n    this.$on('beforeExit', async () => {\n      await app.close();\n    });\n  }\n}\n"
    ],
    "prefix": "nest-prisma"
  }
}
```

## Service

```
  {
    "NestJS Service": {
      "body": ["import { Injectable } from '@nestjs/common';\nimport { Prisma, $2 } from '@prisma/client';\nimport { PrismaService } from 'src/prisma.service';\n\n@Injectable()\nexport class $2Service {\n  constructor(private prisma: PrismaService) {}\n\n  create(data: Prisma.$2CreateInput): Promise<$2 | null> {\n    return $1.create({ data });\n  }\n\n  findAll() {\n    return $1.findMany();\n  }\n\n  findOne(where: Prisma.$2WhereInput) {\n    return $1.findFirst({ where });\n  }\n\n  update(\n    where: Prisma.$2WhereUniqueInput,\n    data: Prisma.$2UpdateInput,\n  ) {\n    return $1.update({ where, data });\n  }\n\n  remove(where: Prisma.$2WhereUniqueInput) {\n    return $1.delete({ where });\n  }\n}\n"],
      "prefix": "nest-service"
    }
  }
```

## Controller

```
{
  "NestJS Controller": {
    "body": [
      "import {\n  Controller,\n  Get,\n  Post,\n  Body,\n  Patch,\n  Param,\n  Delete,\n} from '@nestjs/common';\nimport { $2sService } from './$1.service';\nimport { Prisma } from '@prisma/client';\n\n@Controller('$1')\nexport class $2sController {\n  constructor(private readonly $1Service: $2sService) {}\n\n  @Post()\n  create(@Body() create$2Dto: Prisma.$2sCreateInput) {\n    return this.$1Service.create(create$2Dto);\n  }\n\n  @Get()\n  findAll() {\n    return this.$1Service.findAll();\n  }\n\n  @Get(':id')\n  findOne(@Param('id') id: number) {\n    return this.$1Service.findOne({ id: +id });\n  }\n\n  @Patch(':id')\n  update(\n    @Param('id') id: string,\n    @Body() update$2Dto: Prisma.$2sUpdateInput,\n  ) {\n    return this.$1Service.update({ id: +id }, update$2Dto);\n  }\n\n  @Delete(':id')\n  remove(@Param('id') id: string) {\n    return this.$1Service.remove({ id: +id });\n  }\n}\n"
    ],
    "prefix": "nest-controller"
  }
}
```

## Module

```
{
  "NestJS Module": {
    "body": ["import { Module } from '@nestjs/common';\nimport { $2sService } from './$1s.service';\nimport { $2sController } from './$1s.controller';\nimport { PrismaService } from 'src/prisma.service';\n\n@Module({\n  controllers: [$2sController],\n  providers: [$2sService, PrismaService],\n})\nexport class $2sModule {}\n"],
    "prefix": "nest-module"
  }
}
```
