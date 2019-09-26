<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
    <view class="uni-margin-wrap">
    	<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
    		<swiper-item>
    			<view class="swiper-item uni-bg-red"><image src="/static/logo.png"></image></view>
    		</swiper-item>
    		<swiper-item>
    			<view class="swiper-item uni-bg-green">B</view>
    		</swiper-item>
    		<swiper-item>
    			<view class="swiper-item uni-bg-blue">C</view>
    		</swiper-item>
    	</swiper>
    </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
        background: ['color1', 'color2', 'color3'],
        indicatorDots: true,
        autoplay: true,
        interval: 4000,
        duration: 500,
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
page {
		height: auto;
		min-height: 100%;
	}
  .uni-margin-wrap {
  	width:690upx;
  }
  .swiper {
  	height: 300upx;
  }
  .swiper-item {
  	display: block;
  	height: 300upx;
  	line-height: 300upx;
  	text-align: center;
  }
  
  .swiper-list {
  	margin-top: 40upx;
  	margin-bottom: 0;
  }
  
  .uni-common-mt{
  	margin-top:60upx;
  	position:relative;
  }
	.uni-card {
		box-shadow: none;
	}

	.uni-list:after {
		height: 0;
	}

	.uni-list:before {
		height: 0;
	}
	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50upx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
