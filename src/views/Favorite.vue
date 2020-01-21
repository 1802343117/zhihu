<template>
	<div>
		<div class="banner">
			<div style="display: flex;width: 1000px;height: 100px;margin: auto;">
				<svg class="Zi" viewBox="0 0 24 24" width="36" height="36" style="margin-top: 30px;">
					<path d="M5.515 19.64l.918-5.355-3.89-3.792c-.926-.902-.639-1.784.64-1.97L8.56 7.74l2.404-4.871c.572-1.16 1.5-1.16 2.072 0L15.44 7.74l5.377.782c1.28.186 1.566 1.068.64 1.97l-3.89 3.793.918 5.354c.219 1.274-.532 1.82-1.676 1.218L12 18.33l-4.808 2.528c-1.145.602-1.896.056-1.677-1.218z"></path>
				</svg>
				<h3 style="margin-top: 30px;margin-left: 15px;font-size: 24px;">热门收藏夹</h3>
			</div>
		</div>
		<div class="container">
			<div class="row">
				<div class="col-12 box zh-shadow" v-for="(item,index)  in favorites" v-if="index>begin&&index<end" :key="index">
					<div class="left">
						<div style="width: 270px;height: 131px;">
							<div style="height: 25px;">
								<h3 style="font-size: 16px;cursor: pointer;">{{item.title}}</h3>
							</div>
							<div style="display: flex;height: 30px;margin-top: 20px;">
								<img :src="item.creator_avatar" style="width: 30px;height: 30px;cursor: pointer;" />
								<p style="font-size: 15px;margin-top: 3px;margin-left: 8px;cursor: pointer;">{{item.creator_name}}</p>
								<p style="font-size: 15px;margin-top: 3px;margin-left: 8px;color: #999999;">创建</p>
							</div>
							<div style="display: flex;height: 35px;margin-top: 20px;">
								<button class="hidden-btn_gz">关注收藏夹</button>
								<p style="font-size: 15px;margin-top: 6px;margin-left: 8px;color: #999999;">{{item.followers}} 人关注</p>
							</div>
						</div>
					</div>
					<div class="right">
						<div style="height: 95px;margin-left: 20px;">
							<div style="height: 25px;margin-top: 5px;">
								<h3 style="font-size: 15px;cursor: pointer;">{{item.question_title}}</h3>
							</div>
							<div style="height: 50px;">
								<p style="font-size: 14px;">{{item.answer_content}}</p>
							</div>
							<div style="height: 25px;margin-top: 2px;">
								<span class="backto">回答</span>
								<span style="margin-left: 10px;font-size: 12px;color: #999999;">{{item.voteup_count}} 赞同</span>
								<span style="margin-left: 10px;font-size: 12px;color: #999999;">· {{item.comment_count}} 评论</span>
							</div>
						</div>
						<p style="font-size: 14px;color: #999999;margin-top: 10px;margin-left: 20px;font-weight: 600px;cursor: pointer;">已收藏 {{item.comment_count+item.followers}} 条内容 ></p>
					</div>
					</div> 
			</div>
			<button @click="show_all" class="flex center btn_gz">展开全部>>></button>
		</div>
		<div><a href="#top" style="position: fixed; bottom: 5%; right: 5%;"><i class="iconfont">&#xe633;</i></a></div>
	</div>
</template>

<script>
export default{
	name:'favorite',
	data(){
		return{
			favorites:[],
			begin:0,
			end:6,
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/favorite/all').then(res =>{
			console.log(res);
			this.favorites = res.data.data;
		});
	},
	methods: {
	show_all(){
	this.begin=0;
	this.end =this.favorites.length;
	}						
	},					
};
</script>

<style  lang="scss" scoped>
	.backto {
		font-size: 12px;
		color: #999999;
		background-color: rgba(246, 246, 246, 20);
	}
	
	.banner{
		width: 100%;
		margin-bottom: 10px;
		// margin-top: -10px;
		height: 100px;
		display: flex;
		align-items: center;
		font-size: 20px;
		background-color: rgb(255, 255, 255);
	}
	.iconfont{
		color: rgb(0,132,255);
		font-size: 32px;
		margin-right:10px;
	}
	.box{
		display: flex;
		width: 100%;
		height: 185px;
		margin-bottom: 20px;
		padding: 25px;
		background-color: white;
		// border: 1px solid #888888;
	}
	.box-left{
		width: 35%;
		margin-right: 20px;
		img{
			width: 100%;
			height: 100%;
		}
	}
	.box-right{
		width: 65%;
		position: relative;
	}
	.box-head{
		display: flex;
	}
	.left{
		width: 30%;
		border-right: 1px solid #888888;
	}
	.right{
		width: 70%;
		// border: 1px solid #888888;
	}
	.box-bottom{
		display: flex;
		position: absolute;
		left: 0;
		bottom: 0;
	}
	.section{
		padding: 0 8px;
		height: 24px;
		line-height: 24px;
		border-radius: 5px;
		background-color: #f6f6f6;
		color: #8590a6;
		font-size: 12px;	
	}
	
	.introduction{
		display: flex;
	}
	
	.hidden-btn_gz {
		-webkit-tap-highli0ht-color: rgba(26, 26, 26, 0);
		font: inherit;
		cursor: pointer;
		background: none;
		border: none;
		outline: none;
		-webkit-appearance: none;
		height: 34px;
		border-radius: 3px;
		font-size: 14px;
		font-weight: 600;
		width: 102px;
		color: #0084ff;
		background-color: rgba(0, 132, 255, .08);
	}
	
	.Zi {
		fill: #0084FF;
	}
</style>