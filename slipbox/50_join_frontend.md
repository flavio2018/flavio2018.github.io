# Join frontend 
Here I'll take some notes specifically referred to the Join project ([github folder](https://github.com/lascuolaopensource/join)).

First, I am exploring the folder structure of the project, focusing on the `/frontend` folder, since it's what I will have to focus on. The folder structure of `frontend/src` is the following:

```
frontend/src/  
├── assets  
├── components  
├── features  
│   ├── base  
│   │   ├── containers  
│   │   ├── store  
│   │   └── views  
│   ├── courses  
│   │   ├── containers  
│   │   ├── routes  
│   │   ├── store  
│   │   └── views  
│   └── home  
│       └── views  
├── gql  
├── graphql  
├── locale  
├── plugins  
├── router  
└── store
```

I an trying to understand what each of these folders is about here [49_vuejs](49_vuejs.md).

Some relevant questions: 
1. why is the folder `store` replicated inside `features` folders? 
 	see [[52_vuex#What is a store]]
1. why do all features folders *partially* have the same structure?
2. why are folders `features`, `gql`, `graphql`, `locale`, `plugins` not present in the example project?
3. what is the difference between `gql` and `graphql`?
4. what is `containers`? 
	see [[49_vuejs#What are containers]]
	
## User login
[How to build forms](https://vuejs.org/v2/guide/forms.html)
[Call getters from action](https://stackoverflow.com/questions/52048944/vuex-call-getters-from-action)
[Vuex Store getters](https://vuex.vuejs.org/guide/getters.html#property-style-access)
[Redirect after form submit](https://stackoverflow.com/questions/49599274/how-to-submit-a-form-in-vue-redirect-to-a-new-route-and-pass-the-parameters#49609883)