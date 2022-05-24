# Nest.js

* 开启新项目

* ```bash
  $ npm i -g @nestjs/cli
  $ nest new project-name
  ```

* 运行新项目

* ```bash
  $ npm run start:dev
  ```

* `nest generate module messages`  创建一个 messages 模块

* `nest generate controller messages/messages --flat ` 创建一个不带文件折叠的控制器

![generate--flat](D:\NEW\Study\markdown\pic\Nestjs\generate--flat.png)

## 使用 rest client 插件测试HTTP接口

``````http
### List all messages
GET http://localhost:3000/messages


### Create a new message 下面要有一个空行
POST http://localhost:3000/messages
Content-Type: application/json

{
    "content":"hi there"
}

### Get a particular message
GET http://localhost:3000/messages/123121313
``````



遇到报错：`SyntaxError: Unexpected end of JSON input`

检查 message.json，等json文件有没有`{}`

P24



npm install class-validator class-transformer



注意，一定要写 @Get('/:id')，注意冒号！



P65