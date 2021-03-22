# npm常用命令及参数详解
* 安装模块如不指定版本号 默认会安装最新的版本
```
npm install packagename
```

* 安装指定版本的模块
```
npm install packagename 0.0.1
```

* 这个命令会在当前目录生成一个package.json文件，这个文件中会记录一些关于项目的信息，比如：项目的作者，git地址，入口文件、命令设置、项目名称和版本号等等，一般情况下这个文件是必须要有的，方便后续的项目添加和其他开发人员的使用。
```
npm init
```

* --save、-S参数意思是把模块的版本信息保存到dependencies（生产环境依赖）中，即你的package.json文件的dependencies字段中；
```
npm install packagename --save 或 -S
```

* --save-dev 、 -D参数意思是吧模块版本信息保存到devDependencies（开发环境依赖）中，即你的package.json文件的devDependencies字段中；
```
npm install packagename --save-dev 或 -D
```

* --save-optional 、 -O参数意思是把模块安装到optionalDependencies（可选环境依赖）中，即你的package.json文件的optionalDependencies字段中。（本人菜鸟一枚，一直也没理解这个，不过看到了就记录一下吧，万一哪天用到了，说不准就懂了......）
```
npm install packagename --save-optional 或 -O
```

* --save-exact 、 -E参数的意思是精确的安装指定版本的模块，细心的同学会发现dependencies字段里每个模块版本号前面的^不见鸟。。。
```
npm install packagename --save-exact 或 -E
```

* 如果你打开的是别人的项目，这个时候一般是没有任何依赖包的，但是所以需要的包已在package.json里面写好了，这个时候我们就可以使用npm install来安装所有项目中需要的依赖包了

* 安装全局的模块（不加参数的时候默认安装本地模块）
```
npm install packagename -g 或 --global
```

* 查看所有已经安装的模块 ll 、 ls 、 la 三个命令意思都一样 但是列表的展示方式不一样 喜欢用哪个就看个人喜好了,不懂的同学可以每个都去试下。
```
npm list 或 npm ll 或 npm la 或 npm ls
```

* 卸载已经安装的模块，后面的options参数意思与安装时候的意思一样,与这个命令相同的还有npm remove 、npm rm、npm r 、 npm un 、 npm unlink 这几个命令功能和npm uninstall基本一样，个人觉得没什么区别。
```
npm uninstall packagename [options]
```

* 这个命令会列出所有已经过时了的模块，对于已经过时了的模块可以使用下面的命令去更新
```
npm outdated
```

* 更新已经安装的模块(或全局的模块)
```
npm update [-g]
```

* 查看某条命令的详细帮助
```
npm help '命令'
```

* 查看命令的绝对路径
```
npm root
```

* 设置npm命令的配置路径，这个命令一般用于设置代理，毕竟大部分都是国外的模块，不过个人还是比较喜欢用cnpm 这个命令是用的淘宝的镜像，用法与npm一样，速度还可以。
```
npm config
```

* 除去以上的这些命令外，经常还能见到一些npm start、npm deploy、 npm build等等之类的命令，这些一般都是在package.json 中自定义的一些启动、重启、停止服务之类的命令。可以在package.json文件的scripts字段里自定义。例如：
```
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack",
    "start": "webpack-dev-server main.js,
    "deploy": "set NODE_ENV=production"
  }
  ```
