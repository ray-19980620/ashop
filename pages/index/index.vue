<template>
	<view class="content">
		<view class="bg">
			<view class="top">
				<view class="search">
					<view class="search-wrap">
						<view class="magnifier">
							<image src="../../static/icon/fangda.png" mode=""></image>
						</view>
						<view class="search-input-wrap">
							<input type="text" value="" />
						</view>
						<view class="message"></view>
					</view>
				</view>
			</view>
			<view class="hh_swiper">
				<view class="head-swiper">
					<view class="swiper-wrap">
						<view class="uni-padding-wrap">
							<view class="page-section swiper">
								<view class="page-section-spacing">
									<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
										<swiper-item v-for="(img, key) in background" :key="key" :style="{backgroundImage: 'url(' + img + ')' }">
											<view class="swiper-item"></view>
										</swiper-item>
									</swiper> 
								</view>
							</view>
						</view>
					</view>
				</view>
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
				background: ['../../static/swiper/1.png', '../../static/swiper/2.png', '../../static/swiper/3.png'],
				indicatorDots: true,
				autoplay: true,
				interval: 4000,
				duration: 500
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
		background-color: #ff5a00;
		.top{
			display: flex;
			flex-direction: row;
			justify-content: center;
			width: 100%;
			//background-color: #007AFF;
			padding-top: 20rpx;
			.search{
				padding: 5rpx 10rpx 15rpx 10rpx;
				width: 92%;
				height: 30rpx;
				display: flex;
				flex-direction: row;
				border-radius: 35rpx;
				background-color: #F8F8F8;
				.search-wrap{
					width: 100%;
					display: flex;
					flex-direction: row;
					justify-content: space-between;
					.magnifier{
						width: 40rpx;
						height: 40rpx;
						// background-color: red;
						image{
							display: block;
							width: 40rpx;
							height: 40rpx;
						}
					}
					.search-input-wrap{
						width: 80%;
						height: 40rpx;
						border-radius: 10rpx;
						// background-color: pink;
						input{
							height: 40rpx;
							min-height: 40rpx;
							font-size: 25rpx;
						}		
					}

					.message{
						width: 10%;
						height: 35rpx;
					}
				}
			}
		}
		.hh_swiper{
			width: 100%;
			display: flex;
			flex-direction: row;
			justify-content: center;
			margin-top: 20rpx;
			.head-swiper{
				width: 95%;
				background-color: #4CD964;
				border-radius: 25rpx;
				.swiper-wrap{
					width: 100%;
					.uni-padding-wrap{
						width: 100%;
					}
				}
			}
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
