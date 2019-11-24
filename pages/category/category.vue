<template>
	<view>
		<van-toast id="van-toast" />
		
		<van-sidebar v-model="activeKey" @change="change">
		  <van-sidebar-item v-for="(item, key) in category" :category-id="item.id" :key="key" :title="item.name" />
		</van-sidebar>
		
		<van-datetime-picker
		  v-model="currentDate"
		  type="datetime"
		  :min-date="minDate"
		  :max-date="maxDate"
		/>
		
		<button type="primary" @tap="showToast">aaa</button>
	</view>
</template>

<script>
	import Toast from '../../wxcomponents/vant/dist/toast/toast';
	export default {
		data() {
			return {
				minHour: 10,
				maxHour: 20,
				minDate: new Date(),
				maxDate: new Date(2019, 10, 1),
				currentDate: new Date(),
				
				activeKey: 0,
				category: [
					{
						'id': 0, 'name': '男装'
					},
					{
						'id': 1, 'name': '女装'
					},
					{
						'id': 2, 'name': '男鞋'
					}
				],
				category_son: {
					0: [
						{'id': 1, 'name': '风衣'},
						{'id': 2, 'name': '卫衣'}
					],
					1: [
						{'id': 1, 'name': '套装裙'},
						{'id': 2, 'name': '背带裤'}
					],
					2: [
						{'id': 1, 'name': '休闲鞋'},
						{'id': 2, 'name': '皮鞋'}
					]
				}
			};
		},
		methods: {
			change: function(data) { 
				let index = data.mp.detail;
				console.log(index);  
				
			},
			showToast: function()
			{
				Toast(123);
				Toast.loading({
				  context:this,
				  message: '加载中...',
				  forbidClick: true,
				  loadingType: 'spinner'
				});
			}
		}
	}
</script>

<style lang="scss">

</style>
