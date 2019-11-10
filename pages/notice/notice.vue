<template>
	<view>
		<view class="uni-padding-wrap">
			
			<view class="example-title">
				<view>培训公告（3）</view>
				<view><navigator url="./list">更多 ></navigator></view>
			</view>
			<view class="uni-swiper-msg">
				<view class="uni-swiper-msg-icon">
					<image src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" mode="widthFix"></image>
				</view>
				<swiper vertical="true" autoplay="true" circular="true" interval="3000">
					<swiper-item v-for="(item, index) in msg" :key="index">
						<navigator url="./detail">{{item}}</navigator>
					
					</swiper-item>
				</swiper>
			</view>
			
			
			
			<view class="example-title">
				<view>营销活动（2）</view>
				<view><navigator url="./list">更多 ></navigator></view>
			</view>
			<view class="example-body">
				<uni-notice-bar :single="true" :show-icon="true" text="公告内容1, 适用于无需标题且文字数量不多的情况" />
				<uni-notice-bar :show-icon="true" text="公告内容2, 适用于无需标题且文字数量不多的情况" />
			</view>
			
			
			<view class="example-title">
				<view>产品到期提醒（0）</view>
				<view><navigator url="./list">更多 ></navigator></view>
			</view>
			<view class="example-body">
				<uni-notice-bar :single="true" more-text="查看更多" color="red" background-color="#eee" text="没有最新公告!!!" />
				
			</view>
			
			
			
		</view>
	</view>
</template>
<script>
	
import uniNoticeBar from '@/components/uni-notice-bar/uni-notice-bar.vue'
export default {
	components: {
		uniNoticeBar
	},
	data() {
		return {
			msg : [
				'公告标题1',
				'公告标题2',
				'公告标题3'
			]
		}
	},
	created() {},
	methods: {
		getMore() {
			uni.showToast({
				title: '点击查看更多',
				icon: 'none'
			})
		}
	}
}
	

</script>
<style>
	
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
	
	.example-title__after {
		position: relative;
		color: #031e3c
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
	
	

</style>
