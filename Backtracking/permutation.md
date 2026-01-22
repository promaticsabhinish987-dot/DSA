# Permutation

### Formula to find the number of all permutation = n!
### Formula to find the number of all unique permutation = n!/f1!*f2!

1. Generate all the permutation of a string.(with recursion)

```javascript
//print all the permutation of a string with recursion
function permut(str) {
    let result = [];
    function permutation(inputstr, outputstr) {
        if (inputstr == "") {
            result.push(outputstr)
            return
        }

        for (let i = 0; i < inputstr.length; i++) {
            let newInput = inputstr.slice(0, i) + inputstr.slice(i + 1);
            let newOutput = outputstr + inputstr[i];
            permutation(newInput, newOutput)
        }

    }
    permutation(str, "")
    return result;
}


console.log(permut("abc")) // ['abc', 'acb', 'bac', 'bca', 'cab', 'cba']
```

? what is the problem with this code.
“It works, but it does not handle duplicate characters and has factorial time complexity.”

2. Handle duplicate (you can skip the duplicate or use a set)

```javascript
//using a set very simple and clean

function uniquepermute(str) {
    let result = new Set();
    function permutation(inputstr, outputstr) {
        if (inputstr == "") {
            result.add(outputstr)
            return
        }

        for (let i = 0; i < inputstr.length; i++) {
            let newInput = inputstr.slice(0, i) + inputstr.slice(i + 1);
            let newOutput = outputstr + inputstr[i];
            permutation(newInput, newOutput)
        }

    }
    permutation(str, "")
    return [...result];
}


console.log(uniquepermute("abbb")) // ['abbb', 'babb', 'bbab', 'bbba']
```

Generates all permutations, including duplicates
Uses a Set to filter duplicates at the end
Printing the same document 10 times and then deleting 9 copies. 

```javascript
//unique permutaion by skipping the duplicate character at a level of recursion

function uniquepermute(str) {
    let result = [];
    function permutation(inputstr, outputstr) {
        if (inputstr == "") {
            result.push(outputstr)
            return
        }
        let set=new Set();
        for (let i = 0; i < inputstr.length; i++) {
            if(set.has(inputstr[i])) continue;
            set.add(inputstr[i])
            let newInput = inputstr.slice(0, i) + inputstr.slice(i + 1);
            let newOutput = outputstr + inputstr[i];
            permutation(newInput, newOutput)
        }

    }
    permutation(str, "")
    return result;
}


console.log(uniquepermute("abb"))
```
use it for interview.
It is optimized and prefered.
“Skipping duplicates during recursion is better because it avoids unnecessary work and reduces time and space overhead.”
we have to use a normal set and it will use minimum space.
No recursive call for the duplicate. take more recursive space if we call with duplicate.





















