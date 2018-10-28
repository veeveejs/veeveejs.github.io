# Custom Validation Rules
As customization is a core principal of the VeeVee library, you are able to create custom validation rules.

## Creating a custom rule
In its most basic form, a custom rule will contain only one function, `validator` that returns either a promise or a boolean. This custom rule will only have the default error message.
```javascript
const validator = (value, args) => {
  // Return boolean or a promise that resolves to a boolean.
}
```  

In order to make a more advanced rule, with custom error messages, you can create rules in an object format, that contains the `validate` function, and the `getMessage` function.
```javascript
const validator = {
  getMessage(field, args) {
    // Gets merged into the currently selected locale
    // Returns a message, string, etc.
  },
  validate(value, args) {
    // Return boolean or a promise that resolves to a boolean.
  }
}
```
> **Please Note,** that the `validate` function is required.  
> Furthermore, a custom validator must be an implementation of one of the two implementations shown above.  
> Failure to do so, will throw an exception detailing what you were missing when creating your rule.

## Using a custom rule
Once you have created your custom rule, you can then add it to the list of rules by using the `extend(name, validator)` method on the Validator instance.  
```javascript
import { Validator } from 'veevee';

Validator.extend('truth', {
  getMessage: (field, args) => `The ${field} value is not the truth!`,
  validate: (value) => !! value
});

let validatorInstance = new Validator({ trueField: 'truthy' });

// Extend on the instance
validatorInstance.extend('false', (value) => !value);

validatorInstance.attach({
  name: 'falseField',
  rules: 'false'
});
```
> **Tip**  
> When you use extend on either an instance of Validator, or on the root Validator, any rules created will then be shared between **ALL** Validator instances.

You can then use your rule like any other rule: 
```html
<input type="text" name="field" v-validate="'truth'" />
```

## Example backend validator
From time to time you might need to validate more advanced cases against your backend server, i.e. validating a result is unique in a database. This following example is a dummy request, but shows how this could be implemented.
```javascript
import axios from 'axios';
import { Validator } from 'veevee';

const isUniqueEmail = (value) => {
  return axios.post('/api/validate/email', {email: value}).then((response) => {
    // Note that we return an object with the status, and message (valid | data->message)
    return {
      valid: response.data.valid,
      data: {
        message: response.data.message
      }
    }
  });
}

Validator.extend('unique_email', {
  validate: isUniqueEmail,
  getMessage: (field, params, data) => {
    return data.message;
  }
});
```

## Advanced custom rules
...
### Target dependent
...

### Non-immediate
...

### Custom reasoning
...
