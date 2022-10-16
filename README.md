# reaction-timer

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

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Lifecycle Methods 
1- Vue.createApp() => app.mount()

2- [beforeCreate] Hook => 
- this fires before the component is fully created and its at very start of initilization
- We cant access data from data object or any template elements yet

3- [created] Hook => 
- When it creates a component, it fires a created hook
- The component gets created but not mounted to the dom, So we cant access the data now but we can access the template

4- [beforeMount] Hook =>
- After this it starts compiling our template and when it does that, it fires the beforeMount Hook
- In here We can now access our data, events & templates

5- [Mounted] Hook => 
- 
