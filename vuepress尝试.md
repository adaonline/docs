B站链接https://www.bilibili.com/video/BV1vb411m7NY/?spm_id_from=333.999.0.0&vd_source=3358cf8e312ec163e4fba57aec0e3591

快速上手(注意目录层级)https://v0.vuepress.vuejs.org/zh/guide/getting-started.html#%E5%85%A8%E5%B1%80%E5%AE%89%E8%A3%85



## 1.软件安装

1. git

2. nodejs 

   最好使用16版本的，16+版本有概率报错

3. yarn

   https://classic.yarnpkg.com/en/docs/install#windows-stable

4. vscode

## 2.vuepress初体验

### 前期准备工作

初始化

```
npm init -y
```

会生成对应的package.json文件

![image-20221118174224697](C:\Users\shangyixin\Desktop\vuepress尝试.assets\image-20221118174224697.png)

```
# 安装为本地依赖项
npm install -D vuepress

# 创建一个 docs 目录
mkdir docs
# 创建一个 markdown 文件
echo '# Hello VuePress' > docs/README.md
```

给package.json里新增，注意添加逗号，英文逗号

```
{
  "scripts": {
    "docs:dev": "vuepress dev docs",
    "docs:build": "vuepress build docs"
  }
}

后面可以执行
yarn docs:dev # 或者：npm run docs:dev，其实就是执行"vuepress dev docs"
yarn docs:build # 或者：npm run docs:build，其实就是执行"vuepress build docs"
```

然后就可以在命令行里执行如下命令进行运行调试(也可以在vscode里安装 npm scripts插件)

```
npm run docs:dev
npm run docs:build
```

### npm scripts插件

![image-20221119151956384](C:\Users\shangyixin\Desktop\vuepress尝试.assets\image-20221119151956384.png)

这时候在资源库管理器里会出现

![image-20221119152013432](C:\Users\shangyixin\Desktop\vuepress尝试.assets\image-20221119152013432.png)

> 此时点击一条命令，会在控制台出现一条命令： auto run docs:dev，并出现报错信息,需要重新设置

设置 --> 用户 --> 扩展 --> Npm --> Package Manager --> 设置成npm（默认是auto）



## 3.案例内容

### 导航栏

官网链接https://vuepress.vuejs.org/zh/theme/default-theme-config.html#%E5%AF%BC%E8%88%AA%E6%A0%8F

我的代码结构如下

其中.vuepress为公共资源部分，把导航栏logo.png放在下面

![image-20221119152206612](C:\Users\shangyixin\Desktop\vuepress尝试.assets\image-20221119152206612.png)

about.md随便填点内容

config.js内容：

```javascript
module.exports = {
    themeConfig: {
        logo: '/assets/img/logo.png',
        nav: [
            { text: 'Home', link: '/' },
            { text: 'About', link: '/about.html' },
            { text: 'External', link: 'https://google.com' },
        ]
    }
  }

```

执行npm run docs:dev，可以查看效果
