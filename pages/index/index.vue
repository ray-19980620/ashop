<template>
	<view class="content">
		<view class="bg">
			<view class="top">
				<view class="search">
					<input type="text" value="" />
					<button type="button"> </button>
				</view>
			</view>
			<view class="swiper">
				
			</view>
			<view class="recommend">
				
			</view>
			<view class="good-goods">
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.bg{
		width: 100%;
		display: flex;
		flex-direction: column;
		.top{
			width: 100%;
			background-color: #007AFF;
			.search{
				padding: 20rpx 20rpx 20rpx 20rpx;
				width: 100%;
				display: flex;
				flex-direction: row;
				input{
					width: 80%;
					border-radius: 10rpx;
				}
				button{
					width: 10%;
				}
			}
		}
		.swiper{
			width: 100%;
			background-color: #4CD964;
		}
		.recommend{
			width: 100%;
			background-color: orange;
		}
		.good-goods{
			width: 100%;
			background-color: pink;
		}
	}
</style>
