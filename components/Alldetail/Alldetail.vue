<template>
	<view class="detail" >
		<view class="title">{{item.item.classname}}</view>
		<view class="content">
			<view class="shape">
				<text class="title-line"></text>
				<view class="title-text">疾病内容</view>
				<view class="title-row"></view>
			</view>
			<view class=""> </view>
			<view class="text symptom" style="text-indent:30px;">
				{{item.item.symptom}}
			</view>
			<view class="shape">
				<text class="title-line"></text>
				<view class="title-text">解决方案</view>	
				<view class="title-row"></view>
			</view>
			<view class="text solution" style="text-indent:30px;">
				{{item.item.solution}}
			</view>
			<view class="shape">
				<text class="title-line"></text>
				<view class="title-text">预防方案</view>
				<view class="title-row"></view>
			</view>
			<view class="text prevent" style="text-indent:30px;">
				<rich-text :nodes="item.item.prevent"></rich-text>
			</view>
		</view>

	</view>	
</template>

<script>
	export default {
		name:"Alldetail",
		props:{
			item:{
				type:Object,
				default(){
					return {
						img_url:"",
						classname:"疾病名称",
						times:"0000-00-00 00:00:00",
						symptom:"甘蔗，（学名：Saccharum officinarum英文名：Sugarcane）甘蔗属，多年生高大实心草本。根状茎粗壮发达。秆高3-5（-6）米。中国台湾福建、广东、海南、广西、四川、云南等南方热带地区广泛种植。甘蔗适合栽种于土壤肥沃、阳光充足、冬夏温差大的地方。甘蔗是温带和热带农作物，是制造蔗糖的原料，且可提炼乙醇作为能源替代品。全世界有一百多个国家出产甘蔗，最大的甘蔗生产国是巴西、印度和中国。甘蔗中含有丰富的糖分、水分，还含有对人体新陈代谢非常有益的各种维生素、脂肪、蛋白质、有机酸、钙、铁等物质，主要用于制糖，表皮一般为紫色和绿色两种常见颜色，也有红色和褐色，但比较少见。",
						solution:"解决方案,甘蔗属，多年生高大实心草本。根状茎粗壮发达。秆高3-5（-6）米。中国台湾、福建、广东南、广西、四川、云南等南方热带地区广泛种植。甘蔗适合栽种于土壤肥沃、阳光充足、冬夏温差大的地方。甘蔗是温带和热带农作物，是制造蔗糖的原料，且可提炼乙醇作为能源替代品。全世界有一百多个国家出产甘蔗，最大的甘蔗生产国是巴西、印度和中国。甘蔗中含有丰富的糖分、水分，还含有对人体新陈代谢非常有益的各种维生素、脂肪、蛋白质、有机酸、钙、铁等物质，主要用于制糖，表皮一般为紫色和绿色两种常见颜色，也有红色和褐色，但比较少见",
						prevent:"木薯，大戟科木薯属木本植物，块根为圆柱状；叶片纸质，近圆形；萼片为紫红色，有白霜，花药顶部附着白毛；果实为棉圆形；种皮为硬壳质，有斑纹，光滑，花期9~11月。 [7]  木薯块根供食用，得名与其特征有关。 [8] 木薯原产巴西，现全世界热带地区广泛栽培，在中国福建、台湾、两广、海南、云贵等省区有栽培，偶有为野生。 [7]  木薯的适应性很强，耐旱、耐瘠、少病虫害，不择土壤，但要高产仍以土层深厚疏松的土壤种植为佳， [9]  常生于山地疏林中，也栽培于庭园间。 [10]  繁殖方式为切茎繁殖。 [11] 《新华本草纲药》记载，木薯可以治疗痈疽疮疡、瘀肿疼痛、疥疮、顽癣等症状，随着对木薯块根和茎叶生物活性成分研究的不断深入研究，人们发现木薯具有许多保健功能， [12]  而在《广西民族药简编》中记录中毒一般表现：为头晕、恶心、呕吐、疲倦，有时腹痛腹泻、口常流涎，严重者痉挛、神志昏迷、瞳孔散大，在发病后因呼吸麻痹而死亡。故仅作外用，不宜内服。 [13]  木薯的块根富含淀粉，供食用或作糊料，被称为“淀粉之王”，是世界近六亿人的口粮；茎、叶可做饲料。 [11]  据统计，世界木薯总产量的65％都被用于人类食用，它是热带湿地低收入农户的主要食品来源，具有很高的经济价值",
						queryTime:"2023-01-01 00:00:00",
						obj:[]
					}
				}
			}
		},
		data() {
			return {
				obj:null
			};
		},
		onShow(){}
		,
		onLoad(){
			
		}
	}
</script>

<style lang="scss">
	.body{
		display: flex;
		width: 750rpx;
		height: 200rpx;
		// padding-right: 10rpx;
		justify-items: center;
		align-items: center;
		image{
			width: 230rpx;
			height: 100%;
			// height: 500rpx;
		}
	}
		.box{
			border: 1rpx solid #f0efef;
			width: 520rpx;
			height: 200rpx;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			.result{
				// padding-top: 10rpx;
				font-size: 40rpx;
				font-weight: bold;
				color: #333;
			}
			.end{
				font-size: 60rpx;
				padding-bottom: 50rpx;
				padding-left: 70rpx;
				// background: red;
				color: coral;
			}
		}
	.title{
		font-size: 45rpx;
		font-weight: bold;
		text-align: center;
	}
	.content{
		
		.shape{
			margin-bottom: 16rpx;
			display: flex;
			flex-direction: row;
			align-items: center;
			padding: 0 10rpx;
			.title-line {
				width: 15rpx;
				height: 35rpx;
				background: #82d7fa;
				margin-right: 8rpx;
				border-radius: 4rpx;
				// padding: 5rpx;
			}
			.title-text {
				font-size: 40rpx;
				font-weight: bold;
				color: #333;
			}
			.title-row{
				width: 530rpx;
				height: 5rpx;
				background: #f0efef;
				margin-right: 8rpx;
				border-radius: 4rpx;
				

			}
		}
		.text {
		    color: #666;
		    font-size: 30rpx;
		    line-height: 24px;
		    white-space: wrap;
			padding: 5rpx 25rpx;
		}
	}

</style>