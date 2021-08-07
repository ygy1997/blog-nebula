<template>
	<div>
		<div id="cyToolBar">
			<i class="fa fa-dot-circle-o  fa-lg" aria-hidden="true"></i>
			<i class="fa fa-refresh fa-lg" aria-hidden="true"></i>
		</div>
		<div id="cygraph">
			
		</div>
	</div>
</template>

<script>
	const printf = console.log
	import cytoscape from 'cytoscape'
	export default {
		mounted:function() {
			this.$nextTick(function () {
				this.initGraph()
			})
		},
		watch: {

		},
		components: {
			
		},
		data() {
			return {

			}
		},
		created() {

		},
		methods: {
			initGraph(graphJson){
				var cy = cytoscape({
				  // very commonly used options
				  container: document.getElementById('cygraph')	,
				  elements: [ /* ... */ ],
				  style: [ /* ... */ ],
				  layout: { name: 'grid' /* , ... */ },
				  data: { /* ... */ },
				
				  // initial viewport state:
				  zoom: 0.25,
				  pan: { x: 100, y:100},
				
				  // interaction options:
				  minZoom: 1e-50,
				  maxZoom: 1e50,
				  zoomingEnabled: true,
				  userZoomingEnabled: true,
				  panningEnabled: true,
				  userPanningEnabled: true,
				  boxSelectionEnabled: true,
				  selectionType: 'single',
				  touchTapThreshold: 8,
				  desktopTapThreshold: 4,
				  autolock: false,
				  autoungrabify: false,
				  autounselectify: false,
				
				  // rendering options:
				  headless: false,
				  styleEnabled: true,
				  hideEdgesOnViewport: false,
				  textureOnViewport: false,
				  motionBlur: false,
				  motionBlurOpacity: 0.2,
				  wheelSensitivity: 1,
				  pixelRatio: 'auto'
				});
				var eles = cy.add([
				  { group: 'nodes', data: { id: 'n0' }, position: { x: 100, y: 100 } },
				  { group: 'nodes', data: { id: 'n1' }, position: { x: 200, y: 200 } },
				  { group: 'edges', data: { id: 'e0', source: 'n0', target: 'n1' } }
				]);
				if (graphJson != null){
					cy.json(graphJson)
				}
				this.$emit('cyobj',cy)
			},
		}
	}
</script>

<style>
	#cyToolBar{
		width: 100%;
		height:3.25rem;
	}
	#cyToolBar i{
		font-size: 2em;
		margin-right: 5rem;
	}
	#cygraph{
		
		width: 100%;
		height:50.5rem;
		border-style: dotted;
		border-color: #000000;
	}
</style>
