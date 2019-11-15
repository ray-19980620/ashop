<template>
	<view class="container">
		<view class="container1">
			<view class="head-image">
				<image :src="image" mode=""></image>
			</view>
			<view class="head-form">
				<form @submit="formSubmit">
					<view class="uni-form-item uni-column h-input">
						<input class="uni-input" name="input" placeholder="请输入手机号" />
					</view>
					<view class="uni-form-item uni-column h-input">
						<input class="uni-input" name="input" placeholder="请输入密码" />
					</view>
					<view class="uni-btn-v h-button">
						<button form-type="submit">登录</button>
					</view>
				</form>
			</view>
			<view class="head-other">
				<view class="other-left">
					忘记密码
				</view>
				<view class="other-right" @tap="goRegister">
					没有账号？立即注册
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				image: "../../static/head-image.png"
			};
		},
		methods:{
			formSubmit: function(e) {
				console.log('form发生了submit事件，携带数据为：' + JSON.stringify(e.detail.value))
				// var formdata = e.detail.value
				// uni.showModal({
				// 	content: '表单数据内容：' + JSON.stringify(formdata),
				// 	showCancel: false
				// });
				uni.navigateTo({
					url: "/pages/index/index"
				})
			},
			goRegister: function(e) {
				uni.navigateTo({
					url: "register"
				})
			}
		}
	}
</script>

<style lang="scss">
	$font-size: .8rem;
	$font-size-small: .7rem;
	.container{
		padding: 30rpx;
	}
	.container1{
		width: 100%;
		height: 100%;
		// background-color: #007AFF;
		width: 100%;
		display: flex;
		flex-direction: column;
		.head-image{
			margin-top: 130rpx;
			display: flex;
			justify-content: center;
			// background-color: #4CD964;
			width: 100%;
			image {
				width: 150rpx;
				height: 150rpx;
				border-radius: 100%;
				align-items: center;
			}
		}
		.head-form{
			margin-top: 80rpx;
			// background-color: #F0AD4E;
			width: 100%;
			view{
				margin-top: 50rpx;
			}
			.h-input{
				input{
					font-size: $font-size;
				}
			}
			.h-button{
				button{
					background: transparent;
					background-color: #ff5a00;
					color: white;
					margin: 0;
					padding: 0;
					border: 0;
					outline: none;
					border-radius: 25rpx;
				}
				button:after{
					border: none;
				}
			}
		}
		.head-other{
			width: 100%;
			margin-top: 20rpx;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			.other-left, .other-right{
				font-size: $font-size-small;
				color: #999;
			}
		}
	}
</style>