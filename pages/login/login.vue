<template>
	<view class="container">
		<view class="container1">
			<view class="head-image">
				<image :src="image" mode=""></image>
			</view>
			<view class="head-form">
				<form @submit="formSubmit">
					<view class="uni-form-item uni-column h-input">
						<input class="uni-input" name="input" placeholder="用户名/邮箱/手机号" />
					</view>
					<view class="uni-form-item uni-column">
						<input class="uni-input" name="input" placeholder="请输入密码" />
					</view>
					<view class="uni-btn-v h-button">
						<button form-type="submit">Submit</button>
					</view>
				</form>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				image: "../../static/logo.png"
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
			}
		}
	}
</script>

<style lang="scss">
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
			margin-top: 150rpx;
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
			margin-top: 100rpx;
			// background-color: #F0AD4E;
			width: 100%;
			view{
				margin-top: 50rpx;
			}
			.h-input{
				
			}
			.h-button{
				button{
					background: transparent;
					background-color: transparent;
					margin: 0;
					padding: 0;
					border: 0;
					outline: none;
					border-radius: 25rpx;
				}
			}
		}
	}
</style>
