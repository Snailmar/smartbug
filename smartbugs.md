## iPhone6 文字颜色线性渐变时,初始显示无效.
css:
``` css
.active{  
            background-image:-webkit-linear-gradient(bottom,red,#fd8403,yellow); 
            -webkit-background-clip:text; 
            -webkit-text-fill-color:transparent; 
        }
```
html:
```html
<div class='active'>iphone6 文字初始不显示</div>
<div>iphone6 文字初始不显示2</div>
```
js:
```javascript
$('div').on('click',function(){   $(this).addClass('active').siblings().removeClass('active);
})
```

## iscroll 5 使用小坑
+ 如果你要监测scrollbar的值,请务必使用iscroll-probe.js;
+ 点击拖动时没有反应,首先禁止默认事件:对拖动元素添加e.preventDefault()或者在iscroll对象里面preventDefault: false
+ iscroll中最好设置 probeType: 2,滚动每隔一定事件触发
+ 记得要在上拉加载更多或者下拉更新的时候调用refresh(),这样能够避免滚动条不更新时导致页面可以滑动到很远的位置但并不能触发iscroll事件.