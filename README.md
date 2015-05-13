# slider [![spm version](https://moekit.timo.today/badge/slider)](http://spmjs.io/package/slider)

---

image slider

自然滚动组件，主要的应用场景有 弹窗内长规则、视差滚动页面的内部滚动（竖向滚动），还有应用下载页的介绍缩略图的浏览（水平滚动）

## 调用方式

HTML 示意：
```html
<div class="ui-scroller">
	<ul>
		<li></li>
		<li></li>
		<li></li>
	</ul>
</div>
```

这里定义两个概念：wrapper 和 scroller。wrapper 即外层的包含 DOM，如 `div.ui-scroller`；scroller 即内部滚动的元素（wrapper 的第一个子元素，有且只有一个），如 `<ul>`。组件初始化的时候需要传入 `wrapper ('.ui-scroller')`，类名无限制。实际滚动的是内部的 `scroller ('<ul>')`。对于 scroller 的标签无要求。

调用方式相对简单。需要注意的是：

* scroller 的宽/高必须大于 wrapper 的宽/高才能发生滚动
* 若要水平滚动，则 `scrollY: false`




```js
var Slider = require('slider');
/* 竖直滚动*/
var scroll = new Slider('.ui-scroller', {
	scrollY: true
});

/* 水平滚动 */
var scroll = new Slider('.ui-scroller', {
	scrollY: false,
	scrollX: true
});
```


## 配置说明

<table width="100%">
	<tr>
		<th>name</th>
		<th>type</th>
		<th>default</th>
		<th>description</th>
	</tr>
	<tr>
		<td>scrollX</td>
		<td>boolean</td>
		<td>false</td>
		<td>水平滚动</td>
	</tr>
	<tr>
		<td>scrollY</td>
		<td>boolean</td>
		<td>true</td>
		<td>竖直滚动</td>
	</tr>
	<tr>
		<td>bounce</td>
		<td>boolean</td>
		<td>true</td>
		<td>反弹动画</td>
	</tr>
	<tr>
		<td>scrollTo(x, y)</td>
		<td>function</td>
		<td>-</td>
		<td>滚动到具体坐标</td>
	</tr>
	<tr>
		<td>scrollToElement(el, time, offsetX, offsetY)</td>
		<td>function</td>
		<td>-</td>
		<td>滚动到具体坐标：el: 元素；time：滚动时间(ms)；offsetX：水平偏移量；offsetY：垂直偏移量。</td>
	</tr>
	<tr>
		<td>getComputedPosition()</td>
		<td>function</td>
		<td>-</td>
		<td>返回 scroller 当前的 {x:x, y:y} 坐标轴</td>
	</tr>
	<tr>
		<td>enable()</td>
		<td>function</td>
		<td>-</td>
		<td>全局开关，开启滚动</td>
	</tr>
	<tr>
		<td>disable()</td>
		<td>function</td>
		<td>-</td>
		<td>全局开关，禁止滚动</td>
	</tr>

	<tr>
		<td>refresh()</td>
		<td>function</td>
		<td>-</td>
		<td>刷新当前位置</td>
	</tr>
	<tr>
		<td>destroy()</td>
		<td>function</td>
		<td>-</td>
		<td>销毁对象</td>
	</tr>
</table>

