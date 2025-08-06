<template>
	<view class="content">
		<coar-scene-component 
			:sceneId="sceneId"  
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
				// 场景ID
				sceneId: "",
				// 场景数据
				sceneInfo: {}
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