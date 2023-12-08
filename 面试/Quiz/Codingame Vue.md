
# QCM

### Third-party packages with Vue.js
Language knowledge (40 pts)

What would be the best way to use a third-party package throughout an entire Vue application?  

- Register it globally in main.js
- Create a separate vue instance for it
- Use props to share it
- Import the package inside each component where it is used

### Lifecycle hooks - beforeUnmount
Language knowledge (40 pts)

Which Vue3 **lifecycle hook** is used for executing a task **before a component is removed** from the DOM?

- unmounted
- beforeUnmount
- beforeCreated
- beforeRemoved

### Vuex hot reloading
Language knowledge (40 pts)

Does **Vuex** support **hot reloading**? 

- Hot reloading is possible with Vuex
- Hot reloading is not possible with Vuex
- Hot reloading is possible with Vuex but modules can't be "hot" reloaded

### Effects of the `<keep-alive>` tag
Language knowledge (20 pts)

What happens to components inside of `<keep-alive>` tags?

- They are cached when inactive, avoiding rerenders
- They stay rendered even if the user reloads the page
- They can't be hidden using the `v-if` directive
- They remain active even if the user switched to another page

### Displaying data in a component
Language knowledge (20 pts)

How would you display the content of `message` inside of a component?

```javascript
// Component.vue
export default {
    return {
        data() {
            return {
                message: "Hello, world!"
            }
        }
    }
}
```

- 
```html
<!-- Component.vue -->
<p> {{ message }} </p>
```

- 
```html
<!-- Component.vue -->
<p> [[ message ]] </p>
```

- 
```html
<!-- Component.vue -->
<p><data>message</data></p>
```

- 
```html
<!-- Component.vue -->
<p v-data="message"></p>
```

### Passing data through props
Language knowledge (40 pts)

Which type of data CANNOT be passed to a component instance **using props** in Vue.js?

- String
- Component
- Object
- Boolean

### Looping through an array in Vue.js
Language knowledge (20 pts)

Which option would you choose to **loop through an array** named `products` in Vue.js?

- 
```html
<div v-for="product in products"></div>​
```

- 
```html
<div v-loop="::products"></div>
```

- 
```html
<div v-range="product of products"></div>  
```

- 
```html
<div v-show="::products"></div>
```

- 
```html
<div v-loop="product in products"></div>​
```

- 
```html
<div v-for="product of products"></div>
```

### Access the root instance
Language knowledge (20 pts)

How do you access the root instance from inside of a component?

- 
```javascript
this.$root
```

- 
```javascript
this.root
```

- 
```javascript
this.$instance
```

- 
```javascript
this.instance
```

### Import package
Language knowledge (20 pts)

What syntax would you use to **import** a package in Vue.js?  

- 
```javascript
import 'vue' as Vue;
```

- 
```javascript
const Vue = require('vue');
```

- 
```javascript
require('vue') as Vue;
```

- 
```javascript
import Vue from 'vue';
```

### User navigation using Vue Router
Language knowledge (20 pts)

What is the correct syntax for handling **user navigation** when using **Vue Router**?

- 
```html
<route class="nav-link active" to="/">Home</route>
```

- 
```html
<router-path class="nav-path active" to="/">Home</router-path>
```

- 
```html
<router-link class="nav-link active" to="/">Home</router-link>	
```

- 
```html
<routerLink class="nav-link active" to="/">Home</routerLink>
```





# Text

### Else-if condition in Vue.js

Which directive is used for "**else** **if**" conditions in Vue.js?

### Two-way binding directive

Which Vue.js directive is used for **two-way data binding**?

# Code
