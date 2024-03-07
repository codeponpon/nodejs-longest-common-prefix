# nodejs-longest-common-prefix
## Question:
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:
Input: strs = ["flower","flow","flight"]
Output: "fl"


Example 2:
Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

Constraints:
* 1 <= strs.length <= 200
* 0 <= strs[i].length <= 200
* strs[i] consists of only lower-case English letters.


## The solution is
```
function solution(strs) {
  // 1 <= strs.length <= 200
  if(strs.length == 0 || strs.length > 200) return ""

  // 0 <= strs[i].length <= 200
  const tooLength = strs.find((str) => str.length > 200)
  if(tooLength) return ""


  let resp = strs[0]
  for( let i = 1; i < strs.length; i++){
    while(strs[i].indexOf(resp) != 0){
      resp = resp.substr(0, resp.length - 1)
    }
  }

  return resp
}

const strs1 = ["flower", "flow", "flight"];
const strs2 = ["dog", "racecar", "car"];
console.log(solution(strs1)) // Output: "fl"
console.log(solution(strs2)) // Output: ""
```
