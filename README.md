# Service

## Prisma

```
  {
    "NestJS Service": {
      "body": ["import { Injectable } from '@nestjs/common';\nimport { Prisma, $2 } from '@prisma/client';\nimport { PrismaService } from 'src/prisma.service';\n\n@Injectable()\nexport class $2Service {\n  constructor(private prisma: PrismaService) {}\n\n  create(data: Prisma.$2CreateInput): Promise<$2 | null> {\n    return $1.create({ data });\n  }\n\n  findAll() {\n    return $1.findMany();\n  }\n\n  findOne(where: Prisma.$2WhereInput) {\n    return $1.findFirst({ where });\n  }\n\n  update(\n    where: Prisma.$2WhereUniqueInput,\n    data: Prisma.$2UpdateInput,\n  ) {\n    return $1.update({ where, data });\n  }\n\n  remove(where: Prisma.$2WhereUniqueInput) {\n    return $1.delete({ where });\n  }\n}\n"],
      "prefix": "nest-service"
    }
  }
```
