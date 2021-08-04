## What is Vuex?
[Official answer here](https://vuex.vuejs.org/#what-is-a-state-management-pattern)

A Vue.js application consists of a *state*, a set of *components* (some of which can be *views*), and a set of *actions*, i.e. methods responding to user activity modifying the state.

Vuex is a pattern *and* a library implementation designed do deal with the problem of shared state between components, hence also managing concurrent requests of access and modification to the state. 

![vuex](https://vuex.vuejs.org/vuex.png)

### What is a store?
(Understanding what is in `store/index.js`).
[The simplest store](https://vuex.vuejs.org/guide/#the-simplest-store) and [State](https://vuex.vuejs.org/guide/state.html) in Vuex official guide.

The Store is the core component in the Vuex pattern. It is the place where the application state is saved. It is reactive to changes made by the components, which can only happen indirectly by using explicitly defined operations called ***mutations***.

The store state can be accessed like `store.state`, and it can be changed calling a mutation like `store.commit(<mutation-name>)`.

The store can be accessed from components by injecting it at the moment of a component instantiation. The store can even be accessible from the children components of a root component (after all, the state is application-wide) if it's passed at the moment of instantiation with the `store` option:
```
new Vue({
	el: '#app',
	store: store,
})
```

Then, we can embed the `store`'s mutation into one of the component's methods which simply trigger the mutation (e.g. method `increment` embedding a mutation of the state with the same name).

## Vuex Modules
[On the website](https://vuex.vuejs.org/guide/modules.html)

Since components could have individual state that is not or partially shared with other components, we would like to have "local stores" for each component: these are called Modules. Eventually, when the store of the application will be built, all local modules will be part of it; but, conceptually, we can see them associated with a single component.