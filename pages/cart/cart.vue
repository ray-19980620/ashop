<template>
	<view class="container">
		<view class="main">
			<view class="goods-wrap" v-for="(item, key) in list" :key="key">
				<view class="goods-box">
					<view class="goods-check-box">
						<view class="check-item">
							<!-- <van-checkbox :value="checked_goods" data-key="checked_goods" :data-index="item.id" checked-color="#e93a3e" @change="onChange"></van-checkbox> -->
							<van-checkbox v-model="item.is_checked" :data-index="item.id" checked-color="#e93a3e" @change="onChange"></van-checkbox>
						</view>
					</view>
					<view class="goods-left">
						<image class="goods-image" :src="item.image" mode=""></image>
					</view>
					<view class="goods-right">
						<view class="right-title">
							<view class="right-title-item">
								{{ item.title }}
							</view>
						</view>
						<view class="right-price-number">
							<view class="right-price">
								￥ {{ item.price }}
							</view>
							<view class="right-number">
								* {{ item.number }}
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="bottom">
			<van-submit-bar
			  :price="price"
			  button-text="提交订单"
			  @submit="onSubmit"
			>
			  <van-checkbox v-model="checked_all" data-key="checked_all" @change="onChangeAll" :style="{marginLeft:'5vw',fontSize:'15px'}" checked-color="#e93a3e">全选</van-checkbox>
			</van-submit-bar>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				price: 0,
				checked_goods: false,
				checked_all: false,
				list: [
					{'id': 1, 'is_checked': false, 'title': '华硕（ASUS）ROG-STRIX-GeForce RTX2080 TI-O11G-GAMING 1350-1665MHz 14000MHz 游戏电竞专业显卡 11G', 'price': 11999.00, 'number': 1, 'image': '/static/goods/2080ti.jpg'},
					{'id': 2, 'is_checked': false, 'title': '联想(Lenovo) LEGION Y9000X 15.6英寸高性能标压轻薄笔记本电脑(i7-9750H 32G 2TSSD 4K UHD)深空灰', 'price': 11999.00, 'number': 1, 'image': '/static/goods/y9000x.jpg'},
				]
			};
		},
		methods: {
			onLoad: function() {
				let _this = this;
				this.list.forEach((item) => {
					_this.price += item.price * 100
				})
			},
			
			onSubmit: function() {
				
			},
			onChange(event) {
				this.list[event.currentTarget.dataset.index - 1]['is_checked'] = event.detail;
				console.log()
			},
			onChangeAll(event) {
				this.checked_all = event.detail;
				this.list.forEach((item) => {
					item.is_checked = event.detail;
				})
			},
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #f7f7f7;
	}
	.container{
		position: relative;
		.main{
			width: 100%;
			//min-height: 100%;
			display: flex;
			flex-direction: column;
			z-index: -1;
			.goods-wrap{
				display: flex;
				justify-content: center;
				margin-top: 20rpx;
				width: 100%;
				height: 250rpx;
				.goods-box {					
					display: flex;
					flex-direction: row;
					width: 95%;
					//background-color: pink;
					border-radius: 10rpx;
					align-items: center;
					background-color: #fff;
					.goods-check-box{
						display: flex;
						flex-direction: column;
						align-items: center;
						justify-content: center;
						width: 7%;
						height: 100%;
					}
					.goods-left{
						width: 33%;
						height: 100%;
						display: flex;
						justify-content: center;
						align-items: center;
						image {
							width: 95%;
							height: 200rpx;
						}
					}
					.goods-right{
						display: flex;
						flex-direction: column;
						align-items: flex-end;
						width: 60%;
						height: 200rpx;
						.right-title{
							display: flex;
							flex-direction: column;
							justify-content: flex-start;
							//align-items: center;
							width: 100%;
							height: 80%;
							.right-title-item{
								font-size: .8rem;
								//background-color: #07C160;
								display: -webkit-box;      //定义为自适应布局    
								text-overflow: ellipsis;  //超出文字用省略号代替
								overflow: hidden;            //多出不分隐藏
								-webkit-box-orient: vertical;    //竖直方向的超出和隐藏
								-webkit-line-clamp: 2;    //设定行数为2
							}
						}
						.right-price-number{
							display: flex;
							flex-direction: row;
							//background-color: #007AFF;
							width: 100%;
							height: 10%;
							font-size: .8rem;
							.right-price{
								color: #ee0a24;
								line-height: 100%;
								width: 40%;
							}
							.right-number{
								line-height: 100%;
								width: 60%;
								text-align: center;
							}
						}
					}
				}
			}
		}
		.bottom{
			width: 100%;
			z-index: 1;
		}
	}
</style>
