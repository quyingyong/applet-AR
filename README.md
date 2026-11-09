# 微信小程序插件使用示例（HBuilder版）

插件默认占用主包体积，插件支持放入分包，这样插件就不占用主包体积。详情看：[https://github.com/quyingyong/applet-AR-subpkg-example](https://github.com/quyingyong/applet-AR-subpkg-example) 

关键代码：

```json
"subPackages": [{
	"root": "pkgPlugin",
	"plugins" : {
	  "coar" : {
		  "version" : "11.5.0",
		  "provider" : "wx5024d89e4b208ce6"
	  }
	},
	"pages": []
	// ...
}]
```

> 共创AR微信小程序插件不收取任何费用，所有用户均可直接使用，无限制。

使用中遇到任何问题，请加微信交流，同时欢迎您对服务提出宝贵意见。微信号coar88

网页AR集成文档请移步：https://coar.cn/openapi-doc

这款AR插件是基于最新的 VisionKit 进行开发和封装的小程序AR解决方案，性能逼近原生，体验效果好，简单易用，渲染性能全网第二强（不让用最强）。

该插件轻量小巧，整体代码不到300KB，适合希望在自有小程序中添加AR功能的用户。目前插件已实现的AR功能有：码上AR、平面AR、手势AR、人脸AR、环视AR、图片AR、图片AR+物件检测、多图识别、

引入插件即可使用，免开发。第三方开发工具均适用（原生、UniApp、HBuilder X、Donut、Taro）等。

如果您遇到任何问题，请随时与我们联系。

**下载该代码使用HBuilder X打开，然后将manifest.json文件中mp-weixin节点下的appid改成你自己的即可运行。**

微信小程序插件文档地址：[https://mp.weixin.qq.com/wxopen/plugindevdoc?appid=wx5024d89e4b208ce6&token=&lang=zh_CN](https://mp.weixin.qq.com/wxopen/plugindevdoc?appid=wx5024d89e4b208ce6&token=&lang=zh_CN) 

**注意：该插件需要获取摄像头权限，请登录你的小程序后台-隐私保护指引-填写摄像头权限使用说明。为了 “通过相机画面体验AR空间视觉效果”，...**

**如果您使用多图识别功能，还需要获取陀螺仪权限，请登录你的小程序后台-隐私保护指引-填写陀螺仪权限使用说明。为了 “在您使用多图识别功能时计算手机是否静止以识别图片内容”，...**

### 集成小程序AR插件太难？我们提供集成服务，一次性帮您解决烦恼！ https://mp.weixin.qq.com/s/I1QEIIxlcZI6X5zP_8kI-A

[现在，您只需要专注于自己的业务，AR功能的集成就交给我们！](https://mp.weixin.qq.com/s/I1QEIIxlcZI6X5zP_8kI-A)

