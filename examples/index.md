# Demo

---

## Normal usage

````html
<div class="ui-slider" style="height:200px;">
    <ul class="ui-slider-content">
        <li class="current"><span style="background-image:url(http://placehold.sinaapp.com/?640*200)"></span></li>
        <li><span style="background-image:url(http://placehold.sinaapp.com//?640*200)"></span></li>
        <li><span style="background-image:url(http://placehold.sinaapp.com//?640*200)"></span></li>
    </ul>
</div>
````

````javascript
var Slider = require('slider');
var slider = new Slider('.ui-slider', {
    indicator: true,
    autoplay: true,
    interval: 3000
});

/* 滑动开始前 */
slider.on('beforeScrollStart', function(from, to) {
    // from 为当前页，to 为下一页
})

/* 滑动结束 */
slider.on('scrollEnd', function(cruPage) {
    // curPage 当前页
});
````