<template name="sku">
	<view class="sku-wrap">
		<view class="shadow" :class="{ animated: true, fadeIn: turnOn, fadeOut: turnOff}" :style="{display: isDisplay}" @tap="closeSkuAndShadow"></view>
		<view class="content" :class="{ animated: true, slideInUp: turnOn, slideOutDown: turnOff }" :style="{display: isDisplay}">
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
				turnOn: false,
				turnOff: false,
				showBlock: 0
			};
		},
		methods: {
			show: function() {
				var _this = this;
				if (_this.showBlock == 1) {
					return false;
				}
				_this.isDisplay = 'block';
				_this.turnOn = true;
				_this.showBlock = 1;
				setTimeout(function() {
					_this.showBlock = 0;
				}, 1000)
			},
			close: function(e) {
				console.log('close');
				var _this = this;
				_this.turnOn = false;
				_this.turnOff = true;
				setTimeout(function() {
					_this.isDisplay = 'none';
					_this.showBlock = 0;
					_this.turnOff = false;
				}, 1000) 
			},
			closeSkuAndShadow: function() {
				if (this.showBlock == 0) {
					this.close();
				}
			}
		}
	}
</script>

<style lang="scss">
.sku{
	height: 100%;
	width: 100%;
	position: absolute;
	left: -100%;
	.sku-wrap{
		height: 100%;
		width: 100%;
		position: absolute;
		.shadow{
			height: 100%;
			width: 100%;
			z-index: 4;
			position: absolute;
			left: 100%;
			background: rgba(0, 0, 0, 0.4)
		}
		.content{
			width: 100%;
			height: 65%;
			position: absolute;
			left: 100%;
			z-index: 5;
			bottom: 0;
			background-color: #007AFF;	
		}
	}
}
</style>
