<template>	
	<view class="content">
		<van-toast id="van-toast" />
		<view class="bg">
			<view class="background"></view>
			<view class="top-bar">
				<view class="top-bar-icon">
					<van-icon name="setting-o" />
				</view>
			</view>
			<view class="avatar-bar">
				<view class="avatar-left">
					<image class="avatar" :src="avatar" mode=""></image>
				</view>
				<view class="avatar-right">
					<view class="avatar-name">
						{{ nickname }}
					</view>
					<view class="avatar-level">
						<van-tag color="#fff" text-color="#e93a3e" round>LV {{ level }}</van-tag>
					</view>
				</view>
			</view>
			<view class="order-bar">
				<view class="order-bar-inside">
					<view class="order-top">
						<view class="my-order">我的订单</view>
						<view class="my-all-order">查看全部订单 ></view>
					</view>
					<view class="order-hr"></view>
					<view class="order-bottom">
						<view class="order-bottom-block">
							<image class="order-bottom-block-image" src="" mode=""></image>
							<view class="order-bottom-block-name">待付款</view>
						</view>
						<view class="order-bottom-block">
							<image class="order-bottom-block-image" src="" mode=""></image>
							<view class="order-bottom-block-name">待发货</view>							
						</view>
						<view class="order-bottom-block">
							<image class="order-bottom-block-image" src="" mode=""></image>
							<view class="order-bottom-block-name">待收货</view>							
						</view>
					</view>
				</view>
			</view>
			<view class="grid">
				<view class="grid-inside">
					<view class="grid-top">
						
					</view>
					<view class="grid-bottom">
						<van-grid :column-num="3">
						  <van-grid-item
						    v-for="(value) in grid"
						    :key="value.id"
						    :icon="value.icon"
						    :text="value.text"
							:url="url"
							@click="go(value.id)"
						  />
						</van-grid>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import Toast from '../../wxcomponents/vant/dist/toast/toast';
	export default {
		data() {
			return {
				grid: [
					{id: 0, icon: "photo-o", text: "我的下级"},
					{id: 1, icon: "photo-o", text: "佣金记录"},
					{id: 2, icon: "photo-o", text: "公告信息"},
					{id: 3, icon: "photo-o", text: "联系客服"},
					{id: 4, icon: "photo-o", text: "……"},
					{id: 5, icon: "photo-o", text: "……"}
				],
				avatar: "../../static/avatar.jpg",
				nickname: "放羊的星星",
				level: 2
			}
		},
		onLoad() {

		},
		methods: {
			go: function(e) {
				Toast.fail('不要再点啦');return false;
				if (e == 0) {
					uni.switchTab({
						url: "/pages/index/index"
					})
				} else if (e == 1) {
					uni.switchTab({
						url: "/pages/index/index"
					})					
				} else if (e == 2) {
					uni.switchTab({
						url: "/pages/index/index"
					})					
				} else if (e == 3) {
					uni.switchTab({
						url: "/pages/index/index"
					})					
				} else if (e == 4) {
					uni.switchTab({
						url: "/pages/index/index"
					})					
				} else if (e == 5) {
					uni.switchTab({
						url: "/pages/index/index"
					})					
				}
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #f7f7f7;
	}
	.bg{
		width: 100%;
		display: flex;
		flex-direction: column;
		position: absolute;
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
			//background-color: #007AFF;
			display: flex;
			flex-direction: row;
			justify-content: flex-end;
			.top-bar-icon{
				width: 10%;
				height: 100%;
				van-icon{
					width: 100%;
					height: 100%;
					color: #fff;
					font-size: 40rpx;
				}
			}
		}
		.avatar-bar{
			width: 100%;
			height: 180rpx;
			//background-color: #4CD964;
			display: flex;
			flex-direction: row;
			.avatar-left{
				width: 35%;
				height: 100%;
				display: flex;
				flex-direction: row;
				justify-content: center;
				align-items: center;
				.avatar{
					width: 120rpx;
					height: 120rpx;
					border-radius: 50%
				}
			}
			.avatar-right{
				widows: 65%;
				height: 100%;
				display: flex;
				flex-direction: column;
				justify-content: center;
				.avatar-name, .avatar-level{
					color: #fff;
				}
				.avatar-name{
					font-weight: bold;
				}
				.avatar-level{
					//font-size: 25rpx;
				}
			}
		}
		.order-bar{
			//margin-top: 20rpx;
			width: 100%;
			height: 180rpx;
			display: flex;
			flex-direction: row;
			justify-content: center;
			.order-bar-inside{
				width: 95%;
				height: 100%;
				border-radius: 10rpx;
				background-color: #fff;
				.order-top{
					width: 100%;
					height: 25%;
					display: flex;
					flex-direction: row;
					justify-content: space-between;
					font-size: 25rpx;
					.my-order{
						width: 20%;
						height: 100%;
						line-height: 180%;
						text-align: center;
					}
					.my-all-order{
						width: 25%;
						height: 100%;
						line-height: 180%;
						color: #808080;
					}
				}
				.order-hr{
					width: 100%;
					height: 1rpx;
					border-bottom: 1rpx solid #f7f7f7;
				}
				.order-bottom{
					width: 100%;
					height: 75%;
					display: flex;
					flex-direction: row;
					justify-content: space-around;
					align-items: center;
					.order-bottom-block{
						height: 80%;
						width: 25%;
					}
				}
			}
		}
		.grid{
			margin-top: 50rpx;
			width: 100%;
			height: 180rpx;
			display: flex;
			flex-direction: row;
			justify-content: center;
			.grid-inside{
				width: 95%;
				height: 100%;
				border-radius: 35rpx;
				background-color: #999;
				display: flex;
				flex-direction: column;
				.grid-inside-top{
					width: 100%;
					height: 20%;
				}
				.grid-inside-top{
					width: 100%;
					height: 80%;
				}
			}
		}

	}
</style>
