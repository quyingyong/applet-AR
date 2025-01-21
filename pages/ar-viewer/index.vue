<template>
	<view class="content">
		<coar-scene-component 
			:sceneId="sceneId"  
			@onObjectClick="handleObjectClick" 
			@onTrackerState="handleTrackerState" 
			@onARReady="handleARReady" 
		>
		</coar-scene-component>
	</view>
</template>

<script> 
	export default {
		data() {
			return {
				// 场景ID
				sceneId: ""
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
			}
		}
	}
</script>
<style scoped>
.content {
	padding: 0;
}
</style>