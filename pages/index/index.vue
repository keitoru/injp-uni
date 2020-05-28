<template>
	<view class="container">
		<!-- 搜索框 -->
		<view class="search">
			<input class="uni-input" confirm-type="search" placeholder="键盘右下角按钮显示为搜索" />
		</view>
		
		<!-- banner -->
		<view class="uni-padding-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<swiper class="swiper" 
						:indicator-color="dotColor"
						:indicator-active-color="dotColor"
						:indicator-dots="indicatorDots" 
						:autoplay="autoplay" 
						:interval="interval" 
						:duration="duration">
						<swiper-item>
							<view class="swiper-item uni-bg-red">
								<image src="../../static/image/banner1.png"></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-green">
								<image src="../../static/image/banner1.png"></image>
							</view>
						</swiper-item>
						<swiper-item>
							<view class="swiper-item uni-bg-blue">
								<image src="../../static/image/banner1.png"></image>
							</view>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>	
	</view>
</template>

<script>
	export default {
	    data() {
	        return {
	            background: ['color1', 'color2', 'color3'],
	            indicatorDots: true,
				dotColor: '#F69073',
	            autoplay: true,
	            interval: 2000,
	            duration: 500
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
	        }
	    }
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		background-image: url(../../static/image/home_backgroud.png);
		background-size:100% 100%;
	}
	.search{
		width:688rpx;
		height:64rpx;
		background:rgba(255,255,255,0.3);
		border-radius:8rpx;
	}
</style>
