<template>
	<view>
		<van-sidebar v-model="activeKey">
		  <van-sidebar-item v-for="(item, key) in category" :category-id="item.id" :key="key" :title="item.name" />
		</van-sidebar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
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
			change: function(e) {
				console.log(e);
			}
		}
	}
</script>

<style lang="scss">

</style>
