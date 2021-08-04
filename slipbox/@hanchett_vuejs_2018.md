---
title: Vue.js in action
authors: Erik Hanchett, Benjamin Listwon
year: 2018
abstract: Vue.js is a lightweight frontend framework, offering easy two-way data binding, a reactive UI, and a common-sense project structure. It uses UI patterns and modern HTML to deliver impossibly fast page loads, and silky smooth transitions– all from a tiny code footprint. It's a delight to develop in Vue using ordinary JavaScript and its integrated Vuex state management tool. "Vue.js in action" is your guide to building modern web apps. You'll start by exploring the reactive UI model while you get comfortable with Vue's unique features. Then, you'll go deeper as you build a shopping cart with an admin interface and the ability to manage stock! Finally, you'll extend your app, adding transitions, tests, and other key features until it's production ready
---
# Vue.js in action
[Resource on the Web]()

- Vue.js is an instantiation of the MVVM pattern, which came after the MVC pattern to allow building faster, more responsive web applications. With respect to the MVC pattern, interaction between the ViewModel and the Model, responsible of maintaining the state of the application updated, can be asynchronous, whereas the interaction between the Model and the Controller was synchronous and blocking for the View rendering.
![ModelViewView-Model.png](ModelViewView-Model.png.md)
- the use of functional programming also helps making the application more responsive (probably due to the possibility of parallelization?)

The way in which changes in the data in ViewModel are reflected in the View (webpage) depend on the lifecycle of Vue apps.

## 4
- the `v-model` directive is mainly used on forms and inputs in general, whereas the `v-bind` directive (used by `v-model` under the hood) can be used to bind any attribute of any HTML tag with values in the `data` of a component.
- 