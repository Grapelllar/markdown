# Vue3+three.js 3D沉浸式商城项目

### 1、项目创建

① ```npm init vite@latest my-vue-app -- --template vue```

② ```npm i ```

③ 运行： ```npm run dev```

④ 安装 ```vuex npm install vuex@next --save```

#### 2、Vue建立了很多模块后，要分清楚自己在运行哪个模块，要不然改其他模块也不会显示在网页上效果。

![image-20220320182338138](C:\Users\15364\AppData\Roaming\Typora\typora-user-images\image-20220320182338138.png)

#### 3、函数间要加封号!

![image-20220320192702963](C:\Users\15364\AppData\Roaming\Typora\typora-user-images\image-20220320192702963.png)



#### 4、路由踩坑

vite中好像没有自带路由，需要 ```npm add vue-router@next```，否则报错找不到

#### 5、ant-design-vue样式使用

①安装  ```npm add unplugin-vue-components -D```

②安装 ``` npm i --save ant-design-vue@next```

#### 6、后端

使用  ```npm i axios```  引入  ```axios``` 

#### 7、踩坑 \<suspense\>

必须用\<div\>包裹。

```runtime-core.esm-bundler.js:38 [Vue warn]: <Suspense> slots expect a single root node. 
  at <Home onVnodeUnmounted=fn<onVnodeUnmounted> ref=Ref< Proxy {__v_skip: true} > > 
  at <RouterView> 
  at <App>```
```

![image-20220321164443544](C:\Users\15364\AppData\Roaming\Typora\typora-user-images\image-20220321164443544.png)

这个报错是 vue3 前段时间新添加的，就是如果在 Suspense 标签中插入多个组件的话，需要给这多个组件包裹一个根标签，如下的形式：

![image-20220321200807855](C:\Users\15364\AppData\Roaming\Typora\typora-user-images\image-20220321200807855.png)



8、进入文档时记得选择版本，如进入 next.antdv.com 时记得调整为v3，要不然版本不兼容有问题。

9、可以使用开发者模式中的网络进行流量调整，切换3G、4G等控制页面加载速度





3、**箭头函数和匿名函数的区别及具体使用语法有待深入学习（get:()=> set:()=>）**

**响应拦截器**?

