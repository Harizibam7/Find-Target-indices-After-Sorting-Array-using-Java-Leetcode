# Find-Target-indices-After-Sorting-Array-using-Java-Leetcode

    import java.util.*;
    class Solution {
        public static void sort(int[] arr, int n){
            boolean swapped;
            for(int i =0; i<n-1;i++){
                swapped = false;
                for(int j =0; j<n-i-1;j++){
                    if(arr[j]>arr[j+1]){
                        int temp;
                        temp = arr[j];
                        arr[j] = arr[j+1];
                        arr[j+1]= temp;
                        swapped= true;
                    }
                }
                if(swapped==false){
                    break;
                }
            }
        }
        public List<Integer> targetIndices(int[] nums, int target) {
            List<Integer> list = new ArrayList<Integer>();
            int n = nums.length;
            sort(nums,n);
            for(int i =0; i<nums.length;i++){
                if(nums[i]==target){
                    list.add(i);
                }
            }
            return list;
        }
    }
