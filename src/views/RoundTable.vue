<template>
	<div>
		<div class="container">
			<div class="row">
				<div style="width: 1000px;margin: auto;margin-top: 20px;background-color: rgba(255, 255, 255, 20);">
					<div style="display: flex; height: 60px;border-bottom: 1px solid #f6f6f6;padding: 20px 10px 20px 10px;">
						<h4 style="width: 35px;font-size: 15px;">圆桌</h4>
						<h4 style="color: #0084FF;margin-left: 875px;font-size: 15px;">举办圆桌</h4>
					</div>
					<div class="area">
						<div style="margin-left: 38px;margin-top: 25px;"v-for="(item,index)  in roundTables" v-if="index>begin&&index<end" :key="index">
							<div class="area-head">
								<img :src="item.banner" style="width: 200px;height: 200px;border-radius: 6px;"/>
								<p class="name">{{item.name}}</p>
							</div>
							<div class="area-body">
								<p>该圆桌被浏览{{item.visits_count}}次</p>
							</div>
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
			roundTables:[],
			begin:0,
			end:10,
		};
	},
	created() {
		this.axios.get('http://localhost:8080/api/roundTable/all').then(res =>{
			console.log(res);
			this.roundTables = res.data.data;
		});
	},
	methods: {
	show_all(){
	this.begin=0;
	this.end =this.roundTables.length;
	}						
	},					
};
</script>

<style  lang="scss" scoped>
	.col-8{
		flex: 0 0 83.3%;
		img{
			width: 100%;
			height: 100%;
		}
	}
	.col-4{
		flex: 0 0 16.6%;
	}
	.col-3{
		flex: 0 0 25%;
	}
	.area{
		// width: 960px;
		// margin: auto;
		display: none;
		display: flex;
		flex-wrap: wrap;                 /*--如果一行放不下，可以换行--*/
		// border: 1px solid #000000;
		flex: 0 0 25%;
	}
	.area-head{
		height: 200px;
		// border: 1px solid #000000;
		position: relative;
	}
	.area-body{
		// height: 20%;
		background-color: white;
		margin-top: 5px;
		font-size: 14px;
		width: 100%;
		color: #778087;	
	}
	.name{
		position: absolute;
		font-size: 16px;
		bottom: 5%;
		left: 5%;
		color: white;
	}
</style>