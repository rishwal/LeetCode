# Scramble


**Given a string and an array of index numbers, return the characters of the string rearranged to be in the order specified by the accompanying array.**

## Ex:

**scramble('abcd', [0,3,1,2]) -> 'acdb'**

## My answer


```javascript

var firstPalindrome = function (words) {
    for (x of words) {
        if (x == x.split('').reverse().join('')) {
            return x;
        }

    }
    return "";
};
const words = ["abc", "car", "ada", "racecar", "cool"];
console.log(firstPalindrome(words));

```
