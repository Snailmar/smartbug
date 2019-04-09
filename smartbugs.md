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
+ 使用iscroll请务必注意,滚动区域的内容不能用absolute去定位,这样会导致滚动区域脱离文档流,PC端可能不会受影响,但是移动端会导致页面上拉失效,页面无法进行上拉滑动的问题.
  

## 手机点击按钮或者屏幕时,出现黑影闪烁
PC端没问题,但是手机端测试时,一点击屏幕或特定区域就会闪烁一下,解决方法是给对应点击元素添加
-webkit-tap-highlight-color:transparent;

## 使用input type=date的时候,如果想要显示默认时间,一定要注意value的格式,yyyy-MM-dd,如果格式不对,页面不会显示value值