<template>
	<view class="page">
	  <text style="color: #000000; font-size: 16px; font-weight: bolder;">
		共创AR小程序插件使用示例
	  </text>
	  <text style="color: #000000; font-size: 16px; margin-top: 10px;"> 
	    本插件对外提供了两种使用方式，一个是跳转到插件页面、一个是使用组件、以下按钮分别对应了不同的功能，点击即可体验：
		
		1、【跳转到插件页面】使用的是掌上AR，识别到手掌后展示一个3D模型。
		
		2、【跳转到插件组件】使用的是平面AR，识别到平面后可以放置一个3D模型。
	  </text>
	  <button @click="gotoPage" style="margin-top: 10px;">跳转到插件页面</button>
	  
	  <button @click="gotoComponent" style="margin-top: 10px;">跳转到插件组件</button>
	  
	  <text style="color: #000000; font-size: 15px; margin-top: 20px;">
	    AR场景由【共创AR体验】小程序创建。
	  </text>
	  <button @click="gotoCoar" style="margin-top: 10px;">跳转到小程序</button>
	  
	  <text style="color: #000000; font-size: 15px; margin-top: 20px; color: rgb(221, 17, 68);">
	    注意：该插件需要获取摄像头权限，请登录你的小程序后台-隐私保护指引-填写摄像头权限使用说明。为了 “通过相机画面体验AR空间视觉效果”，...
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
				  url: "/pages/ar-viewer/index?sceneId=8a72d9627c3d4a378eab053216c4d973",
				  success: function(res) {}
				})
			},
			// 跳转到《共创AR体验》小程序
			gotoCoar() {
				wx.navigateToMiniProgram({
					appId: "wx5024d89e4b208ce6",
					success(res) {}
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
}
</style>
