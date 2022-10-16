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
- Popular for making fetch requests if you need data from your component

[Note]  You can also make fetch requests in different like [created] or [beforMount]

- Once the component is mounted, we know that data can change either over time or reaction to use events like clicking buttons now when that happens/or data starts to change. It fires 

6- [beforeUpdate] Hook => 
- When data updates or changes it fires this hook. This happens after the data change but before the updates being re-rendered to the DOM

7- [updated] hooks => 
- Once they are rendered to the DOM, We fired the updated hook and that's after all of the updates have been reflected in the browser

8- [beforeUnmount] & [Unmounted] hook => 
- So once the component no longer needed on the screen in the browser, it's removed. 
- These two hooks are being used for removal of the component 
