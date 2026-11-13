# 又一个 Hexo 主题 hexo-theme-varaint

先感谢[原作者](www.dahuzi.me)，这个主题是我无意逛 wordpress 看见的 感觉很简洁。在争取到作者的同意下 开始了移植工作。

## banner
默认情况下 首页的 banner 每一次加载都会随机变动，如果想更改随机策略 ，到 /theme/hexo-theme-varaint/source/js/script.js:

```javascript
var bannerNode = $('.top-image');
   if(bannerNode.data('enable')){
       var index = parseInt((Math.random() * 4) + 1);
       bannerNode.attr('style','background-image:url(/banner/'+index+'.jpg)');
   }
```

进行更改。

## 文章 banner

如果想给文章添加 banner，可以在文章中添加:

```vim
---
title: Hello World
banner: http://oct8d1mqf.bkt.clouddn.com/2016-10-12-Video%20Background%20-%20Looping%20Cloud%20Animation-00-00-00-000.jpg
---
```


## search
```yaml
search: 
    enable: true #是否启用
    placeholder: Enter Key...
```

## count(网站统计)

统计功能使用[不蒜子](http://service.ibruce.info/)，目前最大的弊端就是官方服务网站不开放注册，所以对于运行了一段时间的网站，不蒜子的数据都是从1开始，没办法设置，只有等后期开放注册之后，登入网站才能对统计计数进行设置。
js代码位置在你的themes/your themes/layout/_partial/footer.ejs底部

```html
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```
_config.yml配置项

```yaml
count: 
    enable: true #是否启用
```

## comments

```yaml
comments:
  #livere_uid:  填写来比力UID
  #disqus_username: your_disqus_username
```

> 在国内的话还是建议大家使用多说，disqus 必须要翻墙。
>
> 多说已经下线换成来比力，注册来比力代码中找到livere_uid填上去即可,效果看我的[博客](https://www.plasf.cn)

## sidebar

```yaml
sidebar: 
  enable: true #是否启用
  menus:
    -
      name: Weibo
      link: http://weibo.com
      target: _blank
```

## social

```yaml
social: 
  -
    name: weibo
    link: http://weibo.com
  -
    name: github
    link: https://github.com
  -
    name: zhihu
    link: https://www.zhihu.com/people
```

## 代码高亮 


### 使用

这里没有使用 Hexo 自带的 `highlight`，而是用了 `google-perttify`，所以请先关闭 `highlight` 在 _config.yml 文件中:

```yaml
highlight:
  enable: false
  line_number: false
  auto_detect: false
  tab_replace:
```

### 更换代码高亮风格

- 高亮风格选择：https://jmblog.github.io/color-themes-for-google-code-prettify/

- 把下载好的 css 文件放在 /theme/hexo-theme-varaint/source/js/google-code-prettify/

- 修改 head.ejs 

```ejs
<%- css('js/google-code-prettify/download.css') %>
```

> 如果不关闭 Hexo 默认的 highlight 代码风格会混乱。



#巴啦啦啦

项目目前没有 page 页面，只有 post 文章页 ，由于原主题没有 category 和 tag 页面 我也在考虑这两个页面到底是加还是不加。

如果你喜欢这个主题 能不能动一动小手 点击下 star , 也欢迎大家 fork 😄 

> 开源项目离不开大家 如果在使用中遇到什么问题，请及时提出来。


