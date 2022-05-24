# Nest.js

## 01 起步

**初始 npm 和导入依赖，不通过 cli 创建项目**

* `npm init -y`

* `npm install @nestjs/common@7.6.17 @nestjs/core@7.6.17 @nestjs/platform-express@7.6.17 reflect-metadata@0.1.13 typescript@4.3.2`
* 创建 tsconfig.ts ，对 ts 的编译方式进行配置
* 创建 main.ts，并至少有一个模块和控制器。
* `npx ts-node-dev src/main.ts` 运行项目

**目录文件：**

* `package.json` 存储 Nest.js 配置文件，tsconfig 存储 ts 如何编译

**在 HTTP 服务器（express）中处理请求：**

![image-20220519150650883](D:\NEW\Study\markdown\pic\Nestjs\nestServer.png)

**每个请求都有特定的工具进行处理：**

![image-20220519150805800](D:\NEW\Study\markdown\pic\Nestjs\ServerTool.png)

**Nestjs 的一些 Tool，其中 Controllers 和 Modules 必要**

![partsOfNest](D:\NEW\Study\markdown\pic\Nestjs\partsOfNest.png)

**Nestjs 开始于 main.js**

**Module 会自动为里面包裹的代码创建实例**

**运行 npx ts-node-dev src/main.ts（当没有创建脚手架时）**

**main.js理解**

```typescript
import { ValidationPipe } from '@nestjs/common';
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalPipes(
    new ValidationPipe({
      whitelist: true,
    })
  )
  await app.listen(3000);
}
bootstrap();
```

95% 的 tool 从 @nestjs/common 导入 

文件名规则，和类名一致，易于理解其作用

![filenameRule](D:\NEW\Study\markdown\pic\Nestjs\filenameRule.png)

类创建于多个文件后要使用 export 导出，使得其他文件访问

使用装饰器来控制一些层叠的路由规则



## 02

* `npm install -g  @nestjs/cli`创建脚手架

* 新建项目 `nest new <projectName>`

* 使用 `npm run start:dev` 运行项目，每次有更改则重启服务器

* 可以注释 `.eslintrc.js` 来阻止 nestjs 报错，因为 ts 的报错够用了

* 生成module，使用脚手架会自动连接各个文件，自动导入 `nest generate module <moduleName>`（会自动创建 moduleName 文件夹，注意不要加上 ".module.ts"）

* 要创建在某个文件夹底下，如 controller：

  `nest generate controller messages/messages --flat` 它同时会连接其他 tool

* **快速装填：quick reload ，调出控制器 + re，可以使得包的名称快速改正 P10**

  ## 03

* rest client => Vscode测试HTTP端口的插件，只需要新建.http文件即可使用，其中 POST 请求添加 JSON 文段的方法：

  ``````json
  POST http://localhost:3000/auth/signup
  Content-type: application/json
  //需要一行空行
  {
      "email": "3192703130@qq.com",
      "password": "3192703130"
  }

![HTTPRequest](D:\NEW\Study\markdown\pic\Nestjs\HTTPRequest.png)

![HTTPRequestDecorator](D:\NEW\Study\markdown\pic\Nestjs\HTTPRequestDecorator.png)

以上装饰器从公共库导入，类似:

```typescript
@Get('/:id')
async findUser(@Param('id') id:string){}
```

ValidationPipe

在 main.ts 中导入

```typescript
import { ValidationPipe } from '@nestjs/common';
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalPipes(
    new ValidationPipe({
      whitelist: true,
    })
  )
  await app.listen(3000);
}
bootstrap();
```

DTO：Data transfer object

需要安装依赖包：

`npm install class-validator class-transformer`



![dtogithub](D:\NEW\Study\markdown\pic\Nestjs\dtogithub.png)

P17-P18 待深入研究

## 04

messages.repository.ts 例子：

````typescript
//读写文件模块
import { readFile, writeFile } from 'fs/promises';

export class MessagesRepository{
    
