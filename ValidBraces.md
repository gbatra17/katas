Prompt: 
Write a function that takes a string of braces, and determines if the order of the braces is valid. 
It should return true if the string is valid, and false if it's invalid.

All input strings will be nonempty, and will only consist of parentheses, brackets and curly braces: ()[]{}.

What is considered Valid?
A string of braces is considered valid if all braces are matched with the correct brace.

*Examples*
"(){}[]"   =>  True
"([{}])"   =>  True
"(}"       =>  False
"[(])"     =>  False
"[({})](]" =>  False

Solution:
```javascript
function validBraces(braces){
  const valid = {
    '(': ')',
    '{':'}',
    '[':']'
  }
  
  const braceArray = braces.split('');
  const newArray = [];
  
  for(var i = 0; i < braceArray.length; i++){  
    if(braceArray[i] === valid[newArray[newArray.length-1]]){
      newArray.pop();
    } else {
      newArray.push(braceArray[i]);
    }
  }
  
  return newArray.length === 0;
}
```
