# Using Glimmer as Web Components

To use the components we have built so far, you will need to add an empty html tag on your external page, where you want the component to load, something like `<div id="my-component-here"></div>`. Additionaly, you will need to add a bit of JavaScript to find the tag and load your component into it. Instead of doing all that, ideally it would be great to just use `<my-component />` and eliminate the empty tag and JS setup steps. This is where Web Components come in (http://w3c.github.io/webcomponents/spec/custom/). Web Components have an enormous potential to enable us to extend the browsers limited set of tags with our own custom tags. 

With Glimmer you can also create components as web components. Let's do another new app setup. Instead of doing an installation like we did originally, we'll now run the following command:

```sh
ember new display-tile -b @glimmer/blueprint --web-component
```

When we add the `--web-component` flag, we reconfigure our app to expose our `display-tile` component as a Web Component to browsers. That in turn allows us to render markup like the following from a backend:

```hbs
<display-tile />
```
Once we add our `app.js` file to the page, our browser will automatically load our Glimmer component into the DOM using the options provided by the backend and will boot each Glimmer app.

For more information about web components, browser support and various polyfills to enable broader support, please see:

- [https://www.webcomponents.org/introduction](https://www.webcomponents.org/introduction)
- [https://www.webcomponents.org/polyfills](https://www.webcomponents.org/polyfills)
- [http://jonrimmer.github.io/are-we-componentized-yet/](http://jonrimmer.github.io/are-we-componentized-yet/)

*Note* You cannot currently pass arguments to top-level Glimmer components due to technical limitations. We are working on removing this restriction.
