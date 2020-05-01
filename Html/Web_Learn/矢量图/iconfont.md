一键添加库中
```js
var icons = document.querySelectorAll(".icon-gouwuche1");
var auto_click = function (i) {
	if (i < icons.length) {
		icons.item(i).click();
		auto_click(i + 1);
	}
};
auto_click(0);
```
