# apache
只能读取根目录，别的都是404，html模板无法渲染, 可能只适合静态页面吧
`brew install nginx`
# php
gd2没有freetype，下载了编译也没用，折腾好久，果断放弃
`brew install php@7.2`

# 顺便说一下phpmyadmin遇到的问题

phpmyadmin5.0已经发布，但是直接运行时有以下两条错误：
- 配置文件现在需要一个短语密码
- $cfg['TempDir'] phpMyAdmin无法缓存模板文件
网上有很多说是权限问题的，我一开始也想到了，但是无济于事，
解决方法如下：
在phpMyAdmin根目录中找到config.sample.inc.php文件，复制一份保存为config.inc.php，
并修改以下内容：
1.`$cfg['blowfish_secret'] = 'qasqw2wefsd2asdfgw'`
2.追加 `$cfg['TempDir'] = '/tmp';`
reference:  
    *[1](https://www.doctype.com.cn/archives/278/)*
    *[2](https://cloud.tencent.com/developer/ask/187917)*
