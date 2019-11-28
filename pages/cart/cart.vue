<template>
	<view class="container">
		<view class="main">
			<van-submit-bar
			  :price="3050"
			  button-text="提交订单"
			  @submit="onSubmit"
			>
			  <van-checkbox v-model="checked">全选</van-checkbox>
			  <span slot="tip">
			    你的收货地址不支持同城送, <span>修改地址</span>
			  </span>
			</van-submit-bar>
		</view>
		<view class="bottom">

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.container{
		position: relative;
		.main{
			
		}
		.bottom{
			width: 100%;
			z-index: 1;
		}
	}
</style>
