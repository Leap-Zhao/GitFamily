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

      ![](/assets/2018-02-26_160602.png)     ![](/assets/2018-02-26_162958.png)

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
> `gitbook serve`命令实际上会首先调用`gitbook build`编译书籍，完成以后会打开一个 web 服务器，监听在本地的 4000 端口。
>
> 现在，可以用浏览器打开[http://127.0.0.1:4000](http://127.0.0.1:4000/)查看书籍的效果，如下图：



