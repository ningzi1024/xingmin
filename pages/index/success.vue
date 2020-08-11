<template>
	<view class="success-content">
		<view class="headerImg">
			<view class="img">
				
			</view>
			<text class="notice">核验成功</text>
		</view>
		<view class="btnNext">
			<text class="nextStep" @tap="nextStep">下一步</text>
		</view>
	</view>
</template>

<script>
</script>

<style lang="stylus">
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