    //磁盘同步，异步读取
    async findOne(id: string){
        const contents = await readFile('messages.json', 'utf8');
        //contents 为 Json 对象，需要解析
        const messages = JSON.parse(contents);
        //返回查找的对象
        return messages[id];
    }
    async findAll(){
         const contents = await readFile('messages.json', 'utf8');
        //contents 为 Json 对象，需要解析
        const messages = JSON.parse(contents);
        //返回所有对象
        return messages;
    }
    async create(content: string){
          const contents = await readFile('messages.json', 'utf8');
        //contents 为 Json 对象，需要解析
        const messages = JSON.parse(contents);
        
        //随机生成id，向下取整
        const id = Math.floor(Math.random()*999)
        
        messages[id] = {id,content};
        
        await writeFile('messages.json',JSON.stringify(messages));
    }
}
````

messages.service.ts 例子：

```typescript
import { MessagesRepository} from './messages.repository';

export class MessagesService{
    messagesRepo: MessagesRepository;
    
    constructor(){
        this.messagesRepo = new MessagesRepository();
    }
    
    findOne(id : string){
        return this.messagesRepo.findOne(id);
    }
    //...
}
```

如上做，若使用findOne方法，未找到仍会显示HTTP 200，为了让它404，需要导入包 NotFoundException，抛出异常，异步。



P25-26 控制反转？？？

## 05  Computer example

`nest g module computer` 这种格式可以快速创建模块不带折叠文件夹

![nestjsDB](D:\NEW\Study\markdown\pic\Nestjs\nestjsDB.png)

安装

typeorm、sqlite3

`npm install @nestjs/typeorm typeorm sqlite3`

typeorm使得我们不必创建Repository，它会自动创建在后台



在app.module

```typescript
//导入 TypeOrm 模块
import { TypeOrmModule} from '@nestjs/typeorm'

@Module({
  //导入sqlite
  imports: [TypeOrmModule.forRoot({
    //sql类型
    type: 'sqlite',
    //sql名称
    database: 'db.sqlite',
    entities: [User],
    //同步
    synchronize: true,
  }),
    UsersModule, 
    ReportsModule],
  controllers: [AppController],
  providers: [AppService],
})
```

在user.module

```typescript
import { TypeOrmModule } from '@nestjs/typeorm';
import { User } from './user.entity';
@Module({
  imports: [
    TypeOrmModule.forFeature([User]),
    // UsersModule,
    ReportsModule,
  ],
  controllers: [UsersController],
  providers: [UsersService]
})
```

视图-》扩展-》SQLite-》

ctrl+shift+p -> sqlite:open database

![RepositoryAPI](D:\NEW\Study\markdown\pic\Nestjs\RepositoryAPI.png)

## 06

![diffbetweenCreateandSave](D:\NEW\Study\markdown\pic\Nestjs\diffbetweenCreateandSave.png)

create是创建实例，save是持久化到数据库

但是为什么不能直接save呢？是为了确保一定通过 User 实例，如果里面有加验证器，或者有其他的逻辑，则可以进行验证以确保数据的准确性

![newRouteOfRequest](D:\NEW\Study\markdown\pic\Nestjs\newRouteOfRequest.png)

![saveremovehook](D:\NEW\Study\markdown\pic\Nestjs\saveremovehook.png)

左边函数会执行hook,右边直接保存到数据库

**P57???**

## 07 拦截器



## 08

流程图，登陆注册

![stepOfsign](D:\NEW\Study\markdown\pic\Nestjs\stepOfsign.png)

新的模块

![addAuthUsersModule](D:\NEW\Study\markdown\pic\Nestjs\addAuthUsersModule.png)

* 加密:hash + salt

  回听 P70 细节

  安装cookie `npm install cookie-session @types/cookie-session`

因为兼容性原因，需要如下方法导入，在main.ts：

```typescript
const cookieSeesion = require('cookie-session');
 app.use(cookieSeesion({

  keys:['dsad']

 }))
```

