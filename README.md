
##### 1.创建项目
`vue create <Project Name>`
##### 2.选择配置`Manually select features`  
`babel+ vuex + router`
##### 3.然后一路回车
##### 4.cd `<Project Name>`安装依赖
```
npm i postcss-aspect-ratio-mini postcss-px-to-viewport postcss-write-svg postcss-cssnext postcss-viewport-units cssnano cssnano-preset-advanced postcss-import postcss-url --S
```
#### 5.配置 
1.**cd postcss.config.js**
```
module.exports = {
    "plugins": {
        "postcss-import": {},
        "postcss-url": {},
        "postcss-aspect-ratio-mini": {},
        "postcss-write-svg": {
            utf8: false
        },
        "postcss-cssnext": {},
        "postcss-px-to-viewport": {
            viewportWidth: 750, // (Number) The width of the viewport.
            viewportHeight: 1334, // (Number) The height of the viewport.
            unitPrecision: 3, // (Number) The decimal numbers to allow the REM units to grow to.
            viewportUnit: 'vw', // (String) Expected units.
            selectorBlackList: ['.ignore', '.hairlines'], // (Array) The selectors to ignore and leave as px.
            minPixelValue: 1, // (Number) Set the minimum pixel value to replace.
            mediaQuery: false // (Boolean) Allow px to be converted in media queries.
        },
        "postcss-viewport-units": {},
        "cssnano": {
            preset: "advanced",
            autoprefixer: false,
            "postcss-zindex": false
        },
    }
}
```
2.**cd public/index.html**
```
<script src="//g.alicdn.com/fdilab/lib3rd/viewport-units-buggyfill/0.6.2/??viewport-units-buggyfill.hacks.min.js,viewport-units-buggyfill.min.js"></script>
<script>
    window.onload = function() {
        window.viewportUnitsBuggyfill.init({
            hacks: window.viewportUnitsBuggyfillHacks
        });
    }
</script>
```
#### 运行
`npm run serve`
#### 验证是否编译成功
`cd App.vue` 第19行
```
#nav {
  padding: 30px;
}
```
在浏览器内编译为
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018112013494396.jpg)

- 项目地址【**可直接开发】**: [https://github.com/StavinLi/vueCli3.0_vw.git](https://github.com/StavinLi/vueCli3.0_vw) 记得点赞
- 倘若配置In package.json，则 地址为 [https://github.com/StavinLi/inPackage_vueCli3.0_vw](https://github.com/StavinLi/inPackage_vueCli3.0_vw)
- 具体介绍依赖介绍: [如何在Vue项目中使用vw实现移动端适配](https://www.w3cplus.com/mobile/vw-layout-in-vue.html)
