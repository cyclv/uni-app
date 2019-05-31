<template>
	<view>
		<!-- 用户信息 -->
		<view class='user-info wt100 flexrow'>
			<view class='img'>
			  <!-- <image class='wt100' mode='widthFix' src='https://images.unsplash.com/photo-1551334787-21e6bd3ab135?w=640'></image> -->
			</view>
			<view class='right'>
			  <view class='info1' @click="userdt()">感觉真棒  <text>></text></view>
			  <view class='info2'>角色： 彩民</view>
			</view>
		</view>
		<!-- 分类操作 -->
		<view class='user-classify wt100'>
			<view class='info flexlb wt100'>
				<view class='left flexrow'>
					<image src='../../static/integral.png'></image>
					<text>我的积分</text>
				</view>
				<view class='right flexrow'>
					<text class='rt1'>200积分</text>
					<text class='rt2'>></text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			userdt:function(){
				uni.navigateTo({
					url:'/pages/user/userdt/userdt'
				})
			}
		}
	}
</script>

<style>
.user-info{
  height: 250upx;
  background: #FFCC66;
}
.img{
  width: 210upx;
  height: 210upx;
  border: 1upx solid #f5f5f5;
  margin-left: 20upx;
}
.right{margin-left: 80upx;}
.info1{
  margin-top: -40upx;
  font-size: 40upx;
}
.info1 text{
  font-weight: 900;
  margin-left: 20upx;
}
.info2{
  margin-top: 40upx;
  color: #CC0000;
  font-size: 32upx;
}
/* 用户分类操作 */
.user-classify{
  font-size: 32upx;
}
.user-classify .info{
  height: 120upx;
  margin-top: 10upx;
  background: white;
}
.user-classify .left{
  margin-left: 20upx;
}
.user-classify .left text{
  margin-left: 60upx;
}
.user-classify .right{
  margin-right: 20upx;
}
.left image{
  width: 60upx;
  height: 60upx;
}
.user-classify .rt1{
  margin-right: 20upx;
}
.user-classify .rt2{font-weight: 900;}
</style>
