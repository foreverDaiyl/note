#### *npm官网（Node Package Manager）
https://www.npmjs.com/

#### * npm常用命令
| 命令 | 描述 |
| --- | --- |
| npm -v  | 查看当前npm版本 |
| npm install -y | 创建配置清单 生成package.json |
| npm install | 安装package.json文件中所有依赖的第三方模块信息 |
| npm install xxx --save | 安装xx并保存到配置清单到生产依赖中 |
| npm install xxx@xxx | 安装指定版本号的依赖 |
| npm install xxx --save-dev | 安装xx并保存到配置清单到开发依赖中 |
| npm install node-sass - -save-dev  sass-loader - -save-dev   | `并列`安装xx并保存到配置清单到开发依赖中 |
| npm uninstall less （或-g）   | `卸载`该依赖 |
| npm run xxx | `运行`package.json中的scripts脚本 |
| npm install cnpm -g | 全局安装cnpm |
| npm install yarn -g | 全局安装yarn |
| npm install bower -g | 全局安装bower |
| npm install nrm -g | 全局安装切源工具 基于nrm把源切换到淘宝源上 |
| npm view xxx | 查看模块的历史版本信息 |
| npm root / -g | 查看本地项目或者全局环境下，npm的安装目录 |


#### * package.json
```javascript
{
  "name": "projectName",  //=>模块名称
  "version": "1.0.0",  //=>版本号
  "description": "",   //=>模块的描述
  "main": "index.js",  //=>当前模块的主入口文件
  "dependencies": {    //=>生产依赖
    "zepto": "^1.2.0"
  },
  "devDependencies": { //=>开发依赖

  },
  "scripts": {  //=>可执行脚本
    "test": "echo \"Error: no test specified\" && exit 1",
    "serve": "vue-cli-service serve",//=>npm run serve
    "build": "vue-cli-service build",//=>npm run build
    "lint": "vue-cli-service lint"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
