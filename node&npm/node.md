#### * node官网
http://nodejs.cn/api/

#### * node特点
- 基于V8引擎（谷歌浏览器的引擎）渲染JS的工具或者环境
- 是一个单线程异步无阻塞的I/O操作
- 也是一个event-driven事件驱动（类似于发布订阅或回调函数）

#### * node常用命令

| 命令 | 描述 |
|:--- | :--- |
| node -v | 查看当前node版本 |
| node xxx.js | 执行xxx.js文件 |

#### * node模块
- 内置模块
- 第三方模块（npm安装）
- 自定义模块

###### * commonJS模块化设计思想
     commonJs规范类似于单例模式

| 属性/方法 | 描述 | 类型 |
| :--- | :--- | :--- |
| module.exports | `导出`模块 | object |
| require | `导入`模块 | object |

```javascript
// exports.js

let n = 12,
fn = b => {
    return n * m
},
fn2=c=>{
    return c+n
}

exports.fn = fn //默认重定向到module.exports堆内存中，并给exports的fn属性添加了fn方法

// 备注：
exports={fn:fn} // =>重定向到新的堆内存中，但无法导出
module.exports={fn:fn} //重定向到module.exports堆内存中，可正确导出
module.exports.fn2=fn2 //向新堆内存中加入导出内容
exports.fn3=10 //此时exports和module.exports不是同一个堆内存地址 ，所以无法正确导出

// --------------------------

// require.js
let n=10
    fn=m=>{
        return n/m
    }
let temp=require('./export') //默认从module.exports中导入
//此时导入进来的temp是个对象:{fn:...}  =>[object]

console.log(temp.fn(10)) //120 =>此时执行的是exports.js里的fn
// 备注：导入导出是同步操作，先导入再导出，先执行导入js文件中的代码，再执行导出js文件
```
###### * commonJS模块化特点
- 模块里的代码私有，不会污染全局作用域
- 模块可加载多次，只在第一次加载时运行，之后运行结果被缓存，再次加载从缓存中读取。如需模块再次运行需清除缓存。（为保证性能，应减少模块代码重复执行次数）
- 模块执行顺序为同步加载，按在代码中出现的顺序执行

__dirname:内置变量在当前模块中是绝对路径（推荐），也可以使用相对路径
__firname:绝对路径+文件名

##### * node中的内置模块 
http://nodejs.cn/api/

###### * 创建的web服务需要处理两类请求
1.静态资源文件的请求处理：请求的文件
2.API接口的请求处理：请求的数据

备注： 通过是否包含后缀名来判断请求类型

