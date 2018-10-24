# Configuration

## Config
VeeVee provides an extensive amount of configuration options to change how the validator works at its core. These can all be passed through when installing the plugin on the Vue instance.   

```js
import Vue from 'vue';
import VeeVee from 'veevee';

const config = {
  aria: true,
  classNames: {},
  classes: false,
  delay: 0,
  errorBagName: 'errors', // change if property conflicts
  events: 'input|blur',
  fieldsBagName: 'fields',
  fastExit: false
  inject: true,
  validity: false
};

Vue.use(VeeVee, config);
```

## Config definitions
| Property        | Type            | Default     | Description   |
| :-------------- | :-------------- | :---------- | :------------ |
| aria            | `boolean` | `true` | Sets `aria-invalid` and `aria-required` on HTML 5 fields. |
| classNames      | `object` | `{}` | Classes that get applied to a field, based on their state and flags. |
| classes         | `boolean` | `false` | Automatically apply classes to HTML5 fields based on their state |
| delay           | `number` | `0` | Default debounce time before handling validation. |
| errorBagName    | `string` | `'errors'` | Name that gets bound to `data` of the vue component instance. |
| events          | `string` | <code>'input&#124;blur'</code> | Events that get tracked for validation |
| fieldsBagName   | `string` | `'fields'` | Name that gets bound to `data` of the vue component instance |
| fastExit        | `boolean` | `true` | Whether or not to keep checking for errors if there already has one for a given rule. |
| inject          | `boolean` | `true` | Specifies if the `$validator` instance should get injected automatically into components. |
| validity        | `boolean` | `true` | Whether or not to set custom validity constraints on inputs. |
