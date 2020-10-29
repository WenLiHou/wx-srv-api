# 功能介绍

拉取自[Github](https://github.com/gooking/apifm-wxapi)，在此基础上修改适配自己需求。

# 使用方法

## 安装

```
npm install @muxi/wx-srv-api
```

*如果你的项目还不支持 npm (检查根目录下有没有 package.json 文件)，请先初始化：*

```
npm init
```

## 构建 npm 模块

小程序安装的 npm 模块，还不能直接使用，你需要在开发工具： “工具” --> “构建 npm” ，提示构建成功后，才能使用！

## 小程序调用

1. js文件头部引入插件：

    ```
    const WXAPI = require('apifm-wxapi')
    WXAPI.init('gooking')
    ```

2. js文件直接调用方法：

    ```
    WXAPI.banners().then(res => {
      if (res.code == 0) {
        this.setData({
          banners: res.data
        })
      }
    })
    ```

*上述例子完成了读取后台的 banner 轮播图片的数据，后台发布轮播图，小程序端直接这样简单调用即可~*

# 返回值说明

WXAPI 方法返回数据主要包含 3 个内容： 

1. code 错误码，0 代表操作重构，其他数字均表示错误，具体错误描述请查看 msg；
2. msg 如果上面的code不为0，那么 msg 将会返回具体的错误说明描述
3. data 字段保存了 code 为0 时候的数据，一起你需要的数据，都保存在 data 中返回给你

# 相关资源

[「5分钟使用教程」](https://www.yuque.com/apifm/doc/mdldsd)
[「Demo程序下载」](https://github.com/gooking/apifm-wxapi-demo)
[「功能说明文档」](instructions.md)
[「api接口文档」](https://api.it120.cc/doc.html)

# 授权协议

[MIT License](LICENSE)