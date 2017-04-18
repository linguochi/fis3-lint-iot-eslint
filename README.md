# fis3-lint-iot-eslint

基于fis3的eslint自动检测插件

## 安装

```nodejs
npm install fis3-lint-iot-eslint -g
```

## 使用示例
在fis-config.js中配置如下：
```
var config = {
    ignoreFiles:[], // 不需要lint检查的文件，glob格式
    envs: [],
    globals: [],
    rules: {
        // 参考[Configuring ESLint](http://eslint.org/docs/user-guide/configuring)
    }
}


fis.match('*.js', {
    lint: fis.plugin('iot-eslint', config)
})

```
>在变量config中的属性会覆盖插件的默认配置config.json




- 本插件使用的是fis3提供的lint插件扩展点。此扩展点比较特殊，要触发此扩展点需要在`release`的时候添加`-l`参数，所以要打开文件监听，页面自刷新和代码检查需用以下命令：
```
fis3 release -wLl
```