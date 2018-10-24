# Error Messages
VeeVee comes with standard error messages for each of the default rules implemented. There is also a fallback error message, for when there are no matching messages. These are handled through the localization classes.

## Overwriting Messages
On each instance of the VeeVee validator there is a `localize` method, which will merge new messages into the internal localization dictionary. If there are any duplicates, the new values will take precedence and overwrite the old.   
> **Please Note**   
> It is important to note that any modifications to the internal dictionary will reflect among all VeeVee instances.  
> This is because all instances use the shared dictionary.   
> However, if you affect the dictionary of an instance, rather than the core Validator, it will only reflect in that instance.

Localization objects that are passed need to be "namespaced" by their locale, i.e. "en" for English.
```js
import { Validator } from 'veevee';

const newDictionary = {
  en: {
    messages: {
      email: () => "The email is wrong, please check again!"
    }
  }
};

Validator.localize(newDictionary); // Affects globally

let validator = new Validator();
validator.localize(newDictionary); // Only affects this instance
```
