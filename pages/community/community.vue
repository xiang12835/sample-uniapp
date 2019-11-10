<template>
	<view class="warp">
		
		<view class="example-body">
			<uni-grid :column="3" :show-border="false" :square="false" @change="change">
				<uni-grid-item :hor="35" :ver="-45" marker="badge" type="error" text="">
					<image class="image" src="https://img-cdn-qiniu.dcloud.net.cn/uni-ui/grid-1.png" mode="aspectFill" />
					<text class="text">公告</text>
				</uni-grid-item>
				<uni-grid-item :hor="40" :ver="-55" :img-width="30" marker="image" src="">
					<image class="image" src="https://img-cdn-qiniu.dcloud.net.cn/uni-ui/grid-2.png" mode="aspectFill" />
					<text class="text">调研</text>
				</uni-grid-item>
				<uni-grid-item>
					<image class="image" src="https://img-cdn-qiniu.dcloud.net.cn/uni-ui/gird-3.png" mode="aspectFill" />
					<text class="text">论坛</text>
				</uni-grid-item>
				
			</uni-grid>
		</view>
		
		
			
		<view v-for="item in list" :key="item.id" class="example-box">
			<uni-card :title="item.title" :is-shadow="item.shadow" :note="item.note" :extra="item.extra" :thumbnail="item.thumbnail" @click="clickCard">
			
			
				<view class="content-box">
					{{ item.content }}
				</view>
				
				<view class="time-box">
					{{ item.createTime }}
				</view>
				
				<view class="cate-box">
					# {{ item.categoryStr }}
				</view>
				
				<template v-slot:footer>
					<view class="footer-box">
						<view class="footer-box__item" @click.stop="footerClick('喜欢')"><text> 喜欢 9</text></view>
						<view class="footer-box__item" @click.stop="footerClick('评论')"><text> 评论 4</text></view>
						<view class="footer-box__item" @click.stop="footerClick('收藏')"><text> 收藏</text></view>
					</view>
				</template>
			
			</uni-card>
			
			
			
		</view>
		
		<!-- <view v-for="item in list" :key="item.id" class="example-box">
			<uni-card :is-shadow="true" :title="item.title" mode="title" :thumbnail="item.thumbnail" :extra="item.extra" note="true" @click="clickCard">
			
				<view class="content-box">
					{{ item.content }}
				</view>
				
				<view class="time-box">
					{{ item.createTime }}
				</view>
				
				<view class="cate-box">
					# {{ item.categoryStr }}
				</view>
				
				
				<template v-slot:footer>
					<view class="footer-box">
						<view class="footer-box__item" @click.stop="footerClick('喜欢')"><text> 喜欢 5</text></view>
						<view class="footer-box__item" @click.stop="footerClick('评论')"><text> 评论 9</text></view>
						<view class="footer-box__item" @click.stop="footerClick('收藏')"><text> 收藏</text></view>
					</view>
				</template>
			
			</uni-card>
			
		</view>	 -->
			
			
			
			
			
			
		
		
		
	</view>
</template>

<script>
	import uniGrid from '@/components/uni-grid/uni-grid.vue'
	import uniGridItem from '@/components/uni-grid-item/uni-grid-item.vue'
	import uniCard from '@/components/uni-card/uni-card.vue'
	
	
	
	export default {
		components: {
			uniGrid,
			uniGridItem,
			uniCard
		},
		data() {
			return {
				list: [{
					id: 0,
					title: '森哥',
					content: '你多大了？',
					shadow: true,
					note: 'Tips',
					extra: '热度 90',
					createTime: '2019年11月1日 18:38:21',
					thumbnail: 'https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png',
					categoryStr: '其他'
		
				}, {
					id: 1,
					title: '小璐',
					content: '你炒股嘛？',
					shadow: true,
					note: 'Tips',
					extra: '热度 80',
					createTime: '2019年10月30日 09:23:24',
					thumbnail: 'https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png',
					categoryStr: '财经'
				}, {
					id: 2,
					title: '小倩',
					content: '你是哪里人？',
					shadow: true,
					note: 'Tips',
					extra: '热度 76',
					createTime: '2019年10月29日 13:14:15',
					thumbnail: 'https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png',
					categoryStr: '其他'
				}, {
					id: 3,
					title: '子鱼',
					content: '你有对象吗？',
					shadow: true,
					note: 'Tips',
					extra: '热度 100',
					createTime: '2019年10月23日 20:17:22',
					thumbnail: 'https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png',
					categoryStr: '其他'
				}],
				Tips: ['喜欢', '评论', '分享']
			}
		},
		methods: {
			
			
			toForumDetail() {
				uni.navigateTo({
					url: '../forum/detail'
				});
			},
			
			clickCard() {
				// uni.showToast({
				// 	title: '点击卡片',
				// 	icon: 'none'
				// })
				this.toForumDetail()
				
			},
			footerClick(types) {
				uni.showToast({
					title: types,
					icon: 'none'
				})
			},
			change(e) {
				console.log(e);
				
				let {
					index
				} = e.detail
				console.log(index);
				
				if (index == 0) {
					uni.navigateTo({
						url: '../notice/notice'
					});
				}
				
				if (index == 1) {
					uni.navigateTo({
						url: '../survey/survey'
					});
				}
				
				if (index == 2) {
					uni.navigateTo({
						url: '../forum/forum'
					});
				}
				
				
			}
		}
		
	}
</script>

<style>
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #efeff4
	}

	view {
		font-size: 28upx;
		line-height: inherit
	}

	.example {
		padding: 0 30upx 30upx
	}

	.example-title {
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-size: 32upx;
		color: #464e52;
		padding: 30upx 30upx 30upx 50upx;
		margin-top: 20upx;
		position: relative;
		background-color: #fdfdfd;
		border-bottom: 1px #f5f5f5 solid
	}


	.example-title:after {
		content: '';
		position: absolute;
		left: 30upx;
		margin: auto;
		top: 0;
		bottom: 0;
		width: 6upx;
		height: 32upx;
		background-color: #ccc
	}

	.example .example-title {
		margin: 40upx 0
	}

	.example-body {
		padding: 30upx;
		background: #fff
	}
	
	.example-box {
		margin-bottom: 30upx;
	}
	
	.example-box:last-child {
		margin-bottom: 0;
	}

	.example-info {
		padding: 30upx;
		color: #3b4144;
		background: #fff
	}

	.image {
		width: 50upx;
		height: 50upx;
	}

	.text {
		font-size: 26upx;
		margin-top: 10upx;
	}
	
	/* card */
	.example-body {
		padding: 30upx;
		background: #fff
	}
	
	.content-box {
		padding-top: 20upx;
	}
	
	.footer-box {
		display: flex;
		justify-content: space-between;
		width: 100%;
	
	}
	
	.footer-box__item {
		width: 100%;
		display: flex;
		align-items: center;
	}
	
	.footer-box__item:nth-child(2) {
		justify-content: center;
	}
	
	.footer-box__item:last-child {
		justify-content: flex-end;
	}
	
	
</style>