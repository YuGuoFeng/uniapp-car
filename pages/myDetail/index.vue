<template>
	<view class="myDetail">
		<!--测试部分 -->
		<uni-card>
			<!-- top -->
			<view class="top_1">
				测试1
			</view>
			<view class="top_2">
				已结束
			</view>

		</uni-card>

		<!-- two -->
		<uni-card>
			<view class="two_2">
				<!-- 左边 -->
				<view class="top_1 iconfont icon-gantanhaozhong">
				</view>
				<!-- 右边 -->
				<view class="font_style">
					111
				</view>
			</view>
		</uni-card>
		<!-- three -->
		<uni-card>
			<view>
				<view class="one_1">
					登记信息如下(如需要修改, 请联系发起人)
				</view>

				<view class="one_1">
					姓名: 路飞
				</view>
				<view class="one_1">
					手机号: 无
				</view>
				<view class="one_1">
					学校:刚刚
				</view>
				<view class="one_1">
					学号:123456
				</view>
				<view class="one_1">
					单位:单位
				</view>
				<view class="one_1">
					部门: 开发
				</view>
			</view>
		</uni-card>
		<!-- 地图 -->
		<view class="mapStyle">
			<!-- <uni-card> -->
				<map style="width: 100%; height: 300rpx;" :latitude="latitude" :longitude="longitude" :markers="covers">
				</map>
			<!-- </uni-card> -->
		</view>
		<!-- 登記按鈕 -->
		<view class="button_style">
			<button  class= "bottom_1" disabled="true">确认登记</button>
		</view>
		
		<view class="button_style">
			<button  class= "bottom_1" disabled="true">请先登录</button>
		</view>
	    <!--  记录部分-->
		<uni-card>
			<!-- 内容 -->
			<view class="content_1">
				<view class="content" @click="toCamera()">
					<view style="color: #478DB3;" class="iconfont icon-mobansheji font_1">
					</view>
					<text class="font_style">
						扫码登记
					</text>
				</view>
				<!-- two -->
				<view class="right" @click="toRecord()">
					<view style="font-size: 60rpx;font-weight: 600; margin-bottom: -3rpx;" class="iconfont icon-zhengque  font_1">
					</view>
					<text class="font_style">
						我的记录
					</text>
				</view>
			</view>
		
		</uni-card>
	    <!-- 文字部分 -->
		<view class="font_botton">
			<view class="font_one">
				规则
			</view>
			<view class="font_one">
				1.请在2021-11.1 20:36之前完成.
			</view>
			<view class="font_one">
				2.每人仅可参与一次登记
			</view>
			<view class="font_one">
				3.仅发起人可以[修改、删除]登记记录
			</view>
			<view class="font_one">
				2.需要提供（*姓名、手机号、学校、学号、*单位、*部门）信息
			</view>
			
		</view>
	    <!-- 时间 -->
		<view class="time_1">
			——2021-11-1 19:25 发起——
		</view>
		
		<!--名字 -->
		<view class="name_1">
			<image style="width: 120rpx; height: 120rpx; background-color: #eeeeee;border-radius: 50%;"
				mode="scaleToFill" :src="src" @error="imageError"></image>
		 <view >
		 	 郭大侠
		 </view>
		</view>
		<!-- 版本号 -->
		<view class="banben">
			v1.0.0 | 使用说明
		</view>
		
		<view class="banben" style="margin-top:30rpx">
			赞赏开发者
		</view>
		<view class="banben" style="margin-top:35rpx;color:#787878;">
			由腾讯云提供计算服务
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg',
			// latitude: 0,
			// longitude: 0,
			latitude: 32.0438272,
			longitude: 118.7774464,
				covers: [{
				latitude: 32.0438272,
				longitude: 118.7774464,
					// iconPath: '../../../static/location.png'
				}, {
					latitude: 32.0438272,
					longitude: 118.7774464,
					// iconPath: '../../../static/location.png'
				}]
			}
		},
		onLoad() {
			//获取当前位置
			// this.getLocation()
		},
		onShow(){
			//获取当前位置
			// this.getLocation()
		},
		methods: {
          toRecord(){
			  uni.navigateTo({
			      url: '/pages/myRecord/index'
			  });
		  },
		  //获取当前位置
		  getLocation(){
			   uni.getLocation({
			       type: 'wgs84',
			       success: function (res) {
			           console.log('当前位置的经度：' + res.longitude);
					   this.longitude = res.longitude*1
					   console.log(this.longitude,"===========================")
			           console.log('当前位置的纬度：' + res.latitude);
					   this.latitude = res.latitude*1
			       }
			   });
		  },
		  //调用相机扫码
		  toCamera(){
			  console.log("扫描啦")
			  uni.scanCode({
			      success: function (res) {
			          console.log('条码类型：' + res.scanType);
			          console.log('条码内容：' + res.result);
			      }
			  });
		  }
		},
	}
