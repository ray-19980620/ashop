<template>
	<view>
		<view class="hh_swiper">
			<view class="head-swiper">
				<view class="swiper-wrap">
					<view class="uni-padding-wrap">
						<view class="page-section swiper">
							<view class="page-section-spacing">
								<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
									<swiper-item v-for="(img, key) in background" :key="key">
										<image mode="scaleToFill"  :src="img" class="swiper-image" > </image>
									</swiper-item>
								</swiper> 
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="bottom-fixed">
			<van-goods-action>
			  <van-goods-action-icon icon="chat-o" text="客服" />
			  <van-goods-action-icon icon="cart-o" text="购物车" info="5" />
			  <van-goods-action-icon icon="shop-o" text="店铺" info="12" />
			  <van-goods-action-button type="warning" text="加入购物车" />
			  <van-goods-action-button type="danger" text="立即购买" />
			</van-goods-action>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: ['../../static/goods/y9000x.jpg', '../../static/swiper/2.png', '../../static/swiper/3.png'],
				indicatorDots: true,
				autoplay: true,
				interval: 4000,
				duration: 500
			};
		}
	}
</script>

<style lang="scss">
page {
	background-color: #f7f7f7;
}
.hh_swiper{
	width: 100%;
	display: flex;
	flex-direction: row;
	justify-content: center;
	margin-top: 20rpx;
	.head-swiper{
		width: 96%;
		// background-color: #4CD964;
		border-radius: 25rpx;
		.swiper-wrap{
			width: 100%;
			.uni-padding-wrap{
				width: 100%;
			}
		}
	}
}
.swiper {
 	height: 500rpx;
}
.swiper-item {
 	display: block;
    line-height: 500rpx;
 	text-align: center;
}
.swiper-image{  
    width:100%;  
    height:500rpx; 
}
.bottom-fixed{
	// width: 100%;
	// height: 200rpx;
}
</style>
