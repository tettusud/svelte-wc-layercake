<script>
	import { LayerCake, Html } from 'layercake';
  </script>
  <svelte:options tag="hello-world" immutable={true} />
  
  <style>
	.chart-container {
	  width: 100%;
	  height: 300px;
	}
  </style>
  
  <div class="chart-container">
	<LayerCake>
	  <Html zIndex={1}>  
		 I do not compile
	  </Html>
	</LayerCake>
  </div>