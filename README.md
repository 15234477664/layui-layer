# layui-layer(在vue中引入layer弹框的简易方法)

```html
1. npm i --save layui-layer
```
```html
2、在main.js中引入
import layer from "layui-layer";
```
```html
2、在需要的地方引入且注册
import layer from "layui-layer";
  components: {
    layer
  },
```
```html
3、然后就可以在各个组件中使用layer了
layer.confirm('您是如何看待前端开发？', {
  btn: ['重要','奇葩'] //按钮
    }, function(){
        layer.msg('的确很重要', {icon: 1});
    }, function(){
      layer.msg('也可以这样', {
          time: 20000, //20s后自动关闭
          btn: ['明白了', '知道了']
   });
 });
```
```html
4、在项目中使用loading页
var loading= layer.load(3, {//请求未成功时出现loading页 ,3代表一中效果
    shade: [0.1,'#fff'] //0.1透明度的白色背景
});

layer.close(loading);   //停止loading效果 
```
```html
5，1.5s后消失的提示框
layer.msg("操作成功!",{icon:1,time:1500});//提示框
```
```html
6，询问框
layer.confirm('是否已完成支付？', {//layer弹窗插件
      title:"信息",
      closeBtn: 0,
      btn: ['付款成功','付款失败'] //按钮
  }, function(){
      self.completePay(id);//查询是否支付
      layer.closeAll();
  },function(){
      //...
 });
```
官方地址：http://layer.layui.com/
