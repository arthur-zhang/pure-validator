# pure-validator

based on chriso's [`validator.js`](https://github.com/chriso/validator.js), but improve it by compare type, you can use it in nodejs with [`pure-validator-node`](https://www.npmjs.com/package/pure-validator-node)

## Installation

```
npm install pure-validator
```

## Usage
```
var validator = require('pure-validator');
validator.isEmail('foo@bar.com'); //=> true
```
####`customValidators`
```
var rules = {
  isDate: {
    fn: function(value) {
      return validator.matches(value, /^(19|20)[0-9]{2}[-](0[1-9]|1[012])[-](0[1-9]|[12][0-9]|3[01])$/);
    },
    message: 'Must be formatted as 1900-01-01 and between 1900-01-01 and 2099-12-31'
  }
};
validator.extend(rules);
```

### Optional input

You can use the `optional` to check an input only when the input exists.

### methods

- **equals(str, comparison)** - check if the string matches the comparison.
- **contains(str, seed)** - check if the string contains the seed.
- **matches(str, pattern [, modifiers])** - check if string matches the pattern. Either `matches('foo', /foo/i)` or `matches('foo', 'foo', 'i')`.
- **isEmail(str)** - check if the string is an email.
- **isURL(str [, options])** - check if the string is an URL. `options` is an object which defaults to `{ protocols: ['http','https','ftp'], require_tld: true, require_protocol: false, allow_underscores: false, host_whitelist: false, host_blacklist: false, allow_trailing_dot: false }`.
- **isFQDN(str [, options])** - check if the string is a fully qualified domain name (e.g. domain.com). `options` is an object which defaults to `{ require_tld: true, allow_underscores: false, allow_trailing_dot: false }`.
- **isIP(str [, version])** - check if the string is an IP (version 4 or 6).
- **isAlpha(str)** - check if the string contains only letters (a-zA-Z).
- **isNumeric(str)** - check if the string contains only numbers.
- **isAlphanumeric(str)** - check if the string contains only letters and numbers.
- **isBase64(str)** - check if a string is base64 encoded.
- **isHexadecimal(str)** - check if the string is a hexadecimal number.
- **isHexColor(str)** - check if the string is a hexadecimal color.
- **isLowercase(str)** - check if the string is lowercase.
- **isUppercase(str)** - check if the string is uppercase.
- **isInt(str)** - check if the string is an integer.
- **isFloat(str)** - check if the string is a float.
- **isDivisibleBy(str, number)** - check if the string is a number that's divisible by another.
- **isNull(str)** - check if the string is null.
- **isLength(str, min [, max])** - check if the string's length falls in a range. Note: this function takes into account surrogate pairs.
- **isByteLength(str, min [, max])** - check if the string's length (in bytes) falls in a range.
- **isUUID(str [, version])** - check if the string is a UUID (version 3, 4 or 5).
- **isDate(str)** - check if the string is a date.
- **isAfter(str [, date])** - check if the string is a date that's after the specified date (defaults to now).
- **isBefore(str [, date])** - check if the string is a date that's before the specified date.
- **isIn(str, values)** - check if the value is in a array of allowed values.
- **isCreditCard(str)** - check if the string is a credit card.
- **isISBN(str [, version])** - check if the string is an ISBN (version 10 or 13).
- **isMobilePhone(str, [, locale])** - check if the string is a mobile phone number, (locale should be locales, like 'zh-CN', currently only support 'zh-CN').
- **isJSON(str)** - check if the string is valid JSON (note: uses JSON.parse).
- **isMultibyte(str)** - check if the string contains one or more multibyte chars.
- **isAscii(str)** - check if the string contains ASCII chars only.
- **isFullWidth(str)** - check if the string contains any full-width chars.
- **isHalfWidth(str)** - check if the string contains any half-width chars.
- **isVariableWidth(str)** - check if the string contains a mixture of full and half-width chars.
- **isSurrogatePair(str)** - check if the string contains any surrogate pairs chars.
- **isNotEmptyString**: 'Value must be a string and not be empty string',
- **isMd5**: 'Value must be a valid md5',
- **isMacAddress**: 'Value must be a valid mac address',
- **exists**: 'Value not exists',
- **isUndefinedOrNull**: 'Value must be undefined or null',
- **isTypArray**
- **isTypObject**
- **isTypString**
- **isTypDate**
- **isTypRegExp**
- **isTypFunction**
- **isTypBoolean**
- **isTypNumber**
- **isTypeNull**
- **isTypeUndefined**

## License

Copyright (c) 2014 Arthur Zhang <zhangya_no1@qq.com>, MIT License
