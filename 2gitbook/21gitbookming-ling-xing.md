# 安装GitBook命令行工具

1. 下载nodejs与npm
2. 用nmp安装gitbook：npm install gitbook -g \(-g表示全局安装，不加时表示本地安装，具体差异参见npm\)

   > 装完gitbook后输入gitbook -v 会出现如下信息：

   ![](/assets/2018-02-26_150102.png)

3. 所以想在系统上的任何地方的gitbook命令，需要安装“gitbook CLI”，执行以下命令： npm install -g gitbook-cli

   > gitbook-cli 会自动安装最新版本的gitbook，所以我们可以用npm uninstall gitbook -g 去卸载之前安装的gitbook
   >
   > 之后输入 gitbook -V 查看版本，说明安装成功
   >
   > 注： 推荐直接安装gitbook-cli，而不是先安装gitbook最后再卸载，省去不必要的麻烦

   ![](/assets/2018-02-26_155146.png)

# gitBook-cli相关命令

> gitbook-cli 的基本用法非常简单，基本上就只有两步：
>
> 1. 使用`gitbook init`初始化书籍目录
> 2. 使用`gitbook serve`编译书籍

* ## gitbook init

> 此命令在当前目录下生成README.md与SUMMARY.md文件，且根据SUMMARY.md中的目录结构初始化书籍目录。
>
> README.md 和 SUMMARY.md 是两个必须文件，README.md 是对书籍的简单介绍，SUMMARY.md 是书籍的目录结构

```
  ![](/assets/2018-02-26_160602.png)     ![](/assets/2018-02-26_162958.png)
```

> 接下来往生成的SUMMARY.md文件中添加如下的目录结构：

```markdown
* [Introduction](README.md)
* [Chapter1](chapter1/README.md)
  * [Section1.1](chapter1/section1.1.md)
  * [Section1.2](chapter1/section1.2.md)
* [Chapter2](chapter2/README.md)
```

> 重新运行gitbook init命令

![](/assets/2018-02-26_163356.png) ![](/assets/2018-02-26_163337.png)

* ## gitbook server

> 书籍目录结构创建完成以后，就可以使用gitbook server命令来编译和预览书籍了。
>
> gitbook server命令实际上会首先调用gitbook build命令编译书籍，完成以后打开一个 web 服务器，监听在本地的 4000 端口。
>
> 之后，可以用浏览器打开[http://127.0.0.1:4000](http://127.0.0.1:4000/)查看书籍的效果，如下图：

![](/assets/2018-02-26_165413.png)

> 注： 如果运行之后出现如下错误，只需关闭杀毒软件即可：
>
> Error: ENOENT: no such file or directory, stat 'C:\Users\feiyue\Desktop\gitbooks\\_book\gitbook\gitbook-plugin-fontsettings\fontsettings.js
>
> 到此，你就可以自己在电脑上开始写书了

* ## gitbook build

> 执行 gitbook build 会根据 gitbook init 生成的 md 文件生成对应的 html 文件
>
> gitbook build mygitbook ./output  \(其中output为要输出的目录，不写默认为\_book目录\)

* 注意：执行build可生成书籍的静态网页版，但是从 3.0.0 版起, gitbook build 生成的 website 就不支持 local 打开了（生成本地 html 现在有两个问题：第一，生成的内容没有类似 1.1 1.1.1 之类的章节号；第二，直接打开 html 是不能在点击左边目录时跳转的，报错是跨域。）, 必需要 webserver 开启; 
  实在要完全静态的, 就安装 2.6.7 版吧\( 在有些浏览器下估计不太完美\)
* 上面提到的问题可用 gitbook build --gitbook=2.6.7 解决

* ## gitbook pdf 与 gitbook mobi

> * 这两个命令是用来生成pdf与mobi格式的书籍的，但GitBook 生成 mobi 格式和pdf格式的电子书依赖 Calibre 的 ebook-convert，所以要先安装Calibre
> * 安装Calibre 参考\(这里\)\[https://bookfere.com/tools\#calibre\]

---

# 总结：

> 学会如下命令即可：
>
> 安装gitbook-cli：npm install gitbook-cli -g
>
> 初始化目录：gitbook init
>
> 在浏览器上查看效果： gitbook serve
>
> 生成静态网页版： gitbook build . ./outbook



