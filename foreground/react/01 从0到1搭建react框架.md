# 从0到1搭建react框架
## 1 创建基本的webpack4.x项目
* 1.1 创建空目录文件，作为项目目录
* 1.2 运行 **npm init -y** 快速初始化项目；生成 **package.json** 包管理工具。
    * package.json中包含**项目名称**、**版本号**、**描述**、**作者**和**依赖的包**等一些信息
* 1.3 在项目根目录中创建 **src** 源代码目录和 **dist** 产品目录（打包文件目录）
* 1.4 在 **src** 目录下创建 **index.html**
* 1.5 使用 **npm** 安装 **webpack** 和 **webpack-cli** 模块包，生成的包存放到 **node_modules** 中
```
npm install webpack@4.1.1 -S
npm install webpack-cli@2.0.12 -S
```
* 1.6 注意： **webpack4.x** 提供了约定大于配置概念，减少开发人员的配置
    * 打包的入口是 **src->index.js** 文件
    * ：打包的输出文件是 **dist->main.js** 文件
* 1.7 运行 webpack 命令
    * **错误1** 4.X 中新增了 mode 为必选项。
    ```
    The 'mode' option has not been set, webpack will fallback to 'production' for this value.
    ```
    解决方法：在项目根目录下创建 **webpack.config.js** 文件，添加以下内容
    ```
    module.exports = {
        mode: 'development'
    }
    ```
    * **错误2** 没有发现打包入口文件
    ```
    ERROR in main Module not found: Error: Can't resolve './src'
    ```
    解决方法：在 **src** 下创建 **index.js**
    
