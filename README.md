# coki-jpush-expo

为Expo应用集成极光推送(JPush)的配置插件

## 📋 简介

由于极光推送官方不直接支持Expo配置插件模式，本插件通过以下方式实现集成：

```
Expo配置插件 -> prebuild转为原生工作流 -> 自动注入JPush相关代码
```

## 🚀 安装

### 第一步：安装本插件

```bash
npm install coki-jpush-expo
```

### 第二步：安装JPush相关依赖

```bash
npm install jpush-react-native jcore-react-native
```

## 🔧 配置

在`app.json`或`app.config.js`中添加以下配置：

```js
{
  "expo": {
    // 其他配置...
    "plugins": [
      [
        "coki-jpush-expo",
        {
          "appKey": "你的极光推送AppKey", // 必填，从极光推送控制台获取
          "channel": "你的应用渠道"      // 必填，如：production、dev等
        }
      ]
      // 其他插件...
    ]
  }
}
```

## 🔄 生成原生项目

执行以下命令生成原生项目：

```bash
npx expo prebuild
```

这将生成包含所有JPush配置的`android`和`ios`目录。

## ✅ 验证集成

### iOS

1. 使用XCode打开`ios`目录
2. 确认项目中已添加JPush相关配置
3. 运行项目并验证推送功能

### Android

1. 使用Android Studio打开`android`目录
2. 确认项目中已添加JPush相关配置
3. 运行项目并验证推送功能

## 📚 参考文档

- [JPush 集成 Expo详细教程](https://juejin.cn/post/7423235127716659239)
- [极光推送官方文档](https://docs.jiguang.cn/jpush/client/client_plugins)
