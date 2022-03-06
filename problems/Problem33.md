```java
/*
There will be atmost 3 cases.
1. increasing left half and non uniform right half [3,4,5,1,2]
2. non uniform left half and increasing right half [5,1,2,3,4]
3. increasing left and right half [1,2,3,4,5]
*/
class Solution {
    public int search(int[] nums, int target) {
        
        int start = 0, end = nums.length-1;
        
        while (start <= end) {
            int mid = (start+end) / 2;
            
            if (nums[mid] == target) return mid;
            
            //left half strictly increasing
            if (nums[mid] >= nums[start]) {
                if (target >= nums[start] && target < nums[mid]) {
                    end = mid - 1;
                } else {
                    start = mid + 1;
                }
            } else {
                //right half strictly increasing
                if (target > nums[mid] && target <= nums[end]) {
                    start = mid + 1;
                } else {
                    end = mid - 1;
                }
            }
        }
        
        return -1;
    }
}
```
