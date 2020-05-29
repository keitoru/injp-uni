<template>
	<view class="container">
		<!-- 搜索框 -->
		<view class="search">
			<image class="search-icon" src="../../static/image/icon_search.png"></image>
			<text class="search-input">输入商户名、商品名或型号</text>
		</view>
		
		<!-- banner -->
		<view class="banner-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<swiper class="swiper" 
						:indicator-dots="indicatorDots" 
						:autoplay="autoplay" 
						:interval="interval" 
						:duration="duration"
						>
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image src="../../static/image/banner1.png" class="banner-img"></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-green">
								<image src="../../static/image/banner1.png" class="banner-img"></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-blue">
								<image src="../../static/image/banner1.png" class="banner-img"></image>
							</view>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>	
		
		<!-- 入口 -->
		<view class="entrance-section">
			<view class="entrance-item">
				<image src="/static/image/icon_scan_grey.png"></image>
				<text>扫码比价</text>
			</view>
			<view class="entrance-item">
				<image src="/static/image/icon_coupon.png"></image>
				<text>领劵中心</text>
			</view>
			<view class="entrance-item">
				<image src="/static/image/icon_rate.png"></image>
				<text>汇率计算</text>
			</view>
			<view class="entrance-item">
				<image src="/static/image/icon_location.png"></image>
				<text>附近搜索</text>
			</view>
		</view>
		
		<!-- 排行榜 -->
		<view class="rank-section">
			<view class="rank-title">
				热销人气榜
			</view>
			<scroll-view class="scroll-view_H" scroll-x="true">
				<view class="scroll-view-item_H" v-for="(ranking,index) in rankings" :key="index">
					<image :src="ranking.img" mode=""></image>
				</view>
			</scroll-view>
		</view>
		
		<!-- 文章列表 -->
		<view>
			<liuyuno-tabs :tabData="tabs" :defaultIndex="defaultIndex" @tabClick='tabClick' />
		</view>
	</view>
</template>

<script>
	import liuyunoTabs from "@/components/liuyuno-tabs/liuyuno-tabs.vue";
	export default {
	    data() {
	        return {
	            background: ['color1', 'color2', 'color3'],
	            indicatorDots: false,
				dotColor: '#F69073',
	            autoplay: true,
	            interval: 2000,
	            duration: 500,
				scrollTop: 0,
				rankings:[
					{img:'/static/image/banner2.png'},
					{img:'/static/image/banner2.png'},
					{img:'/static/image/banner2.png'},
					{img:'/static/image/banner2.png'},
					{img:'/static/image/banner2.png'},
					{img:'/static/image/banner2.png'},
				],
				tabs:[
					"aa",
					"bb"
				],
				defaultIndex: 0
	        }
	    },
	    methods: {
	        changeIndicatorDots(e) {
	            this.indicatorDots = !this.indicatorDots
	        },
	        changeAutoplay(e) {
	            this.autoplay = !this.autoplay
	        },
	        intervalChange(e) {
	            this.interval = e.target.value
	        },
	        durationChange(e) {
	            this.duration = e.target.value
	        },
			tabClick(e) {
				
			}
		},
		components: {
			liuyunoTabs
		}
	}
</script>

<style lang="scss">
	scroll-view ::-webkit-scrollbar {
		width: 0;
		height: 0;
		background-color: transparent;
	}
	
	page{
		background-color: #F6F6F6;
	}
	.container {
		padding-top: 58rpx;
		font-size: 14px;
		background: #FFF url(../../static/image/home_backgroud.png) no-repeat ;
		background-size:750rpx 406rpx;
	}
	.search{
		width:688rpx;
		height:64rpx;
		background:rgba(255,255,255,0.3);
		border-radius:8rpx;
		margin-left: 28rpx;
	}
	
	.search-icon {
		width: 28rpx;
		height: 28rpx;
		position: relative;
		margin-left: 20rpx;
		margin-top: 18rpx;
	}
	
	.search-input {
		margin-left: 14rpx;
		width:360rpx;
		height:64rpx;
		font-size:28rpx;
		/* font-family:PingFangSC-Regular,PingFang SC; */
		font-weight:400;
		color: #FFFFFF;
		line-height:64rpx;
		letter-spacing:1rpx;
	}
	
	.banner-wrap {
		margin-top: 40rpx;
		margin-left: 28rpx;
		/* width: 696rpx; */
		/* height: 396rpx; */
	}
	
	.banner-img {
		width: 696rpx;
	}
	
	/* 入口 */
	.entrance-section {
		display: flex;
		justify-content: space-around;
		align-items: center;
		flex-wrap:wrap;
		padding: 80rpx 0 30rpx; 
		background: #fff;
		.entrance-item {
			display: flex;
			flex-direction: column;
			align-items: center;
			// font-size: $font-sm + 2upx;
			// color: $font-color-dark;
			font-size: 12upx;
			color: #242323;
		}
		
		image {
			margin-bottom: 14upx;
		}
		
		.entrance-item:nth-child(1) image{
			width: 60rpx;
			height: 58rpx;
		}
		.entrance-item:nth-child(2) image{
			width: 66rpx;
			height: 56rpx;
		}
		.entrance-item:nth-child(3) image{
			width: 66rpx;
			height: 60rpx;
		}
		.entrance-item:nth-child(4) image{
			width: 56rpx;
			height: 64rpx;
		}
	}
	
	
	/* 排行榜 */
	.rank-section {
		margin-top: 20upx;
		height: 344upx;
		padding: 20upx 32upx ;
	}
	
	.rank-title{
		height:44upx;
		line-height:44upx;
		font-size: 16px;
		font-family:PingFangSC-Medium,PingFang SC;
		font-weight: bold;
		color: #242323;
	}
	.scroll-view_H {
		/* 文本不会换行，文本会在在同一行上继续，直到遇到 <br> 标签为止。 */
		white-space: nowrap;
		width: 100%;
	}
	.scroll-view-item_H {
		display: inline-block;
		// width: 100%;
		// height: 224rpx;
		margin: 24upx 8upx;
	}
	.scroll-view-item_H image{
		width: 396upx;
		height: 224rpx;
	}


</style>
