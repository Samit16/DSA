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
## 8. Move Zeros
```
class Solution {
    public void moveZeroes(int[] nums) {
        int j = 0;
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                int temp = nums[i];
                nums[i] = nums[j];
                nums[j] = temp;
                j++;
            }
        }
    }
}
```
## 9. Search insert position 
```
class Solution {
    public int searchInsert(int[] nums, int target) {
        int k=0;
        for (int i=0;i<nums.length;i++){
            if ( nums[k]>target || nums[k]==target){
                return k;
            }
        }
        return nums.length;
    }
}
```
## 10. Plus one
```
class Solution {
    public int[] plusOne(int[] digits) {
        int n = digits.length;
        for (int i = n - 1; i >= 0; i--) {
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            } else {
                digits[i] = 0;
            }
        }
        int[] result = new int[n + 1];
        result[0] = 1;

        return result;
    }
}
```
## 11. Single Number
```
class Solution {
    public int singleNumber(int[] nums) {
        int ans = 0;
        for (int num : nums) {
            ans ^= num;
        }
        return ans;
    }
}
```
## 12. Majority Element
```
class Solution {
    public int majorityElement(int[] nums) {
        int candidate=0;
        int count=0;
        for (int i=0;i<nums.length;i++) {
            if(count==0){
                candidate=nums[i];
                count=1;
            }
            else{
                if (nums[i]==candidate){
                    count++;
                }
                else{
                count--;
                }
            }
        }
        return candidate;
    }
}
```
-> used boore moyre voting method for this


## 13. Strictly Palindromic Number
```
class Solution {
    public boolean isStrictlyPalindromic(int n) {
        return false;
    }
}
```
