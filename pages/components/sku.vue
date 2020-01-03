<template name="sku">
	<view class="sku-wrap">
		<view class="shadow" :style="{display: isDisplay}"></view>
		<view class="content" :class="{ animated: isSnimated, slideInUp: isSlideInUp }" :style="{display: isDisplay}">
			fuck
		</view>
	</view>
</template>

<script>
	export default {
		name: "sku",
		data() {
			return {
				isDisplay: 'none',
				isSnimated: false,
				isSlideInUp: false
			};
		},
		methods: { 
			show: function() {
				this.isDisplay = 'block';
				this.isSnimated = true;
				this.isSlideInUp = true;
			},
			test: function() {
				console.log('test')
			}
		}
	}
</script>

<style lang="scss">
.sku{
	height: 100%;
	width: 100%;
	//z-index: 2;
	position: absolute;
	.sku-wrap{
		height: 100%;
		width: 100%;
		position: relative;
		.shadow{
			height: 100%;
			width: 100%;
			z-index: 4;
			position: absolute;
			background: rgba(0, 0, 0, 0.5)
		}
		.content{
			width: 100%;
			height: 65%;
			position: fixed;
			z-index: 5;
			bottom: 0;
			background-color: #007AFF;	
		}
	}
}
</style>
