
## 特点

- 上传 webpack 打包后的所有静态资源到七牛云。
- 自动忽略`.html`文件。
- 支持覆盖已上传文件。

基于官方七牛云[Node.js SDK](https://developer.qiniu.com/kodo/sdk/1289/nodejs)。

## 安装

```js
npm install qiniu-upload-plugin --save-dev
```

## 使用方法

```js
const QiniuUploadPlugin = require('./QiniuUploadPlugin');

plugins: [
  new QiniuUploadPlugin({
    publicPath: 'http://cdn.xxx.com', // 七牛云域名，自动替换 publicPath
    accessKey: 'your qiniu accessKey', // 个人中心，秘钥管理，AK
    secretKey: 'your qiniu secretKey', // 个人中心，秘钥管理，SK
    bucket: 'your qiniu bucket', // 存储空间名称
    zone: 'Zone_z2', // 存储地区
    // 可选参数：
    cover: false // 慎用！默认为 false，设置为 true 会覆盖掉已经保存在七牛云上的同名文件。
  })
];
```

## 效果截图

![上传七牛云](https://raw.githubusercontent.com/yhlben/qiniu-upload-plugin/master/screenshots/qiniu-upload.png)

