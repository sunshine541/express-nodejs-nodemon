# express + node + nodemon搭建自动重启服务端

> 前提安装：
> node
> npm
> cnpm
> express  （express --version 查看版本）

<a name="c6Fpn"></a>
### 启动

1. express app（进入文件夹 通过express创建应用）
1. npm i （安装依赖）
1. npm start（node ./bin/www）（启动）

~~~可以看到localhost:3000服务已启

<a name="1G7KG"></a>
### 将jade改html
可以看到views文件夹中的文件后缀名是.jade，需要改成html才可以使用打包后的资源

1. npm i ejs --save （安装依赖）（npm install ejs / cnpm install ejs -save）
1. app.js文件中修改
```javascript
var ejs=require('ejs');

// view engine setup
app.set('views', path.join(__dirname, 'views'));
app.engine('html',ejs.__express);
app.set('view engine', 'html');
```

3.  将html、css、js放入views文件夹
3. 会发现此时会发现控制台报错
3. ![image.png](https://cdn.nlark.com/yuque/0/2019/png/114101/1571040454207-51bce2b3-c0cb-4003-93d6-c3a257817aec.png#align=left&display=inline&height=143&name=image.png&originHeight=159&originWidth=550&search=&size=18348&status=done&width=496)
3. （以上操作每个步骤需要重启）
<a name="yO6hV"></a>
### 静态资源路径
```javascript
// 原文引入资源文件夹为public，改成同html一起的views就可以
app.use(express.static(path.join(__dirname, 'public')));


app.use(express.static(path.join(__dirname, 'views')));

```

<a name="sqVkh"></a>
### 加入codemon

1. npm i nodemon -g -f  全局安装nodemon
1. npm i nodemon -f     在项目中安装nodemon
1. nodemon bin/www  使用nodemon
<a name="rw8ae"></a>
### nginx配置接口代理





