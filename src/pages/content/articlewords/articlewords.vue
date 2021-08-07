<template>
	<div v-if="$route.path==='/articlewords'"  class="templatemo-content-container">
		<div class="templatemo-flex-row flex-content-row" >
			<div class="templatemo-content-widget white-bg col-1 text-center"  >
				<router-link id="newArticle" to="/articlewords_new"><i class="fa fa-play-circle fa-lg"></i>
				<h2 class="text-uppercase">新建抽詞</h2>
				<h3 class="text-uppercase margin-bottom-10">Blog Article</h3>
				<img src="../../static/images/bicycle.jpg" alt="Bicycle" class="img-circle img-thumbnail"></router-link>
			</div>
		</div>
	</div>
	<newArticlewords v-else-if="$route.path==='/articlewords_new'">
	</newArticlewords>
</template>

<script>
	const printf = console.log
	import newArticlewords from "./newArticlewords.vue"
	export default {
		watch: {

		},
		components: {
			'newArticlewords':newArticlewords,
		},
		data() {
			return {
				path: 'home'
			}
		},
		created() {
			this.path = this.$route.fullPath.replace("/", "")
		},
		methods: {
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>


</style>
