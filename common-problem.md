## 安装完主题后，页面错乱

A：依次检查主题文件夹名称是否为`handsome`——是否已经安装并且启用主题必要的插件


## 使用EditorMD前台文章首次不加载，刷新一次才能加载

主题pjax与EditorMD的前台解析js有冲突，在该插件的设置界面，将
```
接管前台Markdown解析并启用ToC、TeX科学公式、流程图 Flowchart、时序图 Sequence Diagram 等扩展
```
选择否即可。


## typecho1.1版本编辑器无法解析HTML代码

typecho 1.0原生markdown解析器非常弱，无法解析表格。

typecho 1.1原生markdown解析器非常坑，无法直接解析HTML代码。你可以一劳永逸使用该插件：
[kokororin / typecho-plugin-Parsedown](https://github.com/kokororin/typecho-plugin-Parsedown)

启用该插件后，无需任何设置，自动替换前台文章解析，没有任何问题了。


## 点击首页头像，显示404页面

A：需要新建“时光机”独立页面，具体方法见[独立页面](/page)

## 评论区不能斗图不能显示图片/说说不能显示图片

A：后台 `设置——评论——允许使用的HTML标签和属性` 里面添加html标签
```html
<img src="">
```

## 评论区无法使用markdown语法

A：后台 `设置——评论——在评论中使用Markdown语法(选中)`
后台 `设置——评论——允许使用的HTML标签和属性` 里面添加html标签
```html
<blockquote><pre><code><strong><em><h5><h6><a href title><table><thead><tr><th><tbody><td>
```



## links插件无法启用，显示500错误

A：一般是由于你的`usr/plugin`没有足够的权限导致的。

如果是Linux服务器尝试，在typecho的usr目录下输入此命令：

```bash
sudo chmod -R 777 plugin
```

如果仍有问题，请联系我