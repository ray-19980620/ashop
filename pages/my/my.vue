<template>
	<view class="content">
		<view class="bg">
			<view class="background"></view>
			<view class="top-bar">
				<view class="top-bar-icon">
					<van-icon name="setting-o" />
				</view>
			</view>
			<view class="avatar-bar">
				
			</view>
			<view class="order-bar">
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {

		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	// view{
	// 	z-index: 1;
	// }
	.bg{
		width: 100%;
		display: flex;
		flex-direction: column;
		position: absolute;
		background-color: #f7f7f7;
		z-index: -2;
		.background{
			position: absolute;
			top: -350rpx;
			width: 100%;
			height: 650rpx;
			z-index: -1;
			background-color: #e93a3e;
			border-radius: 50rpx;
		}
		.top-bar{
			width: 100%;
			height: 80rpx;
			background-color: #007AFF;
			// .top-bar-icon{
			// 	width: 10%;
			// 	height: 10%;
			// }
		}
		.avatar-bar{
			width: 100%;
			height: 180rpx;
			background-color: #4CD964;
		}

	}
</style>
