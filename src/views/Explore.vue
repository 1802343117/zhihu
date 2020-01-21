<template>
	<div>
		<div class="container">
			<div class="row">
				<div class="banner">
					<svg class="Zi " viewBox="0 0 24 24" width="36" height="36">
						<path d="M7.667 3.667h11.466a1.2 1.2 0 0 1 1.2 1.2v13.066a2.4 2.4 0 0 1-2.4 2.4H6.467V4.867a1.2 1.2 0 0 1 1.2-1.2zM4.2 9.619h1.689v10.714H5.4a2.4 2.4 0 0 1-2.4-2.4V10.82a1.2 1.2 0 0 1 1.2-1.2zm5.178-2.38a.6.6 0 0 0-.6.6v.585a.6.6 0 0 0 .6.6h8.044a.6.6 0 0 0 .6-.6v-.586a.6.6 0 0 0-.6-.6H9.378zm0 3.57a.6.6 0 0 0-.6.6v.586a.6.6 0 0 0 .6.6h8.044a.6.6 0 0 0 .6-.6v-.585a.6.6 0 0 0-.6-.6H9.378zm0 3.572a.6.6 0 0 0-.6.6v.586a.6.6 0 0 0 .6.6h4.578a.6.6 0 0 0 .6-.6v-.586a.6.6 0 0 0-.6-.6H9.378z"
						 fill-rule="evenodd"></path>
					</svg>
					<h3>最新专题</h3>
				</div>
				<div class="col-6 card" v-for="(item,index) in specials" :key="index">
					<div class="card-head"><img :src="item.banner" style="cursor: pointer;"></div>
					<div class="card-body flex">
						<div class="left">
							<h3 style="cursor: pointer;">{{item.title}}</h3>
							<p class="meta">{{item.updated}}更新,{{item.viewCount}}次浏览</p>
						</div>
						<div class="right">
							<button class="btn_gz">关注专题</button>
						</div>
						<p class="introduction">{{item.introduction}}</p>
					</div>
					<div class="card-buttom">
						<span v-for="(section,index) in item.sections" :key="index" class="section flex">
							{{section.sectionTitle}}
						</span>
					</div>
				</div>
				<div class="center">
					<router-link to="/special/all" class="l">查看更多专题 ></router-link>
				</div>
			</div>
			<div class="row">
				<div class="banner">
					<svg class="Zi" viewBox="0 0 24 24" width="36" height="36">
						<path d="M12 21.333a9.333 9.333 0 1 1 0-18.666 9.333 9.333 0 0 1 0 18.666zm-.66-11.287c.332.385.609.77.775 1.21.055-.054.665-.99.72-1.706.055-.385.126-1.616-.443-2.367-.443-.496-1.219-.77-1.884-.55a1.788 1.788 0 0 0-1.33 2.036c.887.276 1.607.771 2.161 1.377zm-1.33 1.541c.443-.055.941-.11 1.44 0 0-.055-.484-.936-1.108-1.486-.665-.496-1.33-.973-2.216-.771-.72.11-1.723.77-1.55 2.092.11.606.553 1.101 1.162 1.321.61-.605 1.44-1.046 2.272-1.156zm2.714.165c.056 0 1.164.055 1.828-.165.72-.275 1.412-.68 1.773-1.541.11-.276.23-1.248-.443-1.872-.72-.716-1.717-.716-2.438-.165.222.825.063 1.966-.11 2.532-.103.348-.333.88-.61 1.211zm-1.44.55c-.056 0-1.33.056-1.828.221-.72.275-1.447.668-1.773 1.541-.11.276-.21 1.26.443 1.872.665.661 1.718.661 2.438.11-.295-.811-.166-1.761.055-2.477.166-.495.388-.936.665-1.266zm5.041-.99c-.665.605-1.44.99-2.327 1.211-.443.055-.941.11-1.44 0 0 .055.554.991 1.108 1.431.665.496 1.385.771 2.216.771.72-.11 1.678-.692 1.551-2.092-.055-.605-.554-1.101-1.108-1.321zm-3.656 2.642a3.475 3.475 0 0 1-.776-1.156c-.055.055-.665.991-.72 1.707-.055.385-.101 1.506.499 2.312.443.496 1.218.77 1.883.55.887-.275 1.496-1.1 1.33-2.036a5.38 5.38 0 0 1-2.216-1.377z"
						 fill-rule="evenodd"></path>
					</svg>
					<h3>圆桌讨论</h3>
				</div>
				<div class="col-6 card" v-for="(item,index) in roundTables" :key="index">
					<div class="table-card-head">
						<div class="left-mark">
							<div class="mark-1">
								<h3 style="cursor: pointer;">{{item.name}}</h3>
							</div>
							<div class="mark-2">
								<p style="margin-left: 38px;margin-top: 10px;cursor: pointer;">近期指数基金突然在知乎火了起来，各种大V、小V
									创作者们如雨后春笋般冒出来推荐指数基金，到底
									指数基金好不好，是不是真的适合小白，小白如何..
								</p>
							</div>
							<div class="mark-3">
								<div style="display: flex;width: 150px;height: 50px;margin-left: 35px;">
									<div>
										<img src="../assets/image/sl.jpg" style="width: 45px; height: 45px;margin-right: 1px; border-radius: 10px;" />
									</div>
									<div>
										<img src="../assets/image/tx.jpeg" style="width: 45px; height: 45px;margin-right: 1px; border-radius: 10px;" />
									</div>
									<div>
										<img src="../assets/image/gt.jpeg" style="width: 45px; height: 45px;margin-right: 1px; border-radius: 10px;" />
									</div>
								</div>
								<div style="width: 280px;height: 50px;">
									<p style="color: #cbcbcb;margin-top: 10px;">5 位嘉宾参与 | {{item.includeCount}} 人关注</p>
								</div>
							</div>
						</div>
						<div class="right-mark">
							<button class="mark-btn_gz">关注圆桌</button>
						</div>
					</div>
					<div style="height: 208px;padding: 20px 20px 20px 20px;">
						<div style="height: 50px;">
							<p style="cursor: pointer;">每个月有5000元结余,买基金定投好还是扔余额宝?</p>
							<p style="color: #9d9d9d;font-size: 12px;margin-top: 5px;">67个回答</p>
						</div>
						<div style="height: 50px;margin-top: 10px;">
							<p style="cursor: pointer;">可以推荐几个值得长期投资的基金吗?</p>
							<p style="color: #9d9d9d;font-size: 12px;margin-top: 5px;">467个回答</p>
						</div>
						<div style="height: 50px;margin-top: 10px;">
							<p style="cursor: pointer;">学生党想每月拿王百块做基金定投，逼迫自己强制储蓄，面对基. ..</p>
							<p style="color: #9d9d9d;font-size: 12px;margin-top: 5px;">543个回答</p>
						</div>
					</div>
				</div>
				<div class="center">
					<router-link to="/roundTable/all" class="l">查看更多圆桌 ></router-link>
				</div>
			</div>
			<div class="row">
				<div class="banner">
					<svg class="Zi" viewBox="0 0 24 24" width="36" height="36">
						<path d="M5.515 19.64l.918-5.355-3.89-3.792c-.926-.902-.639-1.784.64-1.97L8.56 7.74l2.404-4.871c.572-1.16 1.5-1.16 2.072 0L15.44 7.74l5.377.782c1.28.186 1.566 1.068.64 1.97l-3.89 3.793.918 5.354c.219 1.274-.532 1.82-1.676 1.218L12 18.33l-4.808 2.528c-1.145.602-1.896.056-1.677-1.218z"
						 fill-rule="evenodd"></path>
					</svg>
					<h3>热门收藏夹</h3>
				</div>
				<div class="col-6 hidden" v-for="(item,index) in favorites" :key="index">
					<div style="height: 360px;">
						<div style="display: flex;width: 600px;height: 112px;border-bottom: 1px solid #888888;padding: 20px 0px 20px 0px;margin-left: 30px;">
							<div class="left-hidden">
								<h3 style="cursor: pointer;">{{item.title}}</h3>
								<div style="display: flex;height: 40px;">
									<img :src="item.creatorAvatar" style="cursor: pointer;width: 35px;height: 35px;padding: 0px 0px 0px 0px;margin-top: 5px;" />
									<p style="font-size: 16px;margin-top: 10px;margin-left: 10px;cursor: pointer;">{{item.creatorName}}</p>
									<p style="font-size: 16px;color: #8590A6; margin-top: 10px;margin-left: 10px;">创建 |</p>
									<p style="font-size: 16px;color: #8590A6; margin-top: 10px;margin-left: 10px;">{{item.followers}} 人关注</p>
								</div>
							</div>
							<div class="right-hidden">
								<button class="hidden-btn_gz">关注收藏夹</button>
							</div>
						</div>
						<div style="height: 200px;padding: 20px 20px 20px 20px;">
							<div style="height: 72px;">
								<p style="font-weight: 600;cursor: pointer;">经验分享:深圳买房记</p>
								<p style="margin-top: 5px;font-size: 16px;">蓝宝王:经历两个月终于把这这件事顺利搞定了。第一次买房都..</p>
								<span class="chapter">文章</span>
								<span style="font-size: 12px;margin-left: 10px;color: #999999;">26 赞同</span>
								<span style="font-size: 12px;margin-left: 10px;color: #999999;">· 29 评论</span>
							</div>
							<div style="height: 72px;margin-top: 20px;">
								<p style="font-weight: 600;cursor: pointer;">资产荒-触即发!现在买什么? (深度长文附标的)</p>
								<p style="margin-top: 5px;">投研帮:到现在为止,形势已经再明显不过了。我们已然踏上了...</p>
								<span class="chapter">文章</span>
								<span style="font-size: 12px;margin-left: 10px;color: #999999;">106 赞同</span>
								<span style="font-size: 12px;margin-left: 10px;color: #999999;">· 11 评论</span>
							</div>
						</div>
						<div style="height: 45px;">
							<p style="font-weight: 600;font-size: 14px;color: #999999;margin-top: 10px;margin-left: 20px;cursor: pointer;">已收藏
								{{item.commentCount+item.followers}} 条内容 ></p>
						</div>
					</div>
				</div>
				<div class="center">
					<router-link to="/favorite/all" class="l">查看更多收藏夹 ></router-link>
				</div>
			</div>
			<div class="row">
				<div class="banner">
					<svg class="Zi" viewBox="0 0 24 24" width="36" height="36">
						<path d="M12 22C6.477 22 2 17.523 2 12S6.477 2 12 2s10 4.477 10 10-4.477 10-10 10zm4.043-15.524a.745.745 0 0 0-1.053.017l-6.857 7.071 2.237 2.17 6.857-7.071a.743.743 0 0 0-.016-1.052l-1.168-1.135zm-9.028 9.476l-.348 1.381 1.37-.39 1.274-.36-1.973-1.916-.323 1.285z"></path>
					</svg>
					<h3>专栏</h3>
				</div>
				<div class="col-3 bar" v-for="(item,index) in columnss" :key="index">
					<div style="width: 235px;margin: auto;">
						<div style="text-align: center;width: 200px;margin: auto;margin-top: 30px;">
							<img src="../assets/image/gt.jpeg" style="width: 80px;height: 80px;border-radius: 100px;"/>
							<h4 style="margin-top: 20px;">{{item.title}}</h4>
							<p style="font-size: 12px;color: #999999;margin-top: 5px;">{{item.followers}}关注 · {{item.articlesCount}}文章</p>
							<div style="width: 100%;height: 40px;margin-top: 18px;">
								<p style="font-size: 14px;">{{item.description}}</p>
							</div>
							<button class="bar-btn_gz">进入专栏</button>
						</div>
					</div>
				</div>
				<div class="center">
					<router-link to="/columns/all" class="l">查看更多专栏 ></router-link>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'special',
		data() {
			return {
				specials: [],
				roundTables: [],
				favorites: [],
				columnss: []
			};
		},
		created() {
			this.axios.get('http://localhost:8080/api/special').then(res => {
				console.log(res);
				this.specials = res.data.data;
			});
			this.axios.get('http://localhost:8080/api/roundTable').then(res => {
				console.log(res);
				this.roundTables = res.data.data;
			});
			this.axios.get('http://localhost:8080/api/favorite').then(res => {
				console.log(res);
				this.favorites = res.data.data;
			});
			this.axios.get('http://localhost:8080/api/columns').then(res => {
				console.log(res);
				this.columnss = res.data.data;
			});
		}
	};
