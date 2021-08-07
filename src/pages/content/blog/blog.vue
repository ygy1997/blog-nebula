<template>
	<div class="templatemo-content-container">
		<div class="templatemo-flex-row flex-content-row">
			<div class="col-2">
				<div class="templatemo-content-widget white-bg col-1 text-center">
					<div class="Nav">
						<el-menu :default-active="activeIndex" @select="navSelect" class="el-menu-demo" mode="horizontal" >
							<el-menu-item index="1">图像博文</el-menu-item>
							<el-menu-item index="2">文章管理</el-menu-item>
						</el-menu>
					</div>
				</div>
				<div class="templatemo-content-widget white-bg">
					<keep-alive>
					<blogGraph  v-if="activeIndex==='1'"></blogGraph>
					</keep-alive>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	const printf = console.log
	import blogGraph from "../tools/blogGraph.vue"
	export default {
		watch: {

		},
		components: {
			'blogGraph':blogGraph,
		},
		data() {
			return {
				path: 'home',
				activeIndex:"1",
			}
		},
		created() {
			this.path = this.$route.fullPath.replace("/", "")

		},
		methods: {
			navSelect(index){
				this.activeIndex=index
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
