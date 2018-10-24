# Available Validation Rules
VeeVee comes with some basic validation rules out of the box. These rules have been designed to reflect the Laravel validation rules.   

## after
The field under validation must have a valid date and is after the date value in the target field.   

#### Params
* `target:` the other fields `ref` that gets validated against.
* `inclusion:` Whether to include equal dates.

## alpha
The field under validation may only contain alphabetic characters.

## alpha_dash
The field under validation may contain alphabetic characters, numbers, dashes or underscores.   

## alpha_num
The field under validation may contain alphabetic characters or numbers.

## alpha_spaces
The field under validation may contain alphabetic characters or spaces.

## before
The field under validation must have a valid date and is before the date value in the target field.

#### Params
* `target:` the other fields `ref` that gets validated against.
* `inclusion:` Whether to include equal dates.

## between
The field under validation must have a numeric value bounded by a minimum value and a maximum value.

#### Params
* `min:` the minimum value.
* `max:` the maximum value.

## confirmed
The field under validation must have the same value as the confirmation field.

#### Params
* `target:` the other fields `ref` that gets validated against.

## credit_card
The field under validation must be a valid credit card number.

## date_between
The field under validation must be a valid date between the two dates specified.

#### Params
* `min:` the minimum value.
* `max:` the maximum value.
* `inclusion:` Whether to include equal dates.

## date_format
The field under validation must be a valid date in the specified format. This rule must be present when using any date rule.

#### Params
* `format:` the format of the date [date-fns](https://date-fns.org/v2.0.0-alpha.7/docs/format)

## decimal
The field under validation must be numeric and may contain the specified amount of decimal points.

#### Params
* `decimals:` the maximum amount of decimals allowed

## digits
The field under validation must be numeric and have the specified number of digits.

#### Params
* `length:` the amount of digits

## dimensions
The file added to the field under validation must be an image (jpg,svg,jpeg,png,bmp,gif) having the exact specified dimension.

#### Params
* `width:` the width of the image
* `height:` the height of the image

## email
The field under validation must be a valid email.

## excluded
The field under validation value should not be in the specified list.

#### Params
* `list:` a list to check if a value is not included in

## ext
The file added to the field under validation must have one of the extensions specified.

#### Params
* `extensions:` the list of extensions, i.e. 'jpg,png,jpeg'

## image
The file added to the field under validation must have an image mime type (image/\*).

## included
The field under validation must have a value that is in the specified list.

#### Params
* `list:` a list to check if a value is included in

## ip
The field under validation must have a string that is a valid ipv4 value.

## is
The field under validation must be equal to the first argument passed, uses === for equality checks.

#### Params
* `value:` A value of any type to be compared to the fields value

## is_not
A negated version of the is rule

#### Params
* `value:` A value of any type to be compared to the fields value

## length
The field under validation must be an iterable and/or have a length property of the specified amount.

#### Params
* `length:` the length the iterable must be.
* `max:` the maximum length it must be, optional.

## max
The field under validation length may not exceed the specified length.

#### Params
* `length:` a numerical value representing the maximum value.

## max_value
The field under validation must be a numeric value and must not be greater than the specified value.

#### Params
* `length:` a numerical value representing the maximum value allowed.

## mimes
The file type added to the field under validation should have one of the specified mime types.

#### Params
* `list:` list of mime types, comma seperated. i.e. `mimes:image/jpeg,image/png`

## min
The field under validation length should not be less than the specified length.

#### Params
* `length:` a numerical value representing the minimum value.

## min_value
The field under validation must be a numeric value and must not be less than the specified value.

#### Params
* `length:` a numerical value representing the minimum value allowed.

## numeric
The field under validation must only consist of numbers.

## regex
The field under validation must match the specified regular expression.

#### Params
* `pattern:` a regular expression
* `flags:` a list of regexp flags, optional.

## required
The field under validation must have a non-empty value

## size
The file size added to the field under validation must not exceed the specified size in kilobytes.

#### Params
* `size:` the maximum file size allowed.

## url
The field under validation must be a valid url. Protocols are not required by default.
