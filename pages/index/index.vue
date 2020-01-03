<template>
	<view class="content">
		<view class="bg">
			<view class="background">
				
			</view>
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
			<view class="hot-wrap">
				<view class="hot">
					<view class="recommend">
						<view class="recommend-heading">
							今日推荐
						</view>
						<view class="recommend-list">
							<view class="recommend-goods-wrap" v-for="(item, key) in recommend" :key="key" @tap="goGoods">
								<image :src="item.image" mode=""></image>
								<view class="">¥ {{ item.price }}</view>
							</view>
						</view>
					</view>
					<view class="good-goods">
						<view class="good-goods-heading">
							好物推荐
						</view>
						<view class="good-goods-list">
							<view class="good-goods-wrap" v-for="(item, key) in good_goods" :key="key" @tap="goGoods">
								<image :src="item.image" mode=""></image>
								<view class="">¥ {{ item.price }}</view>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="more">
				<view class="more-contanier">
					<view class="more-wrap" v-for="(item, key) in more" :key="key" @tap="goGoods">
						<image :src="item.image" mode=""></image>
						<view class="more-heading">{{ item.name }}</view>
						<view class="more-price">¥{{ item.price }}</view>
					</view>
				</view>
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
				duration: 500,
				recommend: [
					{'id': 1, 'name': 'ipad pro', 'price': '10066.00', 'image': "../../static/goods-1.png"},
					{'id': 2, 'name': 'iphone xs', 'price': '9888.00', 'image': "../../static/goods-2.png"},
					{'id': 3, 'name': 'air pos', 'price': '1033.00', 'image': "../../static/goods-3.png"},
					{'id': 4, 'name': 'magic mouse', 'price': '698.00', 'image': "../../static/goods-4.png"}
				],
				good_goods: [
					{'id': 1, 'name': 'ipad pro', 'price': '10066.00', 'image': "../../static/goods-1.png"},
					{'id': 2, 'name': 'iphone xs', 'price': '9888.00', 'image': "../../static/goods-2.png"},
					{'id': 3, 'name': 'air pos', 'price': '1033.00', 'image': "../../static/goods-3.png"},
					{'id': 4, 'name': 'magic mouse', 'price': '698.00', 'image': "../../static/goods-4.png"}
				],
				more: [
					{'id': 1, 'name': '都市丽人打底裤', 'price': '69.00', 'image': "../../static/goods/legging.png"},
					{'id': 2, 'name': '金龙鱼调和油', 'price': '59.00', 'image': "../../static/goods/oil.png"},
					{'id': 1, 'name': '都市丽人打底裤', 'price': '69.00', 'image': "../../static/goods/legging.png"},
					{'id': 2, 'name': '金龙鱼调和油', 'price': '59.00', 'image': "../../static/goods/oil.png"},
					{'id': 1, 'name': '都市丽人打底裤', 'price': '69.00', 'image': "../../static/goods/legging.png"},
					{'id': 2, 'name': '金龙鱼调和油', 'price': '59.00', 'image': "../../static/goods/oil.png"},
					{'id': 1, 'name': '都市丽人打底裤', 'price': '69.00', 'image': "../../static/goods/legging.png"},
					{'id': 2, 'name': '金龙鱼调和油', 'price': '59.00', 'image': "../../static/goods/oil.png"}
				]
			}
		},
		onLoad() {

		},
		methods: {
			goGoods: function() {
				uni.navigateTo({
				    url: '/pages/other/goods'
				});
			}
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
				width: 93%;
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
		.hot-wrap{
			margin-top: 20rpx;
			width: 100%;
			height: 350rpx;
			display: flex;
			flex-direction: row;
			justify-content: center;
			.hot{
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				width: 95%;
				height: 350rpx;
				border-radius: 10rpx;
				background-color: white;
				.recommend{
					width: 48%;
					height: 350rpx;
					// background-color: orange;
					.recommend-heading{
						width: 100%;
						height: 50rpx;
						font-size: .8rem;
						line-height: 50rpx;
						text-indent: .5rem;
					}
					.recommend-list{
						width: 100%;
						height: 300rpx;
						display: flex;
						flex-direction: row;
						flex-wrap: wrap;
						justify-content: space-around;
						align-content: stretch;
						.recommend-goods-wrap{
							display: flex;
							flex-direction: column;
							justify-content: center;
							align-content:center;
							align-items:center;
							width: 155rpx;
							height: 145rpx;
							// background-color: #3F536E;
							image{
								width: 95%;
								height: 100rpx;
							}
							view{
								font-size: .6rem;
								font-weight: bold;
							}
						}
					}
				}
				.good-goods{
					width: 48%;
					height: 350rpx;
					// background-color: orange;
					.good-goods-heading{
						width: 100%;
						height: 50rpx;
						font-size: .8rem;
						line-height: 50rpx;
						text-indent: .5rem;
					}
					.good-goods-list{
						width: 100%;
						height: 300rpx;
						display: flex;
						flex-direction: row;
						flex-wrap: wrap;
						justify-content: space-around;
						align-content: stretch;
						.good-goods-wrap{
							display: flex;
							flex-direction: column;
							justify-content: center;
							align-content:center;
							align-items:center;
							width: 155rpx;
							height: 145rpx;
							// background-color: #3F536E;
							image{
								width: 95%;
								height: 100rpx;
							}
							view{
								font-size: .6rem;
								font-weight: bold;
							}
						}
					}
				}		
			}
		}
		.more{
			width: 100%;
			display: flex;
			flex-direction: row;
			justify-content: center;
			margin-top: 20rpx;
			.more-contanier{
				width: 95%;
				display: flex;
				flex-direction: row;
				flex-wrap: wrap;
				justify-content: space-around;
				align-content: stretch;
				.more-wrap{
					border-radius: 10rpx;
					background-color: white;
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-content:space-between;
					align-items:center;
					width: 48%;
					height: 400rpx;
					margin-bottom: 20rpx;
					// background-color: #3F536E;
					image{
						width: 95%;
						height: 300rpx;
					}
					.more-heading{
						font-size: .8rem;
					}
					.more-price{
						font-size: .6rem;
						font-weight: bold;
						color: #d06665;
					}
				}
			}
		}
	}
</style>
