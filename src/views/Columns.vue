<template>
	<div style="width: auto;">
		<div style="height: 52px;background-color: #ffffff;border-bottom: 2px solid #edeeee;">
			<div style="display: flex; width: 1020px;height: 52px;margin: auto;">
				<svg viewBox="0 0 200 91" style="height: 30px; width: 64px;margin-top: 8px;fill: #0084ff;">
					<g>
						<path d="M53.29 80.035l7.32.002 2.41 8.24 13.128-8.24h15.477v-67.98H53.29v67.978zm7.79-60.598h22.756v53.22h-8.73l-8.718 5.473-1.587-5.46-3.72-.012v-53.22zM46.818 43.162h-16.35c.545-8.467.687-16.12.687-22.955h15.987s.615-7.05-2.68-6.97H16.807c1.09-4.1 2.46-8.332 4.1-12.708 0 0-7.523 0-10.085 6.74-1.06 2.78-4.128 13.48-9.592 24.41 1.84-.2 7.927-.37 11.512-6.94.66-1.84.785-2.08 1.605-4.54h9.02c0 3.28-.374 20.9-.526 22.95H6.51c-3.67 0-4.863 7.38-4.863 7.38H22.14C20.765 66.11 13.385 79.24 0 89.62c6.403 1.828 12.784-.29 15.937-3.094 0 0 7.182-6.53 11.12-21.64L43.92 85.18s2.473-8.402-.388-12.496c-2.37-2.788-8.768-10.33-11.496-13.064l-4.57 3.627c1.363-4.368 2.183-8.61 2.46-12.71H49.19s-.027-7.38-2.372-7.38zm128.752-.502c6.51-8.013 14.054-18.302 14.054-18.302s-5.827-4.625-8.556-1.27c-1.874 2.548-11.51 15.063-11.51 15.063l6.012 4.51zm-46.903-18.462c-2.814-2.577-8.096.667-8.096.667s12.35 17.2 12.85 17.953l6.08-4.29s-8.02-11.752-10.83-14.33zM199.99 46.5c-6.18 0-40.908.292-40.953.292v-31.56c1.503 0 3.882-.124 7.14-.376 12.773-.753 21.914-1.25 27.427-1.504 0 0 3.817-8.496-.185-10.45-.96-.37-7.24 1.43-7.24 1.43s-51.63 5.153-72.61 5.64c.5 2.756 2.38 5.336 4.93 6.11 4.16 1.087 7.09.53 15.36.277 7.76-.5 13.65-.76 17.66-.76v31.19h-41.71s.88 6.97 7.97 7.14h33.73v22.16c0 4.364-3.498 6.87-7.65 6.6-4.4.034-8.15-.36-13.027-.566.623 1.24 1.977 4.496 6.035 6.824 3.087 1.502 5.054 2.053 8.13 2.053 9.237 0 14.27-5.4 14.027-14.16V53.93h38.235c3.026 0 2.72-7.432 2.72-7.432z"
						 fill-rule="evenodd"></path>
					</g>
				</svg>
				<button type="button" class="Button--blue">
					<svg class="Zi" viewBox="0 0 24 24" width="24" height="24">
						<path d="M18.453 7.992l-1.833-1.65.964-.978a1.223 1.223 0 0 1 1.73-.012l.005.006a1.24 1.24 0 0 1 .007 1.748l-.873.886zm-1.178 1.194l-5.578 5.66-1.935.697a.393.393 0 0 1-.504-.504l.697-1.935 5.488-5.567 1.832 1.65zM7.58 5.848l5.654.006-1.539 1.991-3.666.012A1.02 1.02 0 0 0 7 8.868v7.993c0 .558.46 1.01 1.029 1.01l7.941-.01c.568 0 1.03-.453 1.03-1.012v-4.061l2-1.442v6.002c0 1.397-1.2 2.501-2.62 2.501H7.574C6.153 19.85 5 18.717 5 17.32V8.35c0-1.397 1.16-2.502 2.58-2.502z"></path>
					</svg>写文章
				</button>
				<button title="更多" type="button" class="more">
					<svg style="fill: #8590A6;" viewBox="0 0 24 24" width="24" height="24">
						<path d="M5 14a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm7 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm7 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4z"></path>
					</svg>
				</button>
			</div>
		</div>
		<div class="zlLogo">
			<h1 class="zlbt"></h1>
			<h2 class="ColumnHomeTop-subTitle">随心写作，自由表达</h2>
			<button class="ColumnHomeTop-writeButton">开始写文章</button>
			<p class="ColumnHomeTop-requestButton" href="https://www.zhihu.com/column/request">申请开通专栏 ></p>
		</div>
		<div class="ColumnHomeRecommendation">
			<h3 class="ColumnHomeTitle">
				<div class="ColumnHomeTitle-text">专栏 · 发现</div>
				<div class="ColumnHomeTitle-line"></div>
			</h3>
			<div class="ColumnHomeRecommendation-cardContainer" style="height: 562px;width: 905px;">
				<div class="ColumnHomeRecommendation-kapian zh-shadow" v-for="(item,index) in columnss.slice(since,check)" :key="index">
					<img :src="item.image_url" style="width: 48px;height: 48px;border-radius: 100px;margin-top: 28px;" />
					<div class="ColumnHomeColumnCard-info">
						<div class="ColumnHomeColumnCard-title">{{item.title}}</div>
						<div class="ColumnHomeColumnCard-description">{{item.description}}</div>
					</div>
					<div class="ColumnHomeColumnCard-meta">{{item.followers}} 人关注 | {{item.articles_count}} 篇文章</div>
					<button type="button" class="ColumnHomeColumnCard-but">进入专栏</button>
				</div>
			</div>
			<button type="button" class="ColumnHomeColumnCard-hyh" @click="limitbut()">
				<span style="display:inline-flex;align-items:center">​
					<svg class="Button-zi" viewBox="0 0 24 24" width="1.2em" height="1.2em">
						<path d="M20 12.878C20 17.358 16.411 21 12 21s-8-3.643-8-8.122c0-4.044 3.032-7.51 6.954-8.038.034-1.185.012-1.049.012-1.049-.013-.728.461-1.003 1.057-.615l3.311 2.158c.598.39.596 1.026 0 1.418l-3.31 2.181c-.598.393-1.08.12-1.079-.606 0 0 .006-.606-.003-1.157-2.689.51-4.675 2.9-4.675 5.708 0 3.21 2.572 5.822 5.733 5.822 3.163 0 5.733-2.612 5.733-5.822 0-.633.51-1.148 1.134-1.148.625 0 1.133.515 1.133 1.148"></path>
					</svg>
				</span>换一换
			</button>
		</div>
		<div style="height: 500px;background-color: #FFFFFF;text-align: center;">
			<div style="height: 135px;"></div>
			<h3 class="tail">在知乎创作</h3>
		</div>
		
	</div>
</template>

<script>
	export default {
		name: 'columns',
		data() {
			return {
				columnss: [],
				since: 0,
				check: 8,
				max: null
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/columns/all').then(res => {
				console.log(res);
				this.columnss = res.data.data;
				this.max = parseInt(this.columnss.length)
			});
		},
		methods: {
			limitbut: function() {
				if(this.since > this.max && this.check > this.max) {
					this.since = 0;
					this.check = 8;
				}
				this.since += 8;
				this.check += 8;
			}
		}
	}
</script>

<style lang="scss" scoped>
	.tail {
	    border: solid #97ffd8;
	    border-width: 1px 0;
	    font-size: 18px;
	    font-weight: 300;
	    letter-spacing: 14px;
	    padding: 26px 0;
	    width: 345px;
		margin: auto;
	}
	
	.ColumnHomeColumnCard-hyh {
		width: 100px;
		height: 35px;
		border: 1px solid #000000;
		border-radius: 3px;
		text-align: center;
		cursor: pointer;
		background: none;
	}
	
	.ColumnHomeRecommendation-kapian {
		width: 210px;
		height: 265px;
		// border: 1px solid #000000;
		text-align: center;
		background-color: #FFFFFF;
		border-radius: 4px;
		margin: 0 8px 16px;
	}
	
	.ColumnHomeColumnCard-but{
		width: 90px;
		height: 34px;
		color: #42B983;
		border-color: #42B983;
		border: 1px solid;
		border-radius: 3px;
		text-align: center;
		cursor: pointer;
		background: none;
		margin-top: 15px;
	}
	
	.ColumnHomeColumnCard-meta {
	    color: grey;
	    font-size: 14px;
	    margin-top: 14px;
	}
	
	.ColumnHomeColumnCard-info {
	    -webkit-box-align: center;
	    -ms-flex-align: center;
	    align-items: center;
	    display: -webkit-box;
	    display: -ms-flexbox;
	    display: flex;
	    -webkit-box-orient: vertical;
	    -webkit-box-direction: normal;
	    -ms-flex-direction: column;
	    flex-direction: column;
	    -webkit-box-flex: 1;
	    -ms-flex-positive: 1;
	    flex-grow: 1;
	    padding: 0 16px;
	}
	
	.ColumnHomeColumnCard-title {
	    margin-top: 16px;
	    display: -webkit-box;
	    text-overflow: ellipsis;
	    overflow: hidden;
	    -webkit-line-clamp: 1;
	    -webkit-box-orient: vertical;
	    font-weight: 600;
	    font-synthesis: style;
	}
	
	.ColumnHomeColumnCard-description {
	    color: grey;
	    font-size: 14px;
	    line-height: 21px;
	    margin-top: 7px;
	    text-align: center;
	    word-break: break-all;
	    display: -webkit-box;
	    text-overflow: ellipsis;
	    overflow: hidden;
	    -webkit-line-clamp: 2;
	    -webkit-box-orient: vertical;
	}
	
	.ColumnHomeRecommendation-cardContainer {
	    display: -webkit-box;
	    display: -ms-flexbox;
	    display: flex;
	    -ms-flex-wrap: wrap;
	    flex-wrap: wrap;
		height: 562px;
		width: 905px;
	}
	.ColumnHomeRecommendation {
		-webkit-box-align: center;
		-ms-flex-align: center;
		align-items: center;
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-webkit-box-orient: vertical;
		-webkit-box-direction: normal;
		-ms-flex-direction: column;
		flex-direction: column;
		// margin: 48px auto 0;
		width: auto;
		background-color: #FFFFFF;
	}

	.ColumnHomeTitle {
		-webkit-box-align: center;
		-ms-flex-align: center;
		align-items: center;
		display: -webkit-box;
		display: -ms-flexbox;
		display: flex;
		-webkit-box-pack: center;
		-ms-flex-pack: center;
		justify-content: center;
		margin: 0 3px 32px;
		width: 100%;
	}

	.ColumnHomeTitle-text {
		color: #1a1a1a;
		font-size: 14px;
		line-height: 22px;
		margin: 0 16px;
		font-weight: 600;
		font-synthesis: style;
		margin-top: 48px;
	}

	.ColumnHomeTitle-line {
		background: #d3d3d3;
		display: none;
		-webkit-box-flex: 1;
		-ms-flex-positive: 1;
		flex-grow: 1;
		height: 1px;
	}

	.ColumnHomeTop-requestButton {
		color: #42B983;
		font-size: 14px;
		left: 50%;
		line-height: 12px;
		margin-left: -36px;
		position: absolute;
		top: 466px;
		text-align: center;
		cursor: pointer;
		background: none;
	}

	.ColumnHomeTop-writeButton {
		border-color: #444;
		-webkit-box-sizing: border-box;
		box-sizing: border-box;
		color: #444;
		height: 38px;
		left: 50%;
		line-height: 36px;
		margin-left: -51px;
		position: absolute;
		top: 413px;
		width: 120px;
		padding: 0 16px;
		font-size: 14px;
		text-align: center;
		background: none;
		border: 1px solid;
		border-radius: 3px;
	}

	.ColumnHomeTop-subTitle {
		color: #1a1a1a;
		font-size: 18px;
		font-weight: 300;
		letter-spacing: .5em;
		line-height: 24px;
		margin: 0;
		position: absolute;
		text-align: center;
		top: 350px;
		width: 100%;
	}

	.zlbt {
		background: url(https://static.zhihu.com/heifetz/assets/logo.84666bea.png) 50% no-repeat;
		background-size: 129px 179px;
		height: 0;
		left: 50%;
		margin: 0 0 0 -65px;
		overflow: hidden;
		padding-top: 179px;
		position: absolute;
		top: 152px;
		width: 129px;
	}

	.zlLogo {
		width: auto;
		height: 470px;
		background: url(https://static.zhihu.com/heifetz/assets/patterns.c72a480c.png) 50% no-repeat;
		position: relative;
		background-color: #FFFFFF;
	}

	.more {
		height: 34px;
		margin-top: 8px;
		margin-left: 20px;
		border: none;
		background-color: #FFFFFF;
	}

	.Button--blue {
		display: flex;
		align-items: center;
		padding: 0 12px;
		border: 1px solid;
		border-radius: 3px;
		font-size: 14px;
		height: 34px;
		color: #0084ff;
		border-color: #0084ff;
		background-color: #FFFFFF;
		margin-top: 8px;
		margin-left: 780px;
	}

	.Zi {
		fill: #0084ff;
	}
	
	.Button-zi {
		fill: #444444;
	}
</style>
