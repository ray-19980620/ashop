<template>
	<view class="container">
		<view class="container1">
			<view class="head-form">
				<form @submit="formSubmit">
					<view class="uni-form-item uni-column h-input">
						<input type="text" class="uni-input" name="input" placeholder="请输入手机号" />
					</view>
					<view class="uni-form-item uni-column h-input code-block">
						<input type="number" class="uni-input" name="input" placeholder="请输入验证码" />
						<button>获取</button>
					</view>
					<view class="uni-form-item uni-column h-input">
						<input type="password" class="uni-input" name="input" placeholder="请输入密码" />
					</view>
					<view class="uni-form-item uni-column h-input">
						<input type="password" class="uni-input" name="input" placeholder="请再次输入密码" />
					</view>
					<view class="uni-form-item uni-column h-input">
						<input type="password" class="uni-input" name="input" placeholder="请输入支付密码" />
					</view>
					<view class="uni-form-item uni-column h-input">
						<input type="password" class="uni-input" name="input" placeholder="请再次输入支付密码" />
					</view>
					<view class="uni-form-item uni-column h-input">
						<input type="text" class="uni-input" name="input" placeholder="请输入推荐码" />
					</view>
					<view class="uni-btn-v h-button">
						<button form-type="submit">注册</button>
					</view>
				</form>
			</view>
			<view class="head-other">
				<view class="other-left">
					
				</view>
				<view class="other-right" @tap="goLogin">
					去登陆
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
				var formdata = e.detail.value
				uni.showModal({
					content: '表单数据内容：' + JSON.stringify(formdata),
					showCancel: false
				});
			},
			goLogin: function(e) {
				uni.navigateTo({
					url: "login"
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
		.code-block{
			display: flex;
			flex-direction: row;
			input{
				width: 75%;
			}
			button{
				width: 15%;
				background-color: #ff5a00;//transparent
				border: 1rpx solid #ff5a00;
				color: white;
				font-size: .5rem;
				padding: 0;
			}
		}
		.head-form{
			margin-top: 120rpx;
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