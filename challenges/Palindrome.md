
**Write a function that takes in a string and identifies the longest palindrome in that string through any combination of the letters.**
```
Example Input -> Output
racecar -> racecar || carerac
racecarff -> racfefcar
abbccc -> bcccb || bcacb
```

<details><summary>See example code</summary><p>

---
    
```javascript
function isPalindrome(str) {
  return str.split('').reverse().join('') === str;
}

function toPalindrome(str) {
  const characters = str.split('');
  const characterMap = {};

  characters.forEach(char => {
    if (!(char in characterMap)) {
      characterMap[char] = 0;
    }

    characterMap[char]++;
  });

  // Pull out any odd numbered characters
  const oddCharacterNumbersLetter = Object.keys(characterMap).find(key => {
    if (characterMap[key] % 2 == 0) {
      return false;
    }

    return true;
  });

  const palindromeArr = [];

  // Start with odd number, if available
  if (oddCharacterNumbersLetter) {
    const arrayOfOddLetters = new Array(characterMap[oddCharacterNumbersLetter]).fill(oddCharacterNumbersLetter);
    arrayOfOddLetters.forEach(letter => {
      palindromeArr.push(letter);
    });
  }

  // Remove early input
  delete characterMap[oddCharacterNumbersLetter];

  Object.keys(characterMap).forEach(key => {
    const thisCharacterAmount = characterMap[key];
    const thisCharacterInstances = new Array(thisCharacterAmount).fill(key);

    while (thisCharacterInstances.length % 2 !== 0) {
        thisCharacterInstances.pop();
    }

    thisCharacterInstances.forEach(thisCharacterInstance => {
      if (palindromeArr.length % 2 === 0) {
                palindromeArr.push(thisCharacterInstance);
      } else {
          palindromeArr.unshift(thisCharacterInstance);
      }
    });
  });


  return palindromeArr.join('');
}
```

---

</p></details>
