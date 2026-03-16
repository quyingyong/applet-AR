<template>
	<view class="content">
		<coar-collection-component 
			:collectionId="collectionId" 
			:toolbar="toolbar" 
			:showBack="showBack"
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
				showBack: false
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