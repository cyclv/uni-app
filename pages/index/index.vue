<template>
	<view class="content">
		<swiper class="swiper" :autoplay="true" :interval="5000" :duration="2000" circular='true'>
			<swiper-item>
				<image src="../../static/swipe1.jpg" mode="widthFix"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/swipe2.jpg" mode="scaleToFill"></image>
			</swiper-item>
		</swiper>
		<!-- 警告 -->
		<view class='warn wt100 flexct'> 
			<view class='warn-it'>
				<image class='img' src='../../static/warn1.png'></image>
				<text>当前未联机，请扫码连接彩票机！</text>
			</view>
			<view class='warn-it'>
				<image class='img' src='../../static/warn2.png'></image>
				<text>18周岁以下未成年人，不得购买！</text>
			</view>
		</view>
		<!-- 消息 -->
		<view class='message wt100 flexct'>
			<view class='msg-it wt100 flexrow' @click="messagedt()" v-for="item in message" :key="item.id">
				<image src='https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640'></image>
				<view class='text'>{{item.title}}</view>
				<view class='time'>{{item.time}}</view>
			</view>
		</view>
		<view class="" @click="ecode()">获取扫码支持</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				cyclv:'项目uni-app测试',
				message:[{id:1,title:'2018最新彩票资讯',time:'2018-05-03'},{id:2,title:'曹云金购买10元彩票中200万',time:'2019-01-03'}]
			}
		},
		onLoad() {
			//接口请求
			// uni.request({
			// 	url: 'http://dunge.lyworker.com/api/goods/class', //仅为示例，并非真实接口地址。
			// 	success: (res) => {
			// 		console.log(res.data);
			// 		
			// 	}
			// });
			// 获取当前经纬度
			uni.getLocation({
				type: 'wgs84',
				success: function (res) {
					console.log('当前位置的经度：' + res.longitude);
					console.log('当前位置的纬度：' + res.latitude);
				}
			});
			console.log('onload')
		},
		created:function(){
			console.log(1111)
			// 加载中
			uni.showToast({title:'加载中',icon:'loading'})
			uni.hideToast()
		},
		methods: {
			ecode:function(){
				uni.scanCode({
					success: function (res) {
						console.log('条码类型：' + res.scanType);
						console.log('条码内容：' + res.result);
					}
				});
			},
			messagedt:function(){
				console.log('资讯详情')
			}
		}
	}
</script>

<style>	
/* 轮播 */
.swiper{
	width: 750upx;
	height: 480upx;
}
.swiper image{
	width: 100%;
}
/* 信息警告 */
.warn{
  background: #ffcc33;
  font-size: 28upx;
}
.warn .warn-it{
  width: 750upx;
  display: flex;
  align-items: center;
  height: 64upx;
}
.warn .warn-it:first-child{
  border-bottom: 1px solid #f5f5f5;
}
.warn .warn-it .img{
  margin-left: 40upx;
  width: 48upx;
  height: 48upx;
}
.warn .warn-it text{
  margin-left: 20upx;
  color: #CC0000;
}
/* 信息公告 */
.msg-it{
  height: 130upx;
  font-size: 32upx;
  border-bottom: 1upx solid #f5f5f5;
  background: #E4E4E4;
  margin-bottom: 2upx;
}
.msg-it image{
  height: 100upx;
  width: 100upx;
  border-radius: 10upx;
  margin-left: 20upx;
}
.msg-it .text{
  width: 380upx;
  margin-left: 20upx;
  color: #CC0000;
}
.msg-it .time{
  margin-left: 20upx;
  color: #003399;
}
</style>
