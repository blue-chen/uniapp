<template>
	<view>
		<view class="type">
			<view class="type-1">类型：</view>
			<view class="type-2">
				<radio-group @change="radioChange">
					<label v-for="(item,index) in items" :key="item.value">
						<view>
							<!-- radio 是单选框，中间的字符串是单项框的名称 ，:checked 为 true 时，单项框被选中-->
							<radio :value="item.value" :checked="index===current">{{item.name}}</radio>
						</view>
					<!-- <view>{{item.name}}</view> -->
					</label>
				</radio-group>
			</view>
		</view>
			<!--  -->
			<view class="goodName">
				<view class="goodName-1">物品名称：</view>
			<!-- <picker class="goodName-2" :range="goods" :value="index" @change="pickerChange">{{goods[index]}}</picker> -->
			<input class="goodName-2" type="text" confirm-type="next" maxlength="5"/>
			</view>
			<!--  -->
			<view class="location">
				<view>地点：</view>
				<input class="locationNameInput" type="text" confirm-type="next" maxlength="10"/>
			</view> 
			<!--  -->
			<view class="contact">
				<view>联系方式：</view>
				<input class="contactWay" type="text" confirm-type="next" placeholder="格式:QQ/微信/手机号码:234832943" maxlength="25"/>
			</view>
			<!--  -->
			<view class="upLoaderBody"><!-- 应该还要再添加一个重新选择按钮,`功能是清空图片 -->
				<view class="upLoaderBody-1">添加物品图片：</view>
				<!--image  存储已选择好的图片 -->
				<!-- <block v-for="(image,index) in imageList" :key="index"> 
					<image class="uploaderImg" :src="imageSrc" :data-src="imageSrc" @tap="previewImage"></image>
				</block> -->
				<!-- view 组件作为 添加图片按钮 -->
				<!-- <view class="uploaderInput" @tap="chooseImage"></view> -->
				<view class="upLoaderBody-2">
					<button class="btnChooseImage" @click="chooseImage">选择图片</button>
					<!-- <button class="btnReselectImage" @click="reselectImage">默认图片</button> -->
					<view class="uploaderImg" v-for="(imageSrc,index) in imageList" :key="index">
					<image :src="imageSrc"  :data-src="imageSrc" @tap="previewImage" mode="scaleToFill" ></image>
					</view>
				</view>
				
				<!-- <view class="cross">
									<view class="transverse-line"></view>
									<view class="vertical-line"></view>
				</view> -->
			</view>
			<!--  -->
			<view class="description">
				<textarea placeholder="添加描述"></textarea>
			</view>
		
	</view>
	
</template>

<script>
	let that;
	
	export default{
		
		data(){
			return{
				items:[{
					value:'lost',
					name:'失物',
				},
				{
					value:'get',
					name:'招领',
				}
				],
				current:0,
				// 
				/* goods:['请选择','手机','笔记本','充电宝','课本','雨伞',], */
				index:0,
				imageList:["/static/imgs/fly.png"],
				/*  或者  '/static/imgs/fly.png' */
				/* imageArray:["/static/imgs/fly.png"], */
				
			}
		},
		onNavigationBarButtonTap() {
			/* uni.navigateTo({
				url:'/pages/about/recruitment-release'
			}); */
			 console.log("点击了自定义按钮");  
		},
		methods:{
			radioChange:function(e){
				for(let i=0;i<this.items.length;i++){
					if(this.items[i].value===e.target.value){
						this.current=i;/* 通过 for 循环比较，知道改变事件操作的单选框是哪个，再通过 index===current 确认选中*/
						/* console.log(this.items[this.current].name); */
						break;
					}
				}
			},
			/* pickerChange:function(e){
				console.log("picker选择改变，当前值为："+e.target.value);
				this.index=e.target.value;
			}, */
			chooseImage:function(){
				that=this;
				uni.chooseImage({
					count:1,
					sizeType:'compressed',
					success:function(res){
						console.log(res);
						
						/* uni.previewImage({
							urls:res.tempFilePaths
						}); */
					that.imageList=res.tempFilePaths;
					console.log(that.imageList);
					/* console.log(this.imageList); */
					}
				});
			},
			previewImage: function(res) {
				uni.previewImage({
					urls:that.imageList
				})
			},
			/* reselectImage:function(){
				that.imageList=this.imageArray;
			} */
		}
	}
</script>

<style>
	.type{
		display: flex;
		background: #F1F1F1;
		margin: 10px 20px;
		height: 120rpx;
	}
	
	.goodName{
		display: flex;
		margin: 10px 20px;
		background: #F1F1F1;
		
	}
	
	.goodName-2{
		width: 70%;
		border: 0.05cm solid black;
		/* text-align: center; */
		border-radius: 5px;
		text-align: center;
	}
	
	.location{
		display: flex;
		margin: 10px 20px;
		background: #F1F1F1;
		
	}
	
	.locationNameInput{
		border: 0.05cm solid black;
		border-radius: 5px;
		background: #F1F1F1;
		margin-left: 36px;
		width:70%;
		text-align: center;
		
	}
	
	.contact{
		display: flex;
		margin: 10px 20px;
		background: #F1F1F1;
	}

	.contactWay{
		border: 0.05cm solid black;
		border-radius: 5px;
		background: #F1F1F1;
		width:70%;
		font-size: 13px;
		text-align: center;
	}
	.upLoaderBody{
		display: flex;
		margin: 10px 20px;
		background: #F1F1F1;
		height: 400rpx;
		
	}
	.btnChooseImage/* .btnReselectImage */{
		font-size: 15px;
		height: 35px;
		border-radius: 8px;
		background: #C8C7CC;
	}
	
	/* .btnReselectImage{
		margin-left: 12px;
	} */
	.upLoaderBody-1{
		width: 38%;
		
	}
	.upLoaderBody-2{
		display: flex;
		flex-wrap: wrap;
	
		width: 60%;
	}
	 .upLoaderBody-2 .uploaderImg{
		height: 76%;/* 高度设为 100% 为何会溢出父元素 */
		width: 100%;
	}
	
	 .upLoaderBody-2 .uploaderImg image{
		width: 100%;
		height: 100%;
		border-radius: 8px;
		background: #C8C7CC;
	}
	
	.description{
		margin: 10px 20px;
		border: 0.05cm solid #000000;
		border-radius: 5px;
		background: #F1F1F1;
	}
	/* .transverse-line {
		height: 100%;
		width: 48%;
		position: absolute;
		border-right: 3upx solid #5A5A5A;
		top: 0;
		left: 0;
	}

 .vertical-line {
	height: 48%;
	width: 100%;
	position: absolute;
	border-bottom: 3upx solid #5A5A5A;
	top: 0;
	left: 0;
} */
</style>
