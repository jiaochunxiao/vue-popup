# vue-popup
基于vue2.x的popup弹层

## update

* 2017-02-09 版本1.0.0
* 2017-02-09 版本1.0.1 增加mask点击是否需要关闭popup
* 2017-02-10 版本1.0.1 popup操作区布局方式修改
* 2017-03-08 版本1.0.2 fix warning by[liujianhuanzz](https://github.com/liujianhuanzz)

## 效果截图

![enter description here][1]
[1]: ./src/assets/popup.gif

## 使用场景

主要用于移动端位于底部和顶部的弹层，显示信息，并有取消/确定/标题等元素。

## demo运行

1 git clone

```
git clone https://github.com/jiaochunxiao/vue-popup.git
```
2 进入到仓库文件夹
```
npm install
//或者
cnpm install
```

3
```
npm run dev
```

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

## 后记

公司同事曾经做过基于Vue1.x的组件，受启发，本组件基于Vue2.x，利用vue transition实现popup。
