<template>
	<div>
		<baseCytoGraph @cyobj="getCy"></baseCytoGraph>
	</div>
</template>

<script>
	const printf = console.log
	import baseCytoGraph from "./baseCytoGraph.vue"
	export default {
		data() {
			return{
				
			}
		},
		components: {
			'baseCytoGraph':baseCytoGraph,
		},
		methods:{
			getCy:function(cyobj){	
				this.cy=cyobj
			}
		}
	}
</script>

<style>
</style>
