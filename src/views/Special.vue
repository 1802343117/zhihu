<template>
	<div>
		<div class="banner">
			<div style="display: flex;width: 1000px;height: 100px;margin: auto;">
				<svg class="Zi " viewBox="0 0 24 24" width="32" height="32" style="margin-top: 30px;">
					<path d="M7.667 3.667h11.466a1.2 1.2 0 0 1 1.2 1.2v13.066a2.4 2.4 0 0 1-2.4 2.4H6.467V4.867a1.2 1.2 0 0 1 1.2-1.2zM4.2 9.619h1.689v10.714H5.4a2.4 2.4 0 0 1-2.4-2.4V10.82a1.2 1.2 0 0 1 1.2-1.2zm5.178-2.38a.6.6 0 0 0-.6.6v.585a.6.6 0 0 0 .6.6h8.044a.6.6 0 0 0 .6-.6v-.586a.6.6 0 0 0-.6-.6H9.378zm0 3.57a.6.6 0 0 0-.6.6v.586a.6.6 0 0 0 .6.6h8.044a.6.6 0 0 0 .6-.6v-.585a.6.6 0 0 0-.6-.6H9.378zm0 3.572a.6.6 0 0 0-.6.6v.586a.6.6 0 0 0 .6.6h4.578a.6.6 0 0 0 .6-.6v-.586a.6.6 0 0 0-.6-.6H9.378z"></path>
				</svg>
				<h3 style="margin-top: 30px;margin-left: 15px;font-size: 24px;">全部专题</h3>
				<p style="font-size: 15px;margin-top: 35px;margin-left: 25px;color: #8590A6;">共有 504 个专题</p>
			</div>
		</div>
		<div class="container">
			<div class="row">
				<div class="col-12 box zh-shadow" v-for="(item,index)  in specials" v-if="index>begin&&index<end" :key="index">
						<div class="box-left"><img :src="item.banner" alt=""></div>
						<div class="box-right">
							<div class="box-head">
							<div class="left">
							<h3>{{item.title}}</h3>
							<p class="meta">{{item.updated}}更新,{{item.viewCount}}次浏览</p>
							</div>
							<div class="right">
								<button class="btn_gz">关注专题</button>
							</div>
							</div>
							<div class="box-body">
								<p class="introduction">{{item.introduction}}</p>
							</div>
							<div class="box-bottom">
								<span v-for="(section,index) in item.sections" :key="index" class="section flex">
									{{section.sectionTitle}}
								</span>
							</div>
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
	name:'special',
	data(){
		return{
			specials:[],
			begin:0,
			end:6,
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/special/all').then(res =>{
			console.log(res);
			this.specials = res.data.data;
		});
	},
	methods: {
	show_all(){
	this.begin=0;
	this.end =this.specials.length;
	}						
	},					
};
</script>

<style  lang="scss" scoped>
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
		height: 250px;
		margin-bottom: 20px;
		padding: 25px;
		background-color: white;
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
		width: 83%;
	}
	.right{
		width: 17%;
		margin-bottom: 30px;
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
	
	.Zi {
		fill: #0084FF;
	}
</style>