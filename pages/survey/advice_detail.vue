<template>
	<view class="content">
		<view class="title">{{title}}</view>
		<view class="art-content">
			<rich-text class="richText" :nodes="strings"></rich-text>
		</view>
	</view>
</template>

<script>
	import apiUrl from '../../common/apiUrl.js';
	
	export default {
		data() {
			return {
				title: '',
				strings : ''
			}
		},
		onLoad:function(e){
			uni.showLoading({
				title:"加载中..."
			})
			console.log(e);
			uni.request({
				url: apiUrl.adviceDetailApi+e.adviceid,
				method: 'GET',
				data: {},
				success: res => {
					console.log(res);
					this.title = res.data.title;
					this.strings = res.data.content;
					uni.hideLoading();
				},
				fail: () => {},
				complete: () => {}
			});
		}
	}
</script>

<style>
	.content{padding:10upx 2%; width: 96%; flex-wrap:wrap;}
	.title{line-height:2em; font-weight:700; font-size:38upx;}
	.art-content{line-height:2em;}
</style>
