# Vue.js
Reference book: [@hanchett_vuejs_2018](@hanchett_vuejs_2018.md)

*In Join we use Vue.js 2.6*

For starters, we need some to understand the structure of a general Vue.js project: ([vue.js project structure](https://itnext.io/how-to-structure-a-vue-js-project-29e4ddc1aeeb)). 
In this project, we have some folders in common with Join:
- `assets`: things that are imported in components go here; these are probably things like `css` scripts, pictures and possibly JavaScript snippets.
- `components`: components that are not views
- `router`: the routes to components which are routed, hence to views
- `store`: «Vuex constants in mutation-type.js; the Vuex modules in the subfolder modules (which are then loaded in the index.js)» ([What is Vuex](52_vuex.md)).
- `views`: these are components which are routed, hence they have a URL and can be accessed directly

## What are containers?
It looks like containers are special components, which also implement logic. On the other hand, simpler components, which only fetch and display data (= "view" components), are simply called components and are (I guess) stored elsewhere.

## Naming conventions
[Official Vue 2.x styleguide](https://vuejs.org/v2/style-guide/)

- simple components (not containers) should start with "Base" or "V" or "App";
- only one component per file
- components used only once in a page should start with "The" (e.g. TheNavbar);
- child components (i.e. components embedded in a parent component) should be named starting with the parent component's name (e.g. UserCard and UserCardPhoto).
- don't abbreviate names of files and components: UserCardPhoto, not UCPhoto

## Declarative rendering
From [Vue.js official guide](https://vuejs.org/v2/guide/)

The core of Vue.js applications is programmatic manipulation of DOM objects (parts of the HTML page, such as `div`s). This is done under the hood by instances of the `Vue` class, which are linked to the HTML elements and possess attributes (e.g. `data`) which can be rendered in the final page. The HTML element that a `Vue` instance is linked to is specified instead in the `el` attribute, which can reference to a specific CSS `id`, `class` or (maybe?) even to an HTML tag.

### Directives
Vue.js introduces some special attributes that can be used in the HTML tags to obtain a specific dynamic behaviour of the page. These attributes have the form `v-<something>` and are called *directives*. 

Something powerful which can be done with directives is manipulate the *structure* (and not only the content) of the HTML page. For example, we can use the directives `v-if` and `v-for` in some HTML element linked to a `Vue` object instance to dynamically modify its structure depending on the values defined in the `Vue` instance.

To design more complex behaviour corresponding to user activity on the website we can use `Vue`'s instances *methods*. These are common objects methods which can be used to manipulate data in the `Vue` instance, which are maybe then displayed in the website.

## Components
Components are definitions of special `Vue` objects that can be used in HTML code (and thus even in other components). In practice, a component can be used via an HTML tag named after it and especially defined by Vue. 

Every component can be "registered" in the Vue.js application and then used elsewhere in the app. A component usually includes a `template` attribute, which is its HTML skeleton. It can also define one or more `props`, which are other attributes whose value can be manipulated from other components using the `v-bind` directive inside the components HTML tag.

```
Vue.component('my-component', {
	props: ['message', 'color'],
	template: '<div>Any dynamic HTML code here: {{message.text}}!</div>'
	})
	
<div>
	<my-component>
		v-bind:message='ciao'
	</my-component>
</div>
```

No HTML code is written in the final page, since we use the one defined in template, which we can dynamically modify. Also, if the `div` in the page were linked to another `Vue` instance, we could have used the data of the parent component in the child one, e.g. passing them as `props` values.

- A Vue application has always one and only one root component, which contains other Vue objects that are reusable components themselves.
- The template is used to *declaratively* bind the web page contents to the contents of the data object of the Vue instance that possesses the template. This bind can happen in several ways, the simplest of which is the Moustache syntax: `{{<data_property_name>}}`. However, this only works with plain text (and not HTML code, for example).

## How does the router in Vuejs work?
[Official answer](https://router.vuejs.org/guide/#javascript)