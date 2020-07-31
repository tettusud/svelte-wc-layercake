<script>
	import { LayerCake, Html } from 'layercake';
  </script>
  
  <style>
	.chart-container {
	  width: 100%;
	  height: 300px;
	}
  </style>
  
  <div class="chart-container">
	<LayerCake>
	  <Html zIndex={1}> <!-- Optional z-index -->
		  Hello Layer cake
	  </Html>
	</LayerCake>
  </div>