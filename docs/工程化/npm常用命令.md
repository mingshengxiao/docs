### 升级@vue/cli到最新版本

```npm update -g @vue/cli```

### 查看某个包的全部版本

```npm view @vue/cli versions```

### 查看仓库中未使用的包

当一个项目开发了很久后，总会有很多包曾经安装了，但后面已经没有在代码中使用了却不敢去胡乱删除，这就需要有一个命令可以查找出这些包。找到的不是一个npm命令脚本，而是一个第三方包[npm-check](https://www.npmjs.com/package/npm-check),npm-check可以查找出项目中已过期的，使用错误的和未使用的包。最简单的用法:

```js
  $: npm install -g npm-check

  // 检查代码仓
  $: npm-check
```
