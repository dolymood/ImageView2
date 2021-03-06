ImageCrop2
==========

[DEMO](https://rawgit.com/dolymood/ImageCrop2/master/index.html)

ImageCrop2 —— 一个轻量级无依赖的图片裁剪、预览组件。

__针对于手机端特性，模仿 QQ 客户端上传头像的裁切，增加了适用于手机端的图片裁切组件 [ImageCrop4Mobile](https://github.com/dolymood/ImageCrop4Mobile)__

配置说明：

```js
function $(id) {
    return document.getElementById(id)
}
var imgCrop = new ImageCrop({
    sourceContainer: $('source'), // 必选，图片所在的容器元素
    src: '1.jpg', // 必选，图片地址
    imgCls: 'img maxImg', // 可选，图片元素img的classname，默认 img
    preImg: $('prevImg'), // 可选，预览图片元素，已存在img元素
    areaImg: $('areaImg'), // 可选，当前移动框所包含的图片内容
    width: 50, // 可选，默认移动框的宽度，默认 100
    height: 50, // 可选，默认移动框的高度，默认 100
    lockWHScale: true, // 可选，是否锁定宽高比，默认false
    defaultCenter: false, // 可选，是否默认出现在中心位置，默认true
    top: 10, // 可选，默认出现位置的top值（当defaultCenter为false时有效），默认0
    left:10, // 可选，默认出现位置的left值（当defaultCenter为false时有效），默认0
	
    minHeight: 10, // 可选，移动框的最小高度，默认20
    minWidth: 10, // 可选，移动框的最小宽度，默认20

    minImgWidth: 120, // 可选，预览图片的最小宽度，默认150
    minImgHeight: 120, // 可选，预览图片的最小高度，默认150
	
	// 可选，当移动的时候调用
	// 移动的概念是指 选择框的大小、位置 发生改变的时候
    onMove: function() {
		console.log('preInfo::', this.getPreInfo())
        console.log('areaInfo::', this.getAreaInfo())
        console.log('originInfo::', this.getOriginInfo())
	}
});
```

api部分：

```js
var info = imgCrop.getPreInfo(); // 预览图片相关信息
var info1 = imgCrop.getAreaInfo(); // 移动框所包含的的图片相关信息
var info2 = imgCrop.getOriginInfo(); // 得到相对于图片原始大小时位置大小信息
// info info1 info2 均为
/*
 {
    left: 10,
    top: 10,
    width: 200,
    height: 200
 }
 */
//这种形式.
imgCrop.changeImage('2.jpg'); // 更改图片
```

兼容性：

_IE6+，其他浏览器_
