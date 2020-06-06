# Random pick with weight
## https://leetcode.com/problems/random-pick-with-weight


# Implementation :
```java
class Solution {
    int[] prefixSums;
    int totalSum;
    
    public Solution(int[] w) {
        prefixSums = new int[w.length];
        int sum = 0;
        for(int i = 0; i < w.length; i++) {
            sum += w[i];
            prefixSums[i] = sum;
        }
        totalSum = sum;
    }
    
    public int pickIndex() {
        double target = Math.random() * totalSum;
        for(int i = 0; i < prefixSums.length; i++) {
            if(target < prefixSums[i])
                return i;
        }
        
       return -1; 
    }
    
}

/**
 * Your Solution object will be instantiated and called as such:
 * Solution obj = new Solution(w);
 * int param_1 = obj.pickIndex();
 */
```
