# vue_crash_todolist

## tips

if you need to generate unique id, use 'npm install uuid'

when using @sumbit on form browser reloads every time, to prevent it use @submit.prevent
or 
you can call e.preventDefault() in your method 

to catch an $emit use v-on:name="method you'll be using"

how to add an object to existing array -> use a spread operator [...arrayName] to copy whats already in an array and add your object e.g this.todos = [...this.todos, newTodo]

created() -> fires off when component loads

api request made with axios -> first install using npm : npm i axios
axios is basically an http library, where we can make get, post, etc requests

always import librarys you intend to use

?_limit=10 at the end of api get url limits data to 10

destructuring is used to pull out specific data const ""const { title, completed } = newTodo "" from object

backtick on estonian mac keyboard shift +
## When development is finisehed use npm run build from cli or do it from the vui
## Vue ui
to start type `vue ui` into terminal
you can add vue router and vuex from there
be warned - adding vue router from there will overwrite app.vue file. you should install it beforehand starting development

## JSONPlaceholder.typicode.com
Fake online REST API for Testing and Prototyping




## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
