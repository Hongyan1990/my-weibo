<template>
	<div>
	  <el-main>
		  <el-row>
			<el-col :span="24">
				<div class="block">
					<el-avatar :size="100" :src="imgUrl"></el-avatar>
					<div class="user-info">
						<p>zhangsan</p>
						<div class="guan-zhu">
							<p>
								<el-avatar style="background: #fff" :size="30" :src="gzUrl"></el-avatar>
								<span class="my-btn" @click="showMyAttention">我的关注</span>
							</p>
							<p>
								<el-avatar style="background: #fff" :size="30" :src="fansUrl"></el-avatar>
								<span class="my-btn" @click="showMyFans">我的粉丝</span>
							</p>
						</div>
					</div>
				</div>
			</el-col>
		  </el-row>
		  <el-row style="margin: 20px 0px;">
			<el-col :span="24"><span style="font-size: 14px; font-weight: 777;">{{myTitle}}</span></el-col>
		  </el-row>
		  <el-row>
			  <el-col style="text-align: center;margin-bottom: 10px;" :span="3" v-for="(o, index) in 10" :key="o" :offset="index%6 != 0 ? 1 : 0">
				  <el-card class="card">
					  <img :src="usersIcon[index%3]" class="image">
					  <div style="padding: 14px;">
						  <span>lisi</span>
						  <div class="bottom clearfix guzhu-btn">
							  <span>关注</span>
							  <span>取消关注</span>
						  </div>
					  </div>
					  <i class="el-icon-success my-icon"></i>
				  </el-card>
			  </el-col>
		  </el-row>
		  <el-row style="margin-top: 20px;">
			  <el-col :span="24">
				  <el-pagination
						  layout="prev, pager, next"
						  :total="50">
				  </el-pagination>
			  </el-col>
		  </el-row>
	  </el-main>
	</div>
</template>
<script>
	import imgUrl from '../static/user.png'
	import gzUrl from '../static/gz.png'
	import fansUrl from '../static/fans.png'
	import url_1 from '../static/1.png'
	import url_2 from '../static/2.png'
	import url_3 from '../static/3.png'
	export default {
		name: 'adminorder',
		data () {
			return {
				imgUrl,
				gzUrl,
				fansUrl,
				usersIcon: [url_1, url_2, url_3],
				myTitle: '全部用户'
			}
		},
		methods: {
			showMyAttention() {

			},
			showMyFans() {

			},
			showAllUsers() {

			}
		},
		mounted () {
			this.showAllUsers()
		}
	}
</script>
<style>
	.block {
		display: flex;
		padding: 5px;
		box-shadow: 0px 2px 3px 0px rgba(0, 0, 0, 0.2), 0px 3px 10px 0px rgba(0, 0, 0, 0.19);
		border-radius: 5px;
	}
	.user-info {
		margin-left: 20px;
		padding: 10px 0px;
	}
	.guan-zhu {
		margin-top: 10px;
		display: flex;

	}
	.guan-zhu > p {
		display: flex;
		align-items: center;
		margin-right: 20px;
	}
	.guan-zhu > p > a {
		font-size: 14px;
		color: #555;
		margin-left: 10px;
	}
	.image {
		width: 50%;
	}
	.card {
		position: relative;
	}
	.my-icon {
		position: absolute;
		top: 5px;
		right: 5px;
		color: #67c23a;
		font-size: 20px;
	}
	.guzhu-btn {
		font-size: 12px;
		font-weight: 777;
		cursor: pointer;
	}
	.my-btn {
		font-size: 14px;
		color: #555;
		margin-left: 10px;
		cursor: pointer;
	}
</style>