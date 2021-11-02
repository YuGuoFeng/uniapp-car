<template>
	<view class="myRecord">
		<!--头像部分 -->
		<uni-card>
			<!-- top -->
			<view class="image_style">
				<view class="top_style">
					<view class="top_1">
						<image style="width: 90rpx; height: 90rpx; background-color: #eeeeee;border-radius: 50%;"
							mode="scaleToFill" :src="src" @error="imageError"></image>
					</view>
					<view class="font_1">
						三七
					</view>
				</view>
		
				<view class="right">
					10-19 18:15
				</view>
			</view>
		    <!-- 内容 -->
			<view class="content">
				<view class="font_1">
					姓名: 索隆
				</view>
				<view class="font_1">
					手机号: 无
				</view>
				<view class="font_1">
					学校: 启明中学
				</view>
				<view class="font_1">
					学号: 123456
				</view>
				<view class="font_1">
					单位:单位
				</view>
				<view class="font_1">
					部门:开发
				</view>
			</view>
		</uni-card>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg'
			}
		},
		onLoad() {
			//获取请求
			// this.getData()
		},
		}
</script>

<style lang="scss">
	page {
		background-color: #F5F5F5;
	}
	.myRecord{
		.image_style {
			// width: 100%;
			display: flex;
			align-items: center;
			justify-content: space-between;
			border-bottom: 1rpx solid #cccccc;
		
			.top_style {
				margin-bottom: 30rpx;
				display: flex;
				justify-content: start;
				align-items: center;
		
				.font_1 {
					font: 34rpx;
					margin-left: 30rpx;
				}
			}
		
			//右边
			.right {
				margin-top: -18rpx;
				font-size: 37rpx;
				padding: 0 15rpx;
				color: #999999;
			}
		
		}
		//内容部分
		.content{
			margin-top: 30rpx;
			font-size: 30rpx;
			color: #999999;
			.font_1{
				margin-bottom: 15rpx;
			}
		}
	}
</style>
