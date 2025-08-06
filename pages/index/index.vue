<template>
	<view class="page">
		<text class="text">
			本插件是基于小程序 VisionKit 进行开发和封装的AR解决方案，目前插件已实现的AR功能有：码上AR、平面AR、手势AR、人脸AR、环视AR、图片AR、图片AR+物件检测、多图识别、
		</text>
		<text class="text">
			本插件对外提供了两种使用方式，一种是跳转到插件页面、一种是使用组件、以下按钮分别对应了不同的功能与介绍，点击即可体验：
		</text>

		<text class="text">
			1、【跳转到插件页面】使用的是手势识别，识别到手势后会展示一个3D模型并跟随手掌移动。
		</text>
		<button @click="gotoPage" style="margin-top: 10px;">1、跳转到插件页面</button>

		<text class="text">
			2、【跳转到插件组件】使用的是平面AR，识别到平面后，点击摆放场景，可放置一个3D模型（玩具车）。
		</text>
		<button @click="gotoComponent" style="margin-top: 10px;">2、跳转到插件组件</button>

		<text class="text">
			3、【跳转到旋转AR】打开摄像头，以手机为中心点，旋转手机即可查看环绕您的两张图片，图片在手机的正前方和右边。
		</text>
		<button @click="gotoRotateView" style="margin-top: 10px;">3、跳转到旋转AR</button>

		<text class="text">
			4、【跳转到人脸AR】使用的是人脸识别，识别到人脸后，在人脸的中间展示一张图片，并跟随人脸移动。
		</text>
		<button @click="gotoFace" style="margin-top: 10px;">4、跳转到人脸AR</button>

		<text class="text">
			5、【图片识别】使用的是图片AR，打开摄像头，识别到指定的图片以后，在图片上叠加展示一个3D模型。
		</text>
		<button @click="gotoImage" style="margin-top: 10px;">5、图片AR</button>

		<view style="display: flex; align-items: center;height: 50px;">
			<text class="link-image" @click="previewImage">点击查看识别图</text>
		</view>

		<text class="text">
			6、【多图识别】打开摄像头，支持识别多张图片（最多3张），每张图所展示的内容不同。
		</text>
		<button @click="gotoCollection" style="margin-top: 10px;">6、多图识别</button>
		<view style="display: flex; align-items: center;height: 50px;">
			<text class="link-image" @click="previewImage">点击查看识别图1</text>
			<text class="link-image" @click="previewImage2">点击查看识别图2</text>
		</view>


		<text style="color: #000000; font-size: 15px; margin-top: 20px;">
			AR场景由【共创AR体验】小程序创建。
		</text>
		<button @click="gotoCoar" style="margin-top: 10px;">跳转到小程序</button>

		<text style="color: #000000; font-size: 15px; margin-top: 20px; color: rgb(221, 17, 68);">
			注意：该插件需要获取摄像头权限，请登录你的小程序后台-隐私保护指引-填写摄像头权限使用说明。为了 “通过相机画面体验AR空间视觉效果”，...
		</text>
		<text style="color: #000000; font-size: 15px; margin-top: 20px; color: rgb(221, 17, 68);">
			如果您使用多图识别功能，还需要获取陀螺仪权限，请登录你的小程序后台-隐私保护指引-填写陀螺仪权限使用说明。为了 “在您使用多图识别功能时计算手机是否静止以识别图片内容”，...
		</text>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {
			// 测试场景ID由他人创建，可能不稳定，请替换为自己的。
		},
		methods: {
			// 跳转到 掌上AR
			gotoPage() {
				wx.navigateTo({
					url: "plugin://coar/coar-scene?sceneId=f34803c207ce482493aaefd4e3f2c581",
					success: function(res) {}
				})
			},
			// 跳转到 平面AR
			gotoComponent() {
				wx.navigateTo({
					url: "/pages/ar-viewer/index?sceneId=c374433e3e04412c80c3643f8851cb4d",
					success: function(res) {}
				})
			},
			// 环视AR
			gotoRotateView() {
				wx.navigateTo({
					url: "plugin://coar/coar-scene?sceneId=00c77ff6e845428da8a27c4c94a1f56b",
					success: function(res) {}
				})
			},
			// 人脸AR 6bab7b5a93814aaba8236f9400677121 
			gotoFace() {
				wx.navigateTo({
					url: "plugin://coar/coar-scene?sceneId=6bab7b5a93814aaba8236f9400677121",
					success: function(res) {}
				})
			}, 
			gotoImage() {
				// 青蛙 
				wx.navigateTo({
					url: "plugin://coar/coar-scene?sceneId=1b578ca68a66422b810183d10361cac3",
					success: function(res) {}
				})
			}, 
			// 多图识别 青蛙、孙悟空、等
			gotoCollection() {
				wx.navigateTo({
					url: "plugin://coar/coar-collection?collectionId=11155",
					success: function(res) {}
				})
			},
			// 跳转到《共创AR体验》小程序
			gotoCoar() {
				wx.navigateToMiniProgram({
					appId: "wx5024d89e4b208ce6",
					success(res) {}
				})
			},
			// 预览图片
			previewImage() {
				wx.previewImage({
					urls: ["https://coar.oss-cn-shenzhen.aliyuncs.com/app/common/image/image-ar-qingwa.jpg"]
				})
			},
			previewImage2() {
				wx.previewImage({
					urls: ["https://coar.oss-cn-shenzhen.aliyuncs.com/app/common/image/image-ar-swk.png"]
				})
			}
		}
	}
</script>

<style>
	/* pages/index/index.wxss */
	.page {
		padding: 20px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding-bottom: 50px;
	}

	.text {
		color: #081828;
		font-size: 16px;
		margin-top: 10px;
	}

	.link-image {
		color: #576B95;
		font-size: 16px;
		margin: 0 10px;
	}
</style>