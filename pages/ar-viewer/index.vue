<template>
	<view class="content">
		<coar-scene-component 
			:sceneId="sceneId"  
			:showFeedback="true" 
			:screenIndicate="screenIndicate" 
			@onObjectClick="handleObjectClick" 
			@onTrackerState="handleTrackerState" 
			@onARReady="handleARReady" 
			@onSceneInfo="handleSceneInfo" 
		>
		</coar-scene-component>
	</view>
</template>

<script> 
	export default {
		data() {
			return {
				// 场景ID：在共创AR平台 “我的场景-场景设置” 中查看和复制对应的场景ID。
				sceneId: "",
				// 当前ID对应的AR场景数据：组件初始化完成以后回调给使用者，可以用于分享信息设置等。
				sceneInfo: {},
				// 屏幕提示： showIndicate（Boolean）是否显示引导提示、showWatermark（Boolean）是否显示水印、
				screenIndicate: {
					showIndicate: true
				}
			}
		},
		computed: {
		},
		onLoad(options) {
			// 接收URL传参=场景ID
			if(options.sceneId) {
				this.sceneId = options.sceneId
			}
		},
		methods: {
			handleObjectClick(e) {
				console.log("物体点击事件", e);
			},
			handleTrackerState(e) {
				console.log("追踪器状态", e);
			},
			handleARReady(e) {
				console.log("AR初始化状态", e);
			},
			// 场景加载完成以后会回调场景数据，可用于分享或记录。
			handleSceneInfo({ detail }) {
				if(detail && detail.sceneName) {
					this.sceneInfo = detail
				}
			}
		}
	}
</script>
<style scoped>
.content {
	padding: 0;
}
</style>