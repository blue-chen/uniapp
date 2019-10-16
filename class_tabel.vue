<template>
	<view>
		<scroll-view class="class-table" scroll-y="true">
			<!-- 星期栏   -->
			<view class="week">
					<text></text>
					<text>周一</text>
					<text>周二</text>
					<text>周三</text>
					<text>周四</text>
					<text>周五</text>
					<text>周六</text>
					<text>周日</text>
				
			</view>
			<!-- 第1节和第2节及其对应的课表 -->
			<view class="item-12">
				<view class="item-12-1">
					<text class="line1">1</text>
					<text class="line2">2</text>
				</view>
				<view class="item-12-2">
					<text class="11"></text>
					<text class="12"></text>
					<text class="13"></text>
					<text class="14"></text>
					<text class="15"></text>
					<text class="16"></text>
					<text class="17"></text>
				</view>
			</view>
			<!--  第3节和第4节及其对应的课表 -->
			<view class="item-12">
				<view class="item-12-1">
					<text class="line1">3</text>
					<text class="line2">4</text>
				</view>
				<view class="item-12-2">
					<text class="11"></text>
					<text class="12"></text>
					<text class="13"></text>
					<text class="14"></text>
					<text class="15"></text>
					<text class="16"></text>
					<text class="17"></text>
				</view>
			</view>
			<!--  第5节和第6节及其对应的课表 -->
			<view class="item-12">
				<view class="item-12-1">
					<text class="line1">5</text>
					<text class="line2">6</text>
				</view>
				<view class="item-12-2">
					<text class="11"></text>
					<text class="12"></text>
					<text class="13"></text>
					<text class="14"></text>
					<text class="15"></text>
					<text class="16"></text>
					<text class="17"></text>
				</view>
			</view>
			<!--  第7节和第8节及其对应的课表 -->
			<view class="item-12">
				<view class="item-12-1">
					<text class="line1">7</text>
					<text class="line2">8</text>
				</view>
				<view class="item-12-2">
					<text class="11"></text>
					<text class="12"></text>
					<text class="13"></text>
					<text class="14"></text>
					<text class="15"></text>
					<text class="16"></text>
					<text class="17"></text>
				</view>
			</view>
			<!--  第9节和第10节及其对应的课表 -->
			<view class="item-12">
				<view class="item-12-1">
					<text class="line1">9</text>
					<text class="line2">10</text>
				</view>
				<view class="item-12-2">
					<text class="11"></text>
					<text class="12"></text>
					<text class="13"></text>
					<text class="14"></text>
					<text class="15"></text>
					<text class="16"></text>
					<text class="17"></text>
				</view>
			</view>
			
		</scroll-view>
	</view>
</template>

<script>
</script>

<style>
	.week{
		display:flex;
		background:#F1F1F1;
		height: 100rpx;
	}
	
	
	.week  text{
		width: 93rpx;
		text-align: center;
		line-height: 50px;
		height: 100rpx;
		margin-left: 1px;
		font-size: 14px;
	}
	
	.item-12{
		display: flex;
		height: 210rpx;
		margin-bottom: 1px;
	}
	
	.item-12 .item-12-1{
		display: flex;
		flex-wrap: wrap;
		width: 93rpx;
		height: 210rpx;
		margin-left: 1px;
		margin-top: 1px;
	}
	
	.item-12 .item-12-2{
		display: flex;
		height: 210rpx;
	}
	
	.item-12 .item-12-2 text{
		width: 93rpx;
		height: 210rpx;
		background: #BDEF85;
		margin-left: 1px;
		margin-top: 1px;
		/* border-radius: 5px; */
	}
	.item-12 .item-12-1 .line1{
		width:100%;
		height: 105rpx;
		text-align: center;
		line-height: 50px; /*可以设置文字的垂直居中程度*/
		background:#F1F1F1;
		font-size: 14px;
		/* border-top-left-radius: 5px;
		border-top-right-radius: 5px; */
	}
	
	.item-12 .item-12-1 .line2{
		width: 100%;
		height: 105rpx;
		text-align: center;
		line-height: 50px;
		background:#F1F1F1;
		font-size: 14px;
		/* border-bottom-left-radius: 5px;
		border-bottom-right-radius: 5px; */
	}
	
	
</style>
