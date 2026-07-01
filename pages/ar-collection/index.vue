<template>
	<view class="content">
		<coar-collection-component 
			:collectionId="collectionId" 
			:toolbar="toolbar" 
			:showBack="showBack"
			:setting="setting" 
			@onARReady="handleARReady" 
			@onTracker="handleTracker" 
			@onObjectClick="handleObjectClick"  
			@onCollectionInfo="collectionInfoEvent" 
			>
		</coar-collection-component> 
	</view>
</template>

<script> 
	export default {
		data() {
			return {
				// 合集ID
				collectionId: "",
				toolbar: {},
				showBack: false,
				// 20260701 加、支持传入自定义素材URL地址替换原素材进行展示、
				setting: {
					sceneObjectList: [
						{ "objectName": "图片素材", "objectSrc": "素材地址", "sceneId": "场景ID" },
						{ "objectName": "图片素材", "objectSrc": "素材地址", "sceneId": "场景ID" },
						{ "objectName": "图片素材", "objectSrc": "素材地址", "sceneId": "场景ID" }
					]
				}
			}
		},
		computed: {
		},
		onLoad(options) {
			// 接收URL传参=场景ID
			if(options.collectionId) {
				this.collectionId = options.collectionId
			}
		},
		methods: {
			handleARReady({ detail }) {
				console.log("handleARReady", detail);
			},
			handleTracker({ detail }) {
				console.log("handleTracker", detail);
			},
			handleObjectClick({ detail }) {
				console.log("handleObjectClick", detail);
			},
			collectionInfoEvent({ detail }) {
				console.log("collectionInfoEvent", detail);
			}
		}
	}
</script>
<style scoped>
.content {
	padding: 0;
}
</style>