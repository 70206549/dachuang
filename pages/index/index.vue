<template>
	<view class="home">
		<swiper class="swiper" circular autoplay interval="3000" duration="200"
			 indicator-dots indicator-color="rgba(255,255,255,0)" indicator-active-color="rgba(255,255,255,1)">
			<swiper-item class="item">
				<image class="imgs" src="https://shuguo888.top/image/木薯1.jpg" mode=""></image>
			</swiper-item>
			<swiper-item class="item">
				<image class="imgs" src="https://shuguo888.top/image/玉米1.jpg" mode=""></image>
			</swiper-item> 
			<swiper-item class="item">
				<image class="imgs" src="https://shuguo888.top/image/甘蔗1.jpg" mode=""></image>
			</swiper-item>
		</swiper>
		<!-- </view> -->
		<view class="header">
			<view class="texts">识别分类</view>
		</view>
		<view class="body">
			<view class="dt">
				<view class="lefts">
					<image :src="pic1" mode="aspectFit" @click="onclick1"></image>
					<text>玉米</text>
				</view>
			</view>
			<view class="rights">
				<view class="dts">
					<view class="tops">
						<image :src="pic2" mode="aspectFit" @click="onclick2"></image>
						<text>甘蔗</text>
					</view>
				</view>
				<view class="floors">
					<image :src="pic3" mode="aspectFit" @click="onclick3"></image>
					<text>木薯</text>
				</view>
			</view>
		</view>
		<!-- {{obj["data"]["predict_class_name"]}} -->
		<!-- {{srcdata}} -->
		<!-- {{ifdata}} -->
	</view>
</template>
<script>
	export default {
		data() {
			return {
				pics:"https://shuguo888.top/image/相机.png",
				pic1:"https://shuguo888.top/image/相机 (2).png",
				pic2:"https://shuguo888.top/image/相机 (2).png",
				pic3:"https://shuguo888.top/image/相机 (2).png",
				mode: {
				    mode: 'aspectFit',
				    text: '识别结果：'
				},
				ifdata:"",
				srcdata: "",
				classArr:["mushu","yumi","sugarcane"],
				idArr:["class_1","class_2","class_3","class_4","class_5"],
				obj:null,
				image_name: 50000
			}
		},
		onShow() {
			this.pic1="https://shuguo888.top/image/相机 (2).png",
			this.pic2="https://shuguo888.top/image/相机 (2).png",
			this.pic3="https://shuguo888.top/image/相机 (2).png"
			
		},
		onLoad() {
			
		},
		methods: {
			
			onclick1(){
				this.pic1=this.pics
				this.postImg(1)
				
			},
			// D:\Tencent\微信web开发者工具
			onclick2(){
				this.pic2=this.pics
				this.postImg(2)
			},
			
			onclick3(){
				this.pic3=this.pics
				this.postImg(0)
			},
			postImg(e) {
			    // 本地上传图片
			    uni.chooseImage({
			        // 限制上传图片张数
			        count: 1,
			        // 可以指定是原图还是压缩图，默认二者都有
			        sizeType: ['original', 'compressed'],
			        // 从相册选择或则拍照
			        sourceType: ['album', 'camera'],
			        // 成功之后的回调函数
			        success: res => {
			            const tempFilePaths = res.tempFilePaths
			            console.log(tempFilePaths[0])
			            this.src = [...res.tempFilePaths]
			            // this.getNameInfo()
			            this.status = 1
			            uni.uploadFile({
			                url: 'https://shuguo888.top/home/predict', // 上传 api
			                filePath: tempFilePaths[0],
			                name: 'face',
			                formData: {
			                    names: this.image_name,
								class: e // 0-木薯，1-玉米，2-甘蔗
			                },
			                success: (res) => {
			                    let data = JSON.parse(res.data)
			                    console.log(data)
			                    uni.showToast({
			                        title: "上传成功",
			                        icon: "success"
			                    })
			                    this.image_name++
			                    // this.mode.text = "识别结果：" + data.data.predict_class_name\
								this.obj = data
                                // console.log(data)
                                this.topage(e)
			                }
			            })
						
			        }
			    })
			},
            topage(e) {
				this.ifdata=this.idArr[--this.obj["data"]["id"]]
				this.srcdata=this.obj["data"]["img_url"]
				// this.ifdata=this.ifdata-1
				if (this.obj["data"]["predict_class_name"]=="Healthy健康"){
					uni.navigateTo({
						url:"/pages/healthy/healthy"
					})
				}
				else {
                uni.navigateTo({
                	 url:`/pages/detail0/detail0?uid=${this.classArr[e]}&id=${this.ifdata}&url=${this.srcdata}`
                })
				}
				this.pic1="https://shuguo888.top/image/相机.png",
				this.pic2="https://shuguo888.top/image/相机.png",
				this.pic3="https://shuguo888.top/image/相机.png"
            }
        }
	}
</script>

<style lang="scss" scoped>
.home{
	.swiper{
		padding-bottom: 20rpx;
		height: 500rpx;
		width: 750rpx;
		.imgs{
			height: 100%;
			width: 100%;
		}
	}
	.header{
		display: flex;
		width: 750rpx;
		height: 100rpx;
		background: #c8ebfa;
		padding-bottom: 15rpx;
		align-items: center;
		font-size: 45rpx;
		justify-content: center;
		.texts{
			
		}
	}
	.body{
		display: flex;
		width: 750rpx;
		padding: 30rpx;
		.dt{
			padding-right: 10rpx;
			.lefts{
				height: 410rpx;
				width: 360rpx;
				background: #dfeffa;
				border-radius: 10%;
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				image{
					height: 200rpx;
					width: 260rpx;
				}
				text{
					font-size: 35rpx;
					padding-top: 10rpx;
				}
				
			};
		}
		
		.rights{
			height: 400rpx;
			width: 360rpx;
			.dts{
				padding-bottom: 10rpx;
				.tops{
					height: 200rpx;
					background: #ccf4ef;
					border-radius: 5%;
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					image{
						height: 180rpx;
						width: 230rpx;
					}
					text{
						font-size: 35rpx;
						padding-top: 10rpx;
					}
				};
			}
			
			.floors{
				height: 200rpx;
				background: #fadff0;
				border-radius: 5%;
				display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				image{
					height: 180rpx;
					width: 230rpx;
				}
				text{
					font-size: 35rpx;
					padding-top: 10rpx;
				}
			}
		}
	}
}
</style>
