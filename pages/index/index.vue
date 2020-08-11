<template>
	<view>
		<view class="content" v-if="step===1">
			<view class="btn">
				<text class="title" @tap="checkUser">点 击</text>
			</view>
			<view class="notice">
				<text class="title">入住须知</text>
				<text>根据治安要求，入住人必须进行身份核验，一人一证，人证合一。如冒充他人身份或未按实际入住人数如实登记，产生的不良后果，出入住人自行承担。</text>
			</view>
		</view>
		<view class="success-content" v-if="step===2">
			<view class="headerImg">
				<view class="img">
					
				</view>
				<text class="notice">核验成功</text>
			</view>
			<view class="btnNext">
				<text class="nextStep" @tap="nextStep">下一步</text>
			</view>
		</view>
	</view>
</template>

<script>
	const AppData = getApp()
	export default {
		data() {
			return {
				step:1,
				token: AppData.extraData.ertToken
			}
		},
		onLoad(options) {
			
		},
			
		onShow(options){
			
		},
		methods: {
			checkUser(){
				const _this = this;
				uni.navigateToMiniProgram({
						appId: 'wx318893774c9bfdd2',
						path: 'pages/thirdCheck/thirdCheck',
						extraData: {
						ertToken: this.token,
					},
					success: function(res){
						console.log('成功',res);
						_this.step = 2;
					},
					error:function(err){
						console.log('失败',err);
					},
					complete: function(){
						console.log('只是完成');
					}
				})
			},
			nextStep(){
				uni.navigateBackMiniProgram({
				  extraData: {
				    'token': ''
				  },
				  success(res) {
				    // 返回成功
				  }
				})
			}
		}
	}
</script>

<style lang="stylus">
	.content 
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.btn 
			width 525rpx
			height 525rpx
			background #6b717a
			border-radius 50%
			text-align center
			margin-top 100rpx
			.title
				font-size 80rpx
				color #fff
				line-height 500rpx
		.notice
			width 80%
			margin-top 60rpx
			color #999
			display flex
			flex-direction column
			font-size 28rpx
			>.title
				width 100%
				margin-bottom 20rpx
				font-size 32rpx
				color #666
		.btnSubmit
			width 80%;
			margin 80rpx auto 10rpx auto
			background #2bbdf4
			color #FFFFFF
			border-radius 10rpx
	
	.success-content
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding 50rpx 30rpx
		.headerImg
			width 717rpx
			overflow hidden
			.img
				width 717rpx
				height 717rpx
				background #ccc
			.notice
				display block
				font-size 32rpx
				color #595956
				text-align center
				margin 20rpx auto
		.btnNext
			margin-top 100rpx
			width 95%
			height 100rpx
			margin 80rpx auto 10rpx auto
			background-color #70777D
			color #FFFFFF
			text-align center
			line-height 100rpx
			border-radius 10rpx
			font-size 32rpx		
					
</style>
