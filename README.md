# UNIAPP 开发随笔
## UNIAPP 简介
uni-app 是一个使用 Vue.js 开发所有前端应用的框架，开发者编写一套代码，可发布到iOS、Android、H5、以及各种小程序（微信/支付宝/百度/头条/QQ/钉钉/淘宝）、快应用等多个平台。
## 版本
* uniapp
* uview-ui 版本 1.7.1
## 疑难杂症
### H5
* 问题：如果在最外层使用 scroll-view 标签，ios微信浏览器会出现滚动BUG，等ios的滚动动画全部结束后页面才能滚动，否则页面会卡住
* 方案：去除最外层 scroll-view 标签，使用原生容器（body）作为滚动容器
------
* 问题：同时使用uview-ui的popup组件和input组件，设置自动获得焦点后，在ios微信浏览器上会导致popup的显示位置不准确
* 方案：取消自动获得焦点，让用户手动点击输入框
------
* 问题：在微信H5页面，video标签在某些型号安卓手机上会出现cover-view失效问题，具体表现为点击播放前cover-view显示在视频上方，点击播放视频会全屏显示，然后退出全屏后，cover-view被video覆盖，无法显示
* 方案：在video标签加上微信特有的属性即可解决
```
x5-video-player-type：h5-page
```
------