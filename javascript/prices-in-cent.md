# Handling prices reflected as integer amount in cent

A price $15.90 can be reflected as 1590 cent. It's convenient when you don't need more than two decimal points accuracy and it prevents some floating point weirdness like [0.1 + 0.2 ≠ 0.3](https://www.quora.com/Why-is-0-1+0-2-not-equal-to-0-3-in-most-programming-languages).

To split one integer into two at the third but last digit, do

```js
const price = 1590;

const cent = price % 100;
const dollars = price / 100 | 0;
```

The bitwise or with 0 in Javascript trims the decimal part and leaves the integer part of any number.
