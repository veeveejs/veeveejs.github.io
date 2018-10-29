# VeeVee Components
VeeVee also comes with a few additional components, to make the life of the developer a little easier. Currently these components are only to do with the displaying of errors.

## Error List (`<veevee-error-list>`)
This component is used for displaying all the errors in the error bag. 
```html
<veevee-error-list></veevee-error-list>
```
Is equivalent to doing the following
```html
<ul>
    <li v-for="error in errors.all()"><strong>Error: </strong>{{ error }}</li>
</ul>
```

## Error (`<veevee-error>`)
This component is used in the displaying of the first error in the error bag. Optionally you can pass a `field` prop and it will show the first error in the error bag for a given field.
```html
<input type="text" v-validate="'required|email'" name="email">
<veevee-error field="email"></veevee-error> <!-- Outputs the first error for the 'email' field. -->
<veevee-error></veevee-error> <!-- Outputs the first error in the error bag -->
``` 

Is equivalent to doing the following
```html
<input type="text" v-validate="'required|email'" name="email">
<span v-if="errors.has('email')"><strong>Error: </strong>{{ errors.first('email') }}</span>
<span v-if="errors.has('*')"><strong>Error: </strong>{{ errors.first('*') }}</span>
```
  
> **TIP**  
> The `<veevee-error>` component also accepts slots, for displaying a message after the error. As this is a span, it's usually handy to add a `<br>` element, to add a space afterwards.

```html
<veevee-error field="email"><br></veevee-error>
```
Is equivalent too
```html
<span v-if="errors.has('email')"><strong>Error: </strong>{{ errors.first('email') }}<br></span>
```