</script>

<style lang="scss" scoped>
	.banner {
		width: 100%;
		margin-bottom: 10px;
		margin-top: 10px;
		height: 60px;
		display: flex;
		align-items: center;
		font-size: 20px;

	}

	.iconfont {
		color: rgb(0, 132, 255);
		font-size: 32px;
		margin-right: 10px;
	}

	.left {
		width: 60%;
	}

	.right {
		width: 30%;
		margin-left: 45px;
		margin-bottom: 30px;
	}

	.card {
		background-color: rgb(255, 255, 255);
		border: 2px solid #d6d6d6;
		box-shadow: 0 1px 3px 0 rgba(26, 26, 26, .1);
		border-radius: 5px;
		width: 500px;
		height: 450px;
		margin-bottom: 30px;
	}

	.hidden {
		background-color: rgb(255, 255, 255);
		border: 2px solid #d6d6d6;
		box-shadow: 0 1px 3px 0 rgba(26, 26, 26, .1);
		border-radius: 5px;
		width: 500px;
		height: 365px;
		margin-bottom: 30px;
	}
	
	.bar {
		background-color: rgb(255, 255, 255);
		border: 2px solid #d6d6d6;
		box-shadow: 0 1px 3px 0 rgba(26, 26, 26, .1);
		border-radius: 5px;
		width: 500px;
		height: 365px;
		margin-bottom: 30px;
	}

	.left-hidden {
		width: 70%;
		height: 70px;
		// border: 1px solid #000000;			/*--设置边框线--*/
	}

	.right-hidden {
		width: 30%;
		height: 70px;
		// border: 1px solid #000000;			/*--设置边框线--*/
	}

	.card-head {
		position: relative;
		height: 240px;
		background-image: linear-gradient(to right, rgb(0, 0, 255) 0%, rgba(0, 0, 255, 0) 100%);
		// border: 1px solid #000000;				/*--设置边框线--*/
	}

	.table-card-head {
		position: relative;
		display: flex;
		/*--flex布局--*/
		justify-content: center;
		height: 240px;
		background-image: linear-gradient(to right, rgb(0, 0, 255) 0%, rgba(0, 0, 255, 0) 100%);
		// border: 1px solid #000000;			/*--设置边框线--*/
	}

	.left-mark {
		width: 70%;
		height: 180px;
		margin-top: 40px;
		// border: 1px solid #000000;			/*--设置边框线--*/
	}

	.right-mark {
		width: 30%;
		height: 180px;
		margin-top: 40px;
		// border: 1px solid #000000;			/*--设置边框线--*/
	}

	.mark-btn_gz {
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
		margin-top: 135px;
		margin-left: 50px;
		color: #00aaff;
		background-color: rgba(255, 255, 255, 20);
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
		margin-top: 10px;
		margin-left: 60px;
		color: #0084ff;
		background-color: rgba(0, 132, 255, .08);
	}
	
	.bar-btn_gz {
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
		width: 88px;
		margin: auto;
		margin-top: 20px;
		color: #0084ff;
		background-color: rgba(0, 132, 255, .08);
	}

	.chapter {
		font-size: 12px;
		color: #999999;
		background-color: rgba(246, 246, 246, 20);
	}

	.mark-1 {
		height: 50px;
		color: #FFFFFF;
		font-size: 20px;
		text-indent: 2em;
		/*--开头空格--*/
		// border: 1px solid #ff0000;			/*--设置边框线--*/
	}

	.mark-2 {
		height: 80px;
		color: #FFFFFF;
		font-size: 14px;
		// border: 1px solid #ffff00;			/*--设置边框线--*/
	}

	.mark-3 {
		display: flex;
		height: 50px;
		// border: 1px solid #00ff00;			/*--设置边框线--*/
	}

	.card-background {
		position: absolute;
		top: 0;
		right: 0;
		bottom: 0;
		width: 240px;
	}

	.card-main {
		position: relative;
		width: 320px;
		padding: 68px 24px 24px;
	}

	.card-btn {
		position: absolute;
		right: 24px;
		bottom: 24px;
		background-color: white;
		border-radius: 5px;
	}

	.card-body {
		margin: 20px;
	}

	.btn_gz {
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

	.introduction {
		display: flex;
	}

	.name {
		font-size: 28px;
		font-weight: 660;
		color: white;
		margin-bottom: 30px;
	}

	.col-6 {
		flex: 0 0 50%;

		img {
			width: 100%;
			height: 100%;
			padding: 5px;
		}
	}

	.Zi {
		fill: #0084FF;
	}
</style>
