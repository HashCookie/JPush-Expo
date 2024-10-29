# MX-JPUSH-Expo
expo接入JPUSH脚本

## 工作原理
由于极光推送不支持`expo`模式，因此采用如下方式：
```text
`prebuild`为裸工作流 -> 代码注入
```
参考文档：
- [JPush 集成 Expo](https://juejin.cn/post/7423235127716659239)
- [JPush-expo-config-plugin](https://github.com/RunoMeow/jpush-expo-config-plugin)

## 使用方式

### 1.下载
- 插件下载：
```bash
npm i mx-jpush-expo
```
- `jpush`依赖包 `jpush-react-native` 和 `jpush-core` 下载
```bash
npm install jpush-react-native jcore-react-native --save
```

### 2.集成
在`app.config.js`的`plugin`中注册插件
```js
{
  "expo": {
    // ...
    "plugins": [
      [
        // ...
        "mx-jpush-expo",
        {
          "appKey": "你的极光推送AppKey",
          "channel": "你的极光推送Channel"
        }
      ]
    ]
  }
}
```

## 3.`prebuild`
```bash
expo prebuild
```
这将生成`android`与`ios`文件夹

## 4.检验
- `ios`可以参考：[JPush 集成 Expo](https://juejin.cn/post/7423235127716659239)
- `android`在`android studio`运行`prebuild`完的文件即可
