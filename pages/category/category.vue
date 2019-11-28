<template>
	<view>
		<view class="container">
			<van-sidebar class="category-main" v-model="activeKey" @change="change">
			  <van-sidebar-item v-for="(item, key) in category" :category-id="item.id" :key="key" :title="item.name" />
			</van-sidebar>
			<view class="category-son">
				<view class="recommend-goods-wrap" v-for="(item, key) in category_son_show" :key="key">
					<image :src="item.image" mode=""></image>
					<view class="">{{ item.name }}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
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
						{'id': 1, 'name': '风衣', 'image': "../../static/goods/legging.png"},
						{'id': 2, 'name': '卫衣', 'image': "../../static/goods/legging.png"},
						{'id': 1, 'name': '风衣', 'image': "../../static/goods/legging.png"},
						{'id': 2, 'name': '卫衣', 'image': "../../static/goods/legging.png"}
					],
					1: [
						{'id': 1, 'name': '套装裙', 'image': "../../static/goods/legging.png"},
						{'id': 2, 'name': '背带裤', 'image': "../../static/goods/legging.png"}
					],
					2: [
						{'id': 1, 'name': '休闲鞋', 'image': "../../static/goods/legging.png"},
						{'id': 2, 'name': '皮鞋', 'image': "../../static/goods/legging.png"}
					]
				},
				category_son_show: []
			};
		},
		methods: {
			onReady: function() {
				this.showCategorySon();
			},
			change: function(data) { 
				let index = data.mp.detail;
				this.showCategorySon(index);
			},
			showCategorySon: function(index)
			{ 
				let _index = index;
				if (this.category_son.length == 0) {
					return false;
				}
				if (_index == undefined) {
					_index = 0;
				}
				this.category_son_show = this.category_son[_index];
			}
		}
	}
</script>

<style lang="scss">
	.container{
		width: 100%;
		display: flex;
		flex-direction: row;
		.category-main{
			width: 22%;
		}
		.category-son{
			width: 78%;
			display: flex;
			flex-direction: row;
			flex-wrap: wrap;
			justify-content: space-around;
			align-content: flex-start;
			.recommend-goods-wrap{
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-content:center;
				align-items:center;
				width: 175rpx;
				height: 200rpx;
				// background-color: #3F536E;
				image{
					width: 95%;
					height: 150rpx;
				}
				view{
					font-size: .6rem;
					font-weight: bold;
				}
			}
		}
	}
</style>
