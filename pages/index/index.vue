<template>
	<view class="index">
		<!--头像部分 -->
		<uni-card>
			<!-- top -->
			<view class="image_style">
				<view class="top_style">
					<view class="top_1">
						<image style="width: 120rpx; height: 120rpx; background-color: #eeeeee;border-radius: 50%;"
							mode="scaleToFill" :src="src" @error="imageError"></image>
					</view>
					<view class="font_1">
						悟空-八戒
					</view>
				</view>

				<view class="right">
					编辑资料
				</view>
			</view>
		</uni-card>
		<!--我的登记  -->
		<uni-card>
			<!-- 头部 -->
			<view class="register_style">我的登记</view>
			<!-- 内容 -->
			<view class="content_1">
				<view class="content">
					<view class="iconfont icon-addfollow font_1">
					</view>
					<text class="font_style">
						创建的登记
					</text>
				</view>
				<!-- two -->
				<view class="right" @click="toPartIn()">
					<view class="iconfont icon-zhengque font_1">
					</view>
					<text class="font_style">
						参与的登记
					</text>
				</view>
			</view>
		</uni-card>
		<!-- 创建登记 -->
		<uni-card>
			<!-- 头部 -->
			<view class="register_style">创建登记</view>
			<!-- 内容 -->
			<view class="content_1">
				<view class="content">
					<view style="color: #478DB3;" class="iconfont icon-chuangjian font_1">
					</view>
					<text class="font_style">
						创建登记
					</text>
				</view>
				<!-- two -->
				<view class="right">
					<view style="font-size: 42rpx;margin-bottom: 15rpx;" class="iconfont icon-mobansheji font_1">
					</view>
					<text class="font_style">
						登记模板
					</text>
				</view>
			</view>
		</uni-card>
	</view>
</template>

<script>
	// import UniCard from '@/components/uni-card/uni-card.vue'
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
		// components:{UniCard},
		methods: {
			async getData() {
				console.log('获取数据接口')
				const res = await this.$myRequest({
					url: '',
				})
			},
			// 图片的方法
			imageError: function(e) {
				console.error('image发生error事件，携带值为' + e.detail.errMsg)
			},

			// 我参与的登记
			toPartIn() {
				uni.navigateTo({
					url: '/pages/myPartIn/index'
				})
			}
		}
	}
</script>

<style lang="scss">
	page {
		background-color: #F5F5F5;
	}

	.index {
		.image_style {
			// width: 100%;
			display: flex;
			align-items: center;
			justify-content: space-between;

			.top_style {
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
				font-size: 24rpx;
				line-height: 40rpx;
				padding: 0 15rpx;
				border: 2rpx solid #808080;
				border-radius: 20rpx;
			}

		}

		// 内容部分
		.register_style {
			height: 60rpx;
			line-height: 50rpx;
			border-bottom: 2rpx solid #DCDCDC;
		}

		.content_1 {
			display: flex;
			align-items: center;
			justify-content: space-between;

			.content {
				font-size: 34rpx;
				width: 50%;
				height: 200rpx;
				border-right: 2rpx solid #DCDCDC;
				text-align: center;

				.font_1 {
					margin-top: 50rpx;
					font-size: 50rpx;
					color: #FB954F;

				}

				.font_style {
					margin-top: 10rpx;
					display: block;
				}
			}

			// two
			.right {
				font-size: 34rpx;
				width: 50%;
				height: 200rpx;
				text-align: center;

				.font_1 {
					margin-top: 50rpx;
					font-size: 60rpx;
					color: #20B923;

				}

				.font_style {
					// margin-top: 10rpx;
					display: block;
				}
			}
		}
	}
</style>
