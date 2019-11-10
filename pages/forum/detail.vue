<template>
    <view>
		
		<uni-card :is-shadow="true" :title="item.title" mode="title" :thumbnail="item.thumbnail" :extra="item.createTime" note="喜欢" @click="clickCard">
		
			<view class="content-box">
				{{ item.content }}
			</view>
			
			
			<!-- <template v-slot:footer>
				<view class="footer-box">
					<view class="footer-box__item" @click.stop="footerClick('喜欢')"><text> 喜欢 5</text></view>
					<view class="footer-box__item" @click.stop="footerClick('评论')"><text> 评论 9</text></view>
					<view class="footer-box__item" @click.stop="footerClick('收藏')"><text> 收藏</text></view>
				</view>
			</template> -->
		
		</uni-card>
		
		
		<view class="uni-padding-wrap">
			

			
			<!-- 评论区 start -->
			<view class="uni-comment">
				<view class="uni-comment-list">
					<view class="uni-comment-face"><image src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" mode="widthFix"></image></view>
					<view class="uni-comment-body">
						<view class="uni-comment-top">
							<text>子鱼</text>
						</view>
						<view class="uni-comment-date">
							<text>2019年11月1日 08:12:09</text>
						</view>
						<view class="uni-comment-content">股市不是长留之地</view>
					</view>
				</view>
				<view class="uni-comment-list">
					<view class="uni-comment-face"><image src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" mode="widthFix"></image></view>
					<view class="uni-comment-body">
						<view class="uni-comment-top">
							<text>森哥</text>
						</view>
						<view class="uni-comment-date">
							<text>2019年10月30日 17:06:39</text>
						</view>
						<view class="uni-comment-content">炒股，已经亏了一万，心脏受不了</view>
					</view>
				</view>
				<view class="uni-comment-list">
					<view class="uni-comment-face"><image src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" mode="widthFix"></image></view>
					<view class="uni-comment-body">
						<view class="uni-comment-top">
							<text>睿哥</text>
						</view>
						<view class="uni-comment-date">
							<text>2019年10月28日 21:26:32</text>
						</view>
						<view class="uni-comment-content">好牛逼的感觉，求带我</view>
						
					</view>
				</view>
				<view class="uni-comment-list">
					<view class="uni-comment-face"><image src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" mode="widthFix"></image></view>
					<view class="uni-comment-body">
						<view class="uni-comment-top">
							<text>小倩</text>
						</view>
						<view class="uni-comment-date">
							<view>2019年10月28日 10:18:41</view><view class="uni-comment-replay-btn">5回复</view>
						</view>
						<view class="uni-comment-content">好孩子，不炒股</view>
						
					</view>
				</view>
			</view>
			<!-- 评论区 end -->
		</view>
		
		
		
    </view>
</template>

<script>
	
	import uniCard from '@/components/uni-card/uni-card.vue'
	
	export default {
		components: {
			uniCard
		},
		
		data() {
			return {
			
				item: {
					id: 3,
					title: '小璐',
					content: '你炒股嘛？',
					shadow: true,
					note: 'Tips',
					extra: '热度 100',
					createTime: '2019年10月23日 20:17:22',
					thumbnail: 'https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png',
					categoryStr: '其他'
				},
			
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
	
	
</style>