</script>

<style lang="scss">
	page {
		background-color: #F5F5F5;
		padding-bottom: 100rpx;
	}

	.top_1 {
		font-size: 36rpx;
		margin-top: 10rpx;
	}

	.top_2 {
		width: 100rpx;
		height: 30rpx;
		background-color: #CCCCCC;
		border-radius: 5px;
		text-align: center;
		line-height: 30rpx;
		font-size: 24rpx;
		color: #FFFFFF;
		margin: 20rpx 0;

	}

	// 第二部分
	.two_2 {
		display: flex;
		justify-content: start;
		align-items: center;

		.top_1 {
			font-size: 50rpx;
			color: #66A8FB;
		}

		.font_style {
			font: 27rpx;
			color: #CCCCCC;
			margin-left: 10rpx;

		}
	}

	//  第三部分
	.one_1 {
		font-size: 28rpx;
		color: #999999;
		margin-bottom: 15rpx;
	}

	// 地图
	.mapStyle {
		// /deep/ .uni-card__content--pd[data-v-19622063]{
		// 	padding: 0 !important;
		// }
		padding: 0 30rpx;
		margin: 10px 0;
	}  
	// 按鈕部分
	.button_style{
		width: 100%;
		margin: 35rpx 0;
		box-sizing: border-box;
		padding: 0 30rpx;
		.bottom_1{
			background-color: #1AAD19 !important;
			color: #FFFFFF !important;
		}
		// .bottom_2{
		// 	background-color: #FF4746;
		// }
	}
	// 记录部分
	.content_1{
			display: flex;
			align-items: center;
			justify-content: space-between;
			.content{
				font-size:  34rpx;
				width: 50%;
				height: 200rpx;
				border-right: 2rpx solid #DCDCDC;
				text-align: center;
			   
				.font_1{
					margin-top: 50rpx;
					font-size: 50rpx;
					color: orange;
					
				}
				.font_style{
					margin-top: 10rpx;
					display: block;
				}
			}
			// two
			.right{
				font-size:  34rpx;
				width: 50%;
				height: 200rpx;
				text-align: center;
			   
				.font_1{
					margin-top: 50rpx;
					font-size: 60rpx;
					color: #20B923;
					
				}
				.font_style{
					// margin-top: 10rpx;
					display: block;
				}
			}
		}
	// 底下文字部分
	.font_botton{
		margin-top: 20rpx;
		padding: 0 60rpx;
		font-size: 28rpx;
		color: #787878;
		.font_one{
			margin: 10rpx;
		}
	}
	// 时间
	.time_1 {
		width: 100%;
		margin: 150rpx 0;
		text-align: center;
		font-size: 28rpx;
		color: #787878;
	}
	
	// 名字
	.name_1{
		text-align: center;
		font-size: 28rpx;
	}
	//版本号
	.banben{
		margin-top:50rpx;
		text-align: center;
		font-size: 28rpx;
		color: #576B95;
	}
</style>