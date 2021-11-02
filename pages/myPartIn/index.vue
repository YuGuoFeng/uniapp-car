<template>
	<view class="myRegister">
		<!--头像部分 -->
		<uni-card>
			<!-- top -->
			<view class="image_style" @click="toDetail()">
				<view class="top_style">
					<view class="top_1">
						<image style="width: 120rpx; height: 120rpx; background-color: #eeeeee;border-radius: 50%;"
							mode="scaleToFill" :src="src" @error="imageError"></image>
					</view>
					<view class="font_1">
						<view> 测试1</view>
						<view class="style_1"> 111</view>
						<view class="style_2"> 已结束</view>
					</view>
				</view>
		
				<!-- <view class="right">
					编辑资料
				</view> -->
			</view>
		</uni-card>
	</view>
</template>

<script>
	export default {
     onLoad() {
     },
	methods: {
		// 跳转详情
		toDetail(){
			uni.navigateTo({
				url:'/pages/myDetail/index'
			})
		}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #F5F5F5;
	}
	.myRegister{
		.image_style {
			// width: 100%;
			display: flex;
			align-items: center;
			justify-content:start;
		
			.top_style {
				display: flex;
				justify-content: start;
				align-items: center;
		
				.font_1 {
					font: 34rpx;
					margin-left: 30rpx;
					.style_1{
					  font-size: 30rpx;
					  color: #CCCCCC;
					}
					.style_2{
						width: 100rpx;
						height: 30rpx;
						background-color:#CCCCCC;
						border-radius: 5px;
						text-align: center;
						line-height: 30rpx;
						font-size: 24rpx;
						color: #FFFFFF;
					}
				}
			}
		
		
		
		}
	}
</style>
