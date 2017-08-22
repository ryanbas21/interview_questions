## SumPair

Given two input values:

- an array of integers of finite length, sorted in ascending order, of which numbers can repeat,
- a sum which is an integer number greater than 0

find 2 values in the array which added to eachother would equal to the sum given. 

Optimise your code with performance in mind. Can you do it with only one loop?

## Example 

Given the values:

```js
const input = [1, 2, 3, 4, 5];
const result = 8;
```

The pair `3` + `5` will satisfy the assumption - `8`.

## Solution

<details><summary>Click to see a solution</summary><p>

```js
function test(input, sum) {
  for(var i = 0, e = input.length - 1 ; i < e ; ) {
    if(i >= e) return null;
    let sumTest = input[i] + input[e];
    if(sumTest === sum) {
      return [input[i], input[e]];
      break;
    }
    if(sumTest < sum) i++;
    else if(sumTest > sum) e--;
  }
}

console.log(test([1,2,3,4,5], 8));
```