## 1. Two Sum
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] { i, j }; 
                }
            }
        }
        return new int[] {}; 
    }
}
```
## 2. Contains Duplicate
```
import java.util.HashSet;
import java.util.Set;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> seen = new HashSet<>();
        for (int num : nums) {
            if (seen.contains(num)) {
                return true;
            }
            seen.add(num);
        }
        return false;
    }
}
```
## 3. Valid Anagram
```
class Solution {
    public boolean isAnagram(String s, String t) {
        return s.length() == t.length() &&
                Arrays.equals(s.chars().sorted().toArray(),
                        t.chars().sorted().toArray());
    }
}
```
-> didn't get in first try, had to look for a solution
## 4. Valid Palindrome
```
class Solution {
    public boolean isPalindrome(String s) {
        String fixed="";
        for (char c: s.toCharArray()) {
            if (Character.isDigit(c) || Character.isLetter(c)) {
                fixed+=c;
            }
        }
        fixed=fixed.toLowerCase();

        int aptr=0;
        int bptr=fixed.length()-1;

        while(aptr<=bptr) {
           if (fixed.charAt(aptr)!=fixed.charAt(bptr)) {
            return false;
           }
           aptr++;
           bptr--;
        }
        return true;
    }
}
```
-> logic development was hard

## 5. Power of 3
```
class Solution {
    public boolean isPowerOfThree(int n) {
        if (n <= 0) {
            return false;
        }
        while (n % 3 == 0) {
            n /= 3;
        }
        return n==1;
    }
}
```
## 6. Power of 4
```
class Solution {
    public boolean isPowerOfFour(int n) {
        if (n<=0) {
            return false;
        }
        while (n % 4 == 0) {
            n/=4;
        }
        return n==1;
    }
}
```
## 7. Remove Element
```
import java.util.Arrays;
class Solution {
    public int removeElement(int[] nums, int val) {
        Arrays.sort(nums);
        int k=0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != val) {
                nums[k]=nums[i];
                k++;
            }
        }
        return k;
    }
}
```


