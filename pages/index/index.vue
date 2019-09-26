<template>
  <view class="content">
    <view class="uni-margin-wrap">
      <swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
        <swiper-item  v-for="list in GametList" :key="list.id">
          <view class="swiper-item">
            <image class="gameImg" :src="list.recommend"></image>
            <view class="uni-text uni-common-pb">{{list.name}}</view>
          </view>
        </swiper-item>
        
      </swiper>
    </view>
  </view>
</template>

<script>
  import http from '@/components/utils/http.js';
  export default {
    data() {
      return {
        title: 'Hello',
        GametList:[],
        background: ['color1', 'color2', 'color3'],
        indicatorDots: true,
        autoplay: true,
        interval: 4000,
        duration: 500,
      }
    },
    onLoad() {
      this.getList();
    },
    methods: {
      getList() {
        let opts = {
          url: '/game/getAllGame',
          method: 'get' 
        };
        let param = {};
        http.httpRequest(opts, param).then(res => {
          console.log(res.data);
          //打印请求返回的数据.data；
          this.GametList = res.data.data;
        }, error => {
          console.log(error);
        })

      }
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
    width: 750upx;
    height: 326upx;
  }

  .swiper {
    height: 326upx;
  }

  .swiper-item {
    display: block;
    height: 326upx;
    line-height: 326upx;
    text-align: center;
  }
  .gameImg{
    width: 750upx;
   height: 326upx;
  }
  .swiper-list {
    margin-top: 40upx;
    margin-bottom: 0;
  }

  .uni-common-mt {
    margin-top: 60upx;
    position: relative;
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
