# Svelte Web component

  1.  Clone this repo and install dependencies

   ```
        npm install
   ```

   2. Run the application,

   ```
    npm run dev
   ```

   3. Access the application on the url displayed in the logs


# Explanation of the issue

  Building a web component in Svelte, while importing third party libraries for example **layercake** .

  As of now all components should have the tag,

  ```
    <svelte:options tag=”my-layercake-map” immutable={true} />
  ```

  Since we do not have control over external libraries to have this tag, there is no way to import/make use of some of the wonderful libraries like **layercake** in our custom component.



# This branch

  You will get compilation error, **No custom element 'tag' option was specified**
  ```
bundles src/main.ts → public/build/bundle.js...
(!) Plugin svelte: No custom element 'tag' option was specified. To automatically register a custom element, specify a name with a hyphen in it, e.g. <svelte:options tag="my-thing"/>. To hide this warning, use <svelte:options tag={null}/>
node_modules/layercake/src/LayerCake.svelte
1: <script>
   ^
2: import { setContext } from 'svelte';
3: import { writable, derived } from 'svelte/store';
node_modules/layercake/src/layouts/Webgl.svelte
1: <script>
   ^
2: import { getContext, onMount, setContext } from 'svelte';
3: import { writable } from 'svelte/store';
node_modules/layercake/src/layouts/Svg.svelte
1: <script>
   ^
2: import { getContext } from 'svelte';
3: 
node_modules/layercake/src/layouts/Canvas.svelte
1: <script>
   ^
2: import { getContext, onMount, setContext } from 'svelte';
3: import { writable } from 'svelte/store';
node_modules/layercake/src/layouts/ScaledSvg.svelte
1: <script>
   ^
2: import { getContext } from 'svelte';
3: 
node_modules/layercake/src/layouts/Html.svelte
1: <script>
   ^
2: import { getContext } from 'svelte';
3: 
(!) Circular dependencies
node_modules/d3-interpolate/src/value.js -> node_modules/d3-interpolate/src/array.js -> node_modules/d3-interpolate/src/value.js
node_modules/d3-interpolate/src/value.js -> node_modules/d3-interpolate/src/object.js -> node_modules/d3-interpolate/src/value.js
created public/build/bundle.js in 1.6s

  ```