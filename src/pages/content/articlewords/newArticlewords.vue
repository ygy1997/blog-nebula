<template>
	<div class="templatemo-content-container">
		<div class="templatemo-content-widget white-bg col-1 text-center">
			<i class="fa fa-file-word-o fa-4x" title="复制文本抽词" v-on:click="ContentWordsPanel = !ContentWordsPanel"></i>
			<i class="fa fa-file-text fa-4x" title="上传文本抽词" @click="fileOpen">
				<input id="file" @change="handleFileChange" name="file" multiple="multiple" accept=".doc,.txt" type="file" data-show-preview="false" v-show="false"></i>
			<i class="fa fa-rotate-right fa-4x" title="清除所有"></i>
			<i class="fa fa-play-circle fa-4x" title="开始抽词"></i>
			<i class="fa fa-stop fa-4x" title="停止抽词"></i>
			<i class="fa fa-cloud-upload fa-4x" title="保存抽词"></i>
		</div>

		<div class="templatemo-content-widget white-bg text-center" v-show="ContentWordsPanel">
			<label class="control-label" for="inputNote" style="float: left;">请复制要抽词的文本到此处</label>
			<textarea class="form-control" id="inputNote" rows="3"></textarea>
			<button type="submit" class="templatemo-blue-button"
				style="margin: 1.25rem 0 0 0;border-radius: 3.125rem;">确定</button>
		</div>
		<div class="templatemo-flex-row flex-content-row">
			<div class="col-2">
				<div class="templatemo-content-widget white-bg">
					<div class="templatemo-content-widget white-bg">
						<baseCytoGraph @cyobj="getCy"></baseCytoGraph>
					</div>
				</div>
			</div>
		</div>
		<div class="templatemo-flex-row flex-content-row">

		</div>
	</div>
</template>

<script>
	import baseCytoGraph from "../tools/baseCytoGraph.vue"
	export default {
		components: {
			"baseCytoGraph": baseCytoGraph,
		},
		mounted() {

		},
		data() {
			return {
				ContentWordsPanel: false,
			}
		},
		methods: {
			getCy: function(cyobj) {
				this.cy = cyobj
			},
			fileOpen: function() {
				$('#file').click()
			},
			handleFileChange:function(e){
				const files = e.target.files;
				console.log(e)
			}
		}
	}
</script>

<style>
	.fa-4x {
		margin: 0 2.5vw 0 2.5vw;

	}

	.fa-4x:hover {
		color: #23527C;
		cursor: pointer;
	}
</style>
