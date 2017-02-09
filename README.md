# vue-popup
基于vue2.x的popup弹层


## 使用场景

主要用于移动端位于底部和顶部的弹层，显示信息，并有取消/确定/标题等元素。

## 使用说明

父组件中引入

```
import Popup from './components/Popup'


<Popup ref='top' from='top' @hideFun='hideFun' @showFun='showFun' @cancelFun='cancelFun' @confirmFun='confirmFun' :action-show='true'>
    <div class="test" >
        我是从屏幕上方滑入的
    </div>
</Popup>
<Popup ref='bottom'>
    <div class="test">
        我是从屏幕下方滑入的
    </div>
</Popup>
```
组件中props值：
```
'show':{//控制弹层的显示与隐藏
	type: Boolean,
	default: false
},
'from': {//设置弹层是从顶部还是底部滑出
	type: String,
	default: 'bottom'
},
'actionShow':{//是否显示取消/确定的动作模块
	type: Boolean,
	default: false
},
'title':{//弹层中间的标题
	type: String,
	default: '标题'
},
'cancleText':{//取消操作的文字显示
	type: String,
	default: '取消'
},
'confirmText': {//确定操作的文字显示
	type: String,
	default: '确定'
},
'confirmFun': {//点击确定操作，执行的方法
	type: Function,
	default: function(){}
},
'cancelFun': {//点击取消操作，执行的方法
	type: Function,
	default: function(){}
},
'showFun': {//弹层显示时，执行的方法
	type: Function,
	default: function(){}
},
'hideFun': {//弹层隐藏时，执行的方法
    type: Function,
    default: function(){}
}
```

## 效果截图

![enter description here][1]
[1]: ./src/assets/popup.gif