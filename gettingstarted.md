# Getting Started

## Installation
VeeVee is installed using [_**npm**_](https://npmjs.com).   
```bash
npm install --save veevee
```  

## Vue Installation
```js
import Vue from 'vue';
import VeeVee from 'veevee';

Vue.use(VeeVee);
```  

## Basic Usage
VeeVee includes most rules that can be found in laravel's validation. On any input field that you desire, you can add the `v-validate` attribute.  
Your input **needs** to have a name, so that it can be displayed correctly in error messages.   

The `v-validate` directive is a formatted string that follows the same guidelines outlined in Laravel. You can also use an object, if you desire custom bindings.   

> **Example:** A required email input
```html
<input v-validate="'required|email'" name="email" type="text">
<!-- Alternatively, the object syntax -->
<input v-validate="{required: true, email: true}" name="email" type="text">
```   

To get the errors for this, VeeVee provides an _**ErrorBag**_ which automatically gets bound to `errors`, and can be accessed as such.
```html
<ul>
    <li v-for="error in errors.all()">Error: {{ error }}</li>
</ul>

<span>Error: {{ errors.first('email') }}</span>
```

To keep things simple, the ErrorBag automatically groups errors based on rules, and as such will only show the first error for any given rule when using `errors.all()`, this of course can be overridden in the config.  
