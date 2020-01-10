# Introduction

## gitbook 和 github pages 整合

### gitbook 安装和初始化

#### 安装： install gitbook-cli -g

注意：需要安装 gitbook-cli,而不是gitbook

#### 初始化一个gitbook项目：

创建一个目录，例如 mkdir ~/test_gitbook

cd ~/test_gitbook

gitbook init

初始化成功，并生成 README.md 和 SUMMARY.md，README.md是说明文件，SUMMARY.md是目录

修改SUMMER.md文件，生成book目录

```
* [Introduction](README.md)

* [Part I](part1/README.md)
    * [Writing is nice](part1/writing.md)
    * [GitBook is nice](part1/gitbook.md)
* [Part II](part2/README.md)
    * [We love feedback](part2/feedback_please.md)
    * [Better tools for authors](part2/better_tools.md)
```

创建对应的md文件

执行：gitbook serve

执行后可以访问 http://localhost:4000 查看电子书

执行：gitbook build

执行后可以生成 _book文件夹，该文件夹保存了 md文件生成的html文件

#### 安装插件

在 Gitbook 的根目录下创建 book.json 文件，写入相关插件的配置。


## 在github中创建工程

在github 中创建一个工程，用于保存 gitbook代码

git clone https://github.com/yyxtlty/book.github.io.git


在此文件夹中，初始化一个gitbook，执行 gitbook init 和 gitbook build

需要将生成的 _book 传到github 的 gh-pages 分支

```
git subtree push --prefix=_book origin gh-pages

```
上传成功后，就可以在 <https://yyxtlty.github.io/book.github.io/> 中访问了。

<strong>git subtree</strong>

用于实现一个仓库作为其他仓库的子仓库。

常用命令如下：

```
git subtree add   --prefix=<prefix> <commit>
git subtree add   --prefix=<prefix> <repository> <ref>
git subtree pull  --prefix=<prefix> <repository> <ref>
git subtree push  --prefix=<prefix> <repository> <ref>
git subtree merge --prefix=<prefix> <commit>
git subtree split --prefix=<prefix> [OPTIONS] [<commit>]
```



## 参考资料

[搭建 GitBook 并托管到 git pages](http://jalan.space/2018/04/22/2018/2018-04-22-gitbook-and-git-pages/)

[book.json](http://www.chengweiyang.cn/gitbook/customize/book.json.html)

[GitBook 使用教程](https://juejin.im/post/5ad412196fb9a028c22b3a41)
[结合 GitHub Pages 使用 GitBook](https://www.jianshu.com/p/3d03ab330df5)
