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
