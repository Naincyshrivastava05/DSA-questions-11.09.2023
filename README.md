Here is my solution of some DSA questions using sorting approaches, which is the part of my DSA learning.
Linkes for the question-
#links
- [Merge soted array](https://leetcode.com/problems/merge-sorted-array/)
- 
1.Merge two sorted array
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
      int left = 0; 
      int right = 0; 
      int index  = 0;
      int[] ans = new int[m+n];
      while(left<m&&right<n){
          if(nums1[left]<=nums2[right]){
         ans[index] = nums1[left];
        index++;
        left++;
          }
          else{
              ans[index] = nums2[right];
              index++;
              right++;
          }
      }
      while(left<m){
          ans[index++] = nums1[left++];
      }
      while(right<n){
          ans[index++]= nums2[right++];
      }
      for(int i=0; i<ans.length; i++){
          nums1[i] = ans[i];
      }
    }
}


https://leetcode.com/problems/majority-element/
https://leetcode.com/problems/missing-number/
https://leetcode.com/problems/intersection-of-two-arrays/
https://leetcode.com/problems/intersection-of-two-arrays-ii/

# Videos
- [Bubble Sort](https://youtu.be/F5MZyqRp_IM)
- [Selection Sort](https://youtu.be/Nd4SCCIHFWk)
- [Insertion Sort](https://youtu.be/By_5-RRqVeE)
- [Cycle Sort](https://www.youtube.com/watch?v=JfinxytTYFQ&list=RDCMUCBGOUQHNNtNGcGzVq5rIXjw&start_radio=1&rv=JfinxytTYFQ&t=2)
- [Merge Sort](https://youtu.be/iKGAgWdgoRk)
- [Quick Sort](https://youtu.be/Z8svOqamag8)

1.Merge two sorted array
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
      int left = 0; 
      int right = 0; 
      int index  = 0;
      int[] ans = new int[m+n];
      while(left<m&&right<n){
          if(nums1[left]<=nums2[right]){
         ans[index] = nums1[left];
        index++;
        left++;
          }
          else{
              ans[index] = nums2[right];
              index++;
              right++;
          }
      }
      while(left<m){
          ans[index++] = nums1[left++];
      }
      while(right<n){
          ans[index++]= nums2[right++];
      }
      for(int i=0; i<ans.length; i++){
          nums1[i] = ans[i];
      }
    }
}

2.Majiority elements
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;
        return nums[n/2];
    }
}

3.Missing number
class Solution {
    public int missingNumber(int[] nums) {
       return sort(nums);
    }
   
    public int sort(int[] nums){
        int i=0; 
        while (i<nums.length) {
            int correct = nums[i];
            if(nums[i]<nums.length && nums[i]!=nums[correct])
            {
                swap(nums,i,correct);
            }
            else{
                i++;
            }
        }
        //Search for the element
        for(i=0; i<nums.length; i++){
            if(nums[i]!=i) return i;
        }
        return nums.length;
    }
    public void swap(int[] nums,int first,int secound){
        int temp =nums[first];
        nums[first] = nums[secound];
        nums[secound] = temp;
    }
}

4 349. Intersection of Two Arrays
class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
            HashSet<Integer> set1 = new HashSet<>();
            HashSet<Integer> set2 = new HashSet<>();
            for(int i=0; i<nums1.length; i++){
                set1.add(nums1[i]);
            }
              for(int i=0; i<nums2.length; i++){
                set2.add(nums2[i]);
            }
            ArrayList<Integer> ans = new ArrayList<>();
            for(int i:set1){
                if(set2.contains(i)){
                    ans.add(i);
                }
            }
            int size = ans.size();
            int [] arr = new int[size];
            for(int i=0; i<size; i++){
                arr[i]=ans.get(i);
            }
            return arr;
    }
}

5.
