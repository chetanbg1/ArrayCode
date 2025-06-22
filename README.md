# ArrayCode

1. Find the Maximum Element in an Array
java
Copy
Edit
public class MaxElement {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int max = arr[0];
        for(int num : arr) {
            if(num > max) max = num;
        }
        System.out.println("Maximum element is: " + max);
    }
}
2. Find the Minimum Element in an Array
java
Copy
Edit
public class MinElement {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int min = arr[0];
        for(int num : arr) {
            if(num < min) min = num;
        }
        System.out.println("Minimum element is: " + min);
    }
}
3. Calculate the Sum of All Elements in an Array
java
Copy
Edit
public class SumArray {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int sum = 0;
        for(int num : arr) sum += num;
        System.out.println("Sum of elements: " + sum);
    }
}
4. Calculate the Average of Array Elements
java
Copy
Edit
public class AverageArray {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int sum = 0;
        for(int num : arr) sum += num;
        double avg = (double) sum / arr.length;
        System.out.println("Average is: " + avg);
    }
}
5. Reverse an Array
java
Copy
Edit
import java.util.Arrays;

public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int n = arr.length;
        for(int i=0; i<n/2; i++) {
            int temp = arr[i];
            arr[i] = arr[n-1-i];
            arr[n-1-i] = temp;
        }
        System.out.println("Reversed array: " + Arrays.toString(arr));
    }
}
6. Check if an Array Contains a Given Element
java
Copy
Edit
public class ContainsElement {
    public static boolean contains(int[] arr, int x) {
        for(int num : arr) {
            if(num == x) return true;
        }
        return false;
    }
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int x = 9;
        System.out.println(contains(arr, x) ? "Element found" : "Element not found");
    }
}
7. Find the Index of a Given Element in an Array
java
Copy
Edit
public class IndexOfElement {
    public static int indexOf(int[] arr, int x) {
        for(int i=0; i<arr.length; i++) {
            if(arr[i] == x) return i;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int x = 2;
        System.out.println("Index of element: " + indexOf(arr, x));
    }
}
8. Find the Second Largest Element in an Array
java
Copy
Edit
public class SecondLargest {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        for(int num : arr) {
            if(num > largest) {
                secondLargest = largest;
                largest = num;
            } else if(num > secondLargest && num != largest) {
                secondLargest = num;
            }
        }
        System.out.println("Second largest element is: " + secondLargest);
    }
}
9. Sort an Array Using Bubble Sort
java
Copy
Edit
import java.util.Arrays;

public class BubbleSort {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int n = arr.length;
        for(int i=0; i<n-1; i++) {
            for(int j=0; j<n-1-i; j++) {
                if(arr[j] > arr[j+1]) {
                    int temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                }
            }
        }
        System.out.println("Sorted array: " + Arrays.toString(arr));
    }
}
10. Remove Duplicates from an Array
java
Copy
Edit
import java.util.Arrays;
import java.util.LinkedHashSet;
import java.util.Set;

public class RemoveDuplicates {
    public static void main(String[] args) {
        Integer[] arr = {5, 8, 2, 9, 1, 5, 2};
        Set<Integer> set = new LinkedHashSet<>(Arrays.asList(arr));
        Integer[] unique = set.toArray(new Integer[0]);
        System.out.println("Array without duplicates: " + Arrays.toString(unique));
    }
}
11. Find the Frequency of Each Element in an Array
java
Copy
Edit
import java.util.HashMap;
import java.util.Map;

public class FrequencyCount {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 5, 1, 8, 5};
        Map<Integer, Integer> freq = new HashMap<>();
        for(int num : arr) {
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }
        for(Map.Entry<Integer, Integer> e : freq.entrySet()) {
            System.out.println(e.getKey() + " occurs " + e.getValue() + " times");
        }
    }
}
12. Merge Two Sorted Arrays
java
Copy
Edit
import java.util.Arrays;

public class MergeSortedArrays {
    public static int[] merge(int[] arr1, int[] arr2) {
        int i=0, j=0, k=0;
        int[] merged = new int[arr1.length + arr2.length];
        while(i < arr1.length && j < arr2.length) {
            if(arr1[i] < arr2[j]) merged[k++] = arr1[i++];
            else merged[k++] = arr2[j++];
        }
        while(i < arr1.length) merged[k++] = arr1[i++];
        while(j < arr2.length) merged[k++] = arr2[j++];
        return merged;
    }
    public static void main(String[] args) {
        int[] arr1 = {1,3,5};
        int[] arr2 = {2,4,6};
        int[] merged = merge(arr1, arr2);
        System.out.println("Merged array: " + Arrays.toString(merged));
    }
}
13. Find the Missing Number in an Array of 1 to N
java
Copy
Edit
public class MissingNumber {
    public static int findMissing(int[] arr, int n) {
        int sum = n*(n+1)/2;
        int arrSum = 0;
        for(int num : arr) arrSum += num;
        return sum - arrSum;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 5, 6};
        int n = 6;
        System.out.println("Missing number: " + findMissing(arr, n));
    }
}
14. Find the Pair of Elements That Sum to a Given Number
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class PairSum {
    public static void findPairs(int[] arr, int target) {
        Set<Integer> set = new HashSet<>();
        for(int num : arr) {
            int diff = target - num;
            if(set.contains(diff)) {
                System.out.println("Pair found: (" + diff + ", " + num + ")");
            }
            set.add(num);
        }
    }
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int target = 10;
        findPairs(arr, target);
    }
}
15. Check if an Array is Sorted
java
Copy
Edit
public class CheckSorted {
    public static boolean isSorted(int[] arr) {
        for(int i=0; i<arr.length-1; i++) {
            if(arr[i] > arr[i+1]) return false;
        }
        return true;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4};
        System.out.println(isSorted(arr) ? "Sorted" : "Not sorted");
    }
}
16. Rotate an Array by K Positions to the Right
java
Copy
Edit
import java.util.Arrays;

public class RotateArray {
    public static void rotate(int[] arr, int k) {
        int n = arr.length;
        k = k % n;
        reverse(arr, 0, n-1);
        reverse(arr, 0, k-1);
        reverse(arr, k, n-1);
    }
    public static void reverse(int[] arr, int start, int end) {
        while(start < end) {
            int temp = arr[start];
            arr[start++] = arr[end];
            arr[end--] = temp;
        }
    }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};
        int k = 2;
        rotate(arr, k);
        System.out.println("Rotated array: " + Arrays.toString(arr));
    }
}
17. Find the Subarray with Maximum Sum (Kadane’s Algorithm)
java
Copy
Edit
public class MaxSubarraySum {
    public static int maxSubArray(int[] arr) {
        int maxSoFar = arr[0], maxEndingHere = arr[0];
        for(int i=1; i<arr.length; i++) {
            maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        return maxSoFar;
    }
    public static void main(String[] args) {
        int[] arr = {-2,1,-3,4,-1,2,1,-5,4};
        System.out.println("Maximum subarray sum: " + maxSubArray(arr));
    }
}
18. Find Common Elements in Two Arrays
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class CommonElements {
    public static void main(String[] args) {
        int[] arr1 = {1,2,3,4};
        int[] arr2 = {3,4,5,6};
        Set<Integer> set = new HashSet<>();
        for(int num : arr1) set.add(num);
        System.out.println("Common elements:");
        for(int num : arr2) {
            if(set.contains(num)) System.out.println(num);
        }
    }
}
19. Find the Intersection of Two Arrays (Unique Elements)
java
Copy
Edit
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class Intersection {
    public static void main(String[] args) {
        int[] arr1 = {1,2,2,3,4};
        int[] arr2 = {2,2,3,5};
        Set<Integer> set1 = new HashSet<>();
        for(int num : arr1) set1.add(num);
        Set<Integer> intersection = new HashSet<>();
        for(int num : arr2) {
            if(set1.contains(num)) intersection.add(num);
        }
        System.out.println("Intersection: " + Arrays.toString(intersection.toArray()));
    }
}
20. Find the Union of Two Arrays (Unique Elements)
java
Copy
Edit
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class Union {
    public static void main(String[] args) {
        int[] arr1 = {1,2,3};
        int[] arr2 = {2,3,4};
        Set<Integer> union = new HashSet<>();
        for(int num : arr1) union.add(num);
        for(int num : arr2) union.add(num);
        System.out.println("Union: " + Arrays.toString(union.toArray()));
    }
}
21. Find the Largest and Smallest Number in an Array
java
Copy
Edit
public class LargestSmallest {
    public static void main(String[] args) {
        int[] arr = {5, 8, 2, 9, 1};
        int largest = arr[0], smallest = arr[0];
        for(int num : arr) {
            if(num > largest) largest = num;
            if(num < smallest) smallest = num;
        }
        System.out.println("Largest: " + largest);
        System.out.println("Smallest: " + smallest);
    }
}
22. Find All Pairs with Given Sum in an Array
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class AllPairsSum {
    public static void findPairs(int[] arr, int sum) {
        Set<Integer> set = new HashSet<>();
        for(int num : arr) {
            int target = sum - num;
            if(set.contains(target)) {
                System.out.println("Pair: (" + num + ", " + target + ")");
            }
            set.add(num);
        }
    }
    public static void main(String[] args) {
        int[] arr = {1,5,7,-1,5};
        int sum = 6;
        findPairs(arr, sum);
    }
}
23. Find Duplicate Elements in an Array
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class FindDuplicates {
    public static void main(String[] args) {
        int[] arr = {1,2,3,2,4,5,1};
        Set<Integer> set = new HashSet<>();
        Set<Integer> duplicates = new HashSet<>();
        for(int num : arr) {
            if(!set.add(num)) duplicates.add(num);
        }
        System.out.println("Duplicates: " + duplicates);
    }
}
24. Find the Length of the Longest Consecutive Subsequence
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class LongestConsecutive {
    public static int longestConsecutive(int[] nums) {
        Set<Integer> set = new HashSet<>();
        for(int num : nums) set.add(num);
        int longest = 0;
        for(int num : nums) {
            if(!set.contains(num - 1)) {
                int currentNum = num;
                int length = 1;
                while(set.contains(currentNum + 1)) {
                    currentNum++;
                    length++;
                }
                longest = Math.max(longest, length);
            }
        }
        return longest;
    }
    public static void main(String[] args) {
        int[] arr = {100, 4, 200, 1, 3, 2};
        System.out.println("Longest consecutive sequence length: " + longestConsecutive(arr));
    }
}
25. Find the Majority Element in an Array (Boyer-Moore Voting Algorithm)
java
Copy
Edit
public class MajorityElement {
    public static int majorityElement(int[] nums) {
        int count = 0, candidate = 0;
        for(int num : nums) {
            if(count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        return candidate;
    }
    public static void main(String[] args) {
        int[] arr = {2,2,1,1,1,2,2};
        System.out.println("Majority element: " + majorityElement(arr));
    }
}
26. Move All Zeros to the End of Array
java
Copy
Edit
import java.util.Arrays;

public class MoveZeros {
    public static void moveZerosToEnd(int[] arr) {
        int count = 0; 
        for(int i=0; i<arr.length; i++) {
            if(arr[i] != 0) {
                arr[count++] = arr[i];
            }
        }
        while(count < arr.length) {
            arr[count++] = 0;
        }
    }
    public static void main(String[] args) {
        int[] arr = {0,1,0,3,12};
        moveZerosToEnd(arr);
        System.out.println(Arrays.toString(arr));
    }
}
27. Find the Missing Number in a Sorted Array of 1 to N
java
Copy
Edit
public class MissingInSortedArray {
    public static int findMissing(int[] arr) {
        int low = 0, high = arr.length - 1;
        while(low <= high) {
            int mid = low + (high - low) / 2;
            if(arr[mid] != mid + 1) high = mid - 1;
            else low = mid + 1;
        }
        return low + 1;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 5, 6};
        System.out.println("Missing number: " + findMissing(arr));
    }
}
28. Find the Length of the Largest Subarray with Sum Zero
java
Copy
Edit
import java.util.HashMap;

public class LargestSubarraySumZero {
    public static int maxLen(int[] arr) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int sum = 0, maxLen = 0;
        for(int i=0; i<arr.length; i++) {
            sum += arr[i];
            if(arr[i] == 0 && maxLen == 0) maxLen = 1;
            if(sum == 0) maxLen = i + 1;
            if(map.containsKey(sum)) {
                maxLen = Math.max(maxLen, i - map.get(sum));
            } else {
                map.put(sum, i);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {15, -2, 2, -8, 1, 7, 10, 23};
        System.out.println("Length of largest subarray with sum 0: " + maxLen(arr));
    }
}
29. Find the Equilibrium Index of an Array
java
Copy
Edit
public class EquilibriumIndex {
    public static int equilibriumIndex(int[] arr) {
        int total = 0;
        for(int num : arr) total += num;
        int leftSum = 0;
        for(int i=0; i<arr.length; i++) {
            total -= arr[i];
            if(leftSum == total) return i;
            leftSum += arr[i];
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {-7, 1, 5, 2, -4, 3, 0};
        System.out.println("Equilibrium index: " + equilibriumIndex(arr));
    }
}
30. Find All Leaders in an Array (Elements Greater Than All Elements to Their Right)

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class LeadersInArray {
    public static List<Integer> findLeaders(int[] arr) {
        List<Integer> leaders = new ArrayList<>();
        int maxFromRight = arr[arr.length - 1];
        leaders.add(maxFromRight);
        for(int i=arr.length - 2; i>=0; i--) {
            if(arr[i] > maxFromRight) {
                maxFromRight = arr[i];
                leaders.add(maxFromRight);
            }
        }
        Collections.reverse(leaders);
        return leaders;
    }
    public static void main(String[] args) {
        int[] arr = {16, 17, 4, 3, 5, 2};
        System.out.println("Leaders: " + findLeaders(arr));
    }
}
31. Find the Two Elements Whose Sum is Closest to Zero

import java.util.Arrays;

public class ClosestToZero {
    public static void findClosestSum(int[] arr) {
        Arrays.sort(arr);
        int left = 0, right = arr.length - 1;
        int minSum = Integer.MAX_VALUE;
        int pairLeft = left, pairRight = right;

        while(left < right) {
            int sum = arr[left] + arr[right];
            if(Math.abs(sum) < Math.abs(minSum)) {
                minSum = sum;
                pairLeft = left;
                pairRight = right;
            }
            if(sum < 0) left++;
            else right--;
        }
        System.out.println("Pair with sum closest to zero: (" + arr[pairLeft] + ", " + arr[pairRight] + ")");
    }
    public static void main(String[] args) {
        int[] arr = {1, 60, -10, 70, -80, 85};
        findClosestSum(arr);
    }
}
32. Count Inversions in an Array

public class CountInversions {
    public static int mergeSort(int[] arr, int l, int r) {
        int count = 0;
        if(l < r) {
            int m = (l + r)/2;
            count += mergeSort(arr, l, m);
            count += mergeSort(arr, m+1, r);
            count += merge(arr, l, m, r);
        }
        return count;
    }

    public static int merge(int[] arr, int l, int m, int r) {
        int[] left = java.util.Arrays.copyOfRange(arr, l, m+1);
        int[] right = java.util.Arrays.copyOfRange(arr, m+1, r+1);

        int i=0, j=0, k=l, swaps=0;

        while(i < left.length && j < right.length) {
            if(left[i] <= right[j]) arr[k++] = left[i++];
            else {
                arr[k++] = right[j++];
                swaps += (m + 1) - (l + i);
            }
        }
        while(i < left.length) arr[k++] = left[i++];
        while(j < right.length) arr[k++] = right[j++];
        return swaps;
    }

    public static void main(String[] args) {
        int[] arr = {2, 4, 1, 3, 5};
        System.out.println("Number of inversions: " + mergeSort(arr, 0, arr.length - 1));
    }
}
33. Find the Product of Array Except Self (Without Using Division)

import java.util.Arrays;

public class ProductExceptSelf {
    public static int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] result = new int[n];
        int leftProduct = 1;
        for(int i=0; i<n; i++) {
            result[i] = leftProduct;
            leftProduct *= nums[i];
        }
        int rightProduct = 1;
        for(int i=n-1; i>=0; i--) {
            result[i] *= rightProduct;
            rightProduct *= nums[i];
        }
        return result;
    }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4};
        System.out.println("Product array: " + Arrays.toString(productExceptSelf(arr)));
    }
}
35. Find the Maximum Product Subarray (continued)
java
Copy
Edit
public class MaxProductSubarray {
    public static int maxProduct(int[] nums) {
        int maxProd = nums[0], minProd = nums[0], result = nums[0];
        for(int i = 1; i < nums.length; i++) {
            if(nums[i] < 0) {
                int temp = maxProd;
                maxProd = minProd;
                minProd = temp;
            }
            maxProd = Math.max(nums[i], maxProd * nums[i]);
            minProd = Math.min(nums[i], minProd * nums[i]);
            result = Math.max(result, maxProd);
        }
        return result;
    }
    public static void main(String[] args) {
        int[] arr = {2, 3, -2, 4};
        System.out.println("Maximum product subarray: " + maxProduct(arr));
    }
}
36. Find the Kth Largest Element in an Array
java
Copy
Edit
import java.util.PriorityQueue;

public class KthLargest {
    public static int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        for(int num : nums) {
            minHeap.add(num);
            if(minHeap.size() > k) minHeap.poll();
        }
        return minHeap.peek();
    }
    public static void main(String[] args) {
        int[] arr = {3,2,1,5,6,4};
        int k = 2;
        System.out.println("Kth largest element: " + findKthLargest(arr, k));
    }
}
37. Find the Kth Smallest Element in an Array
java
Copy
Edit
import java.util.PriorityQueue;

public class KthSmallest {
    public static int findKthSmallest(int[] nums, int k) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>((a,b) -> b - a);
        for(int num : nums) {
            maxHeap.add(num);
            if(maxHeap.size() > k) maxHeap.poll();
        }
        return maxHeap.peek();
    }
    public static void main(String[] args) {
        int[] arr = {7,10,4,3,20,15};
        int k = 3;
        System.out.println("Kth smallest element: " + findKthSmallest(arr, k));
    }
}
38. Find the Intersection of Three Sorted Arrays
java
Copy
Edit
import java.util.ArrayList;
import java.util.List;

public class IntersectionThreeArrays {
    public static List<Integer> intersection(int[] arr1, int[] arr2, int[] arr3) {
        List<Integer> result = new ArrayList<>();
        int i=0, j=0, k=0;
        while(i < arr1.length && j < arr2.length && k < arr3.length) {
            if(arr1[i] == arr2[j] && arr2[j] == arr3[k]) {
                result.add(arr1[i]);
                i++; j++; k++;
            } else if(arr1[i] < arr2[j]) i++;
            else if(arr2[j] < arr3[k]) j++;
            else k++;
        }
        return result;
    }
    public static void main(String[] args) {
        int[] arr1 = {1, 5, 10, 20, 40, 80};
        int[] arr2 = {6, 7, 20, 80, 100};
        int[] arr3 = {3, 4, 15, 20, 30, 70, 80, 120};
        System.out.println("Intersection: " + intersection(arr1, arr2, arr3));
    }
}
39. Rearrange Positive and Negative Numbers Alternately
java
Copy
Edit
import java.util.Arrays;

public class RearrangePositiveNegative {
    public static void rearrange(int[] arr) {
        int n = arr.length;
        int i = -1;
        for(int j = 0; j < n; j++) {
            if(arr[j] < 0) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int pos = i + 1, neg = 0;
        while(pos < n && neg < pos && arr[neg] < 0) {
            int temp = arr[neg];
            arr[neg] = arr[pos];
            arr[pos] = temp;
            pos++;
            neg += 2;
        }
    }
    public static void main(String[] args) {
        int[] arr = {2, 3, -4, -1, 6, -9};
        rearrange(arr);
        System.out.println(Arrays.toString(arr));
    }
}
40. Find the Maximum Length Even-Odd Subarray
java
Copy
Edit
public class MaxEvenOddSubarray {
    public static int maxEvenOdd(int[] arr) {
        int maxLen = 1, currLen = 1;
        for(int i=1; i<arr.length; i++) {
            if((arr[i]%2 == 0 && arr[i-1]%2 != 0) || (arr[i]%2 != 0 && arr[i-1]%2 == 0)) {
                currLen++;
                maxLen = Math.max(maxLen, currLen);
            } else currLen = 1;
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {5, 10, 20, 6, 3, 8};
        System.out.println("Max even-odd subarray length: " + maxEvenOdd(arr));
    }
}
41. Find the First Missing Positive Integer
java
Copy
Edit
public class FirstMissingPositive {
    public static int firstMissingPositive(int[] nums) {
        int n = nums.length;
        for(int i=0; i<n; i++) {
            while(nums[i] > 0 && nums[i] <= n && nums[nums[i]-1] != nums[i]) {
                int temp = nums[nums[i]-1];
                nums[nums[i]-1] = nums[i];
                nums[i] = temp;
            }
        }
        for(int i=0; i<n; i++) {
            if(nums[i] != i+1) return i+1;
        }
        return n+1;
    }
    public static void main(String[] args) {
        int[] arr = {3,4,-1,1};
        System.out.println("First missing positive: " + firstMissingPositive(arr));
    }
}
42. Find the Maximum Sum of K Consecutive Elements
java
Copy
Edit
public class MaxSumKElements {
    public static int maxSumK(int[] arr, int k) {
        int maxSum = 0, windowSum = 0;
        for(int i=0; i<k; i++) windowSum += arr[i];
        maxSum = windowSum;
        for(int i=k; i<arr.length; i++) {
            windowSum += arr[i] - arr[i-k];
            maxSum = Math.max(maxSum, windowSum);
        }
        return maxSum;
    }
    public static void main(String[] args) {
        int[] arr = {2, 1, 5, 1, 3, 2};
        int k = 3;
        System.out.println("Max sum of " + k + " elements: " + maxSumK(arr, k));
    }
}
43. Find the Longest Substring Without Repeating Characters (Array version)
java
Copy
Edit
import java.util.HashSet;
import java.util.Set;

public class LongestUniqueSubarray {
    public static int lengthOfLongestUniqueSubarray(int[] arr) {
        Set<Integer> set = new HashSet<>();
        int i = 0, j = 0, maxLen = 0;
        while(j < arr.length) {
            if(!set.contains(arr[j])) {
                set.add(arr[j++]);
                maxLen = Math.max(maxLen, j - i);
            } else {
                set.remove(arr[i++]);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 4, 5};
        System.out.println("Longest subarray with unique elements: " + lengthOfLongestUniqueSubarray(arr));
    }
}
44. Find All Pairs with Difference K
java
Copy
Edit
import java.util.HashSet;

public class PairsWithDifferenceK {
    public static void findPairs(int[] arr, int k) {
        HashSet<Integer> set = new HashSet<>();
        for(int num : arr) set.add(num);
        for(int num : arr) {
            if(set.contains(num + k)) {
                System.out.println("(" + num + ", " + (num + k) + ")");
            }
        }
    }
    public static void main(String[] args) {
        int[] arr = {1, 7, 5, 9, 2, 12, 3};
        int k = 2;
        findPairs(arr, k);
    }
}
45. Check if Array is a Palindrome
java
Copy
Edit
public class CheckPalindrome {
    public static boolean isPalindrome(int[] arr) {
        int left = 0, right = arr.length - 1;
        while(left < right) {
            if(arr[left++] != arr[right--]) return false;
        }
        return true;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 2, 1};
        System.out.println("Is palindrome: " + isPalindrome(arr));
    }
}
46. Find the Second Largest Element in an Array
java
Copy
Edit
public class SecondLargest {
    public static int secondLargest(int[] arr) {
        int first = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
        for(int num : arr) {
            if(num > first) {
                second = first;
                first = num;
            } else if(num > second && num != first) {
                second = num;
            }
        }
        return second;
    }
    public static void main(String[] args) {
        int[] arr = {12, 35, 1, 10, 34, 1};
        System.out.println("Second largest element: " + secondLargest(arr));
    }
}
47. Rotate Array by K Positions to the Right
java
Copy
Edit
import java.util.Arrays;

public class RotateArray {
    public static void rotate(int[] arr, int k) {
        k %= arr.length;
        reverse(arr, 0, arr.length - 1);
        reverse(arr, 0, k - 1);
        reverse(arr, k, arr.length - 1);
    }
    private static void reverse(int[] arr, int start, int end) {
        while(start < end) {
            int temp = arr[start];
            arr[start++] = arr[end];
            arr[end--] = temp;
        }
    }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,6,7};
        int k = 3;
        rotate(arr, k);
        System.out.println(Arrays.toString(arr));
    }
}
48. Count Number of Subarrays with Given Sum
java
Copy
Edit
import java.util.HashMap;

public class SubarraySumCount {
    public static int countSubarraysWithSum(int[] arr, int k) {
        int count = 0, sum = 0;
        HashMap<Integer, Integer> map = new HashMap<>();
        map.put(0, 1);
        for(int num : arr) {
            sum += num;
            if(map.containsKey(sum - k)) count += map.get(sum - k);
            map.put(sum, map.getOrDefault(sum, 0) + 1);
        }
        return count;
    }
    public static void main(String[] args) {
        int[] arr = {1, 1, 1};
        int k = 2;
        System.out.println("Count of subarrays with sum " + k + ": " + countSubarraysWithSum(arr, k));
    }
}
49. Sort an Array of 0s, 1s and 2s (Dutch National Flag)
java
Copy
Edit
import java.util.Arrays;

public class Sort012 {
    public static void sort012(int[] arr) {
        int low = 0, mid = 0, high = arr.length - 1;
        while(mid <= high) {
            if(arr[mid] == 0) {
                int temp = arr[low];
                arr[low++] = arr[mid];
                arr[mid++] = temp;
            } else if(arr[mid] == 1) mid++;
            else {
                int temp = arr[mid];
                arr[mid] = arr[high];
                arr[high--] = temp;
            }
        }
    }
    public static void main(String[] args) {
        int[] arr = {0,1,2,0,1,2};
        sort012(arr);
        System.out.println(Arrays.toString(arr));
    }
}
50. Merge Two Sorted Arrays Without Extra Space
java
Copy
Edit
import java.util.Arrays;

public class MergeSortedArrays {
    public static void merge(int[] arr1, int[] arr2) {
        int n = arr1.length, m = arr2.length;
        for(int i = 0; i < n; i++) {
            if(arr1[i] > arr2[0]) {
                int temp = arr1[i];
                arr1[i] = arr2[0];
                arr2[0] = temp;

                int first = arr2[0], k;
                for(k=1; k<m && arr2[k]<first; k++) {
                    arr2[k-1] = arr2[k];
                }
                arr2[k-1] = first;
            }
        }
    }
    public static void main(String[] args) {
        int[] arr1 = {1, 5, 9, 10, 15, 20};
        int[] arr2 = {2, 3, 8, 13};
        merge(arr1, arr2);
        System.out.println("Array 1: " + Arrays.toString(arr1));
        System.out.println("Array 2: " + Arrays.toString(arr2));
    }
}
51. Find Majority Element (Element occurring more than n/2 times)
java
Copy
Edit
public class MajorityElement {
    public static int findMajority(int[] arr) {
        int count = 0, candidate = -1;
        for(int num : arr) {
            if(count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        // Verify candidate
        count = 0;
        for(int num : arr) if(num == candidate) count++;
        return (count > arr.length/2) ? candidate : -1;
    }
    public static void main(String[] args) {
        int[] arr = {2, 2, 1, 1, 2, 2, 2};
        System.out.println("Majority element: " + findMajority(arr));
    }
}
52. Move All Zeros to the End
java
Copy
Edit
import java.util.Arrays;

public class MoveZeros {
    public static void moveZerosToEnd(int[] arr) {
        int count = 0; 
        for(int num : arr) {
            if(num != 0) arr[count++] = num;
        }
        while(count < arr.length) arr[count++] = 0;
    }
    public static void main(String[] args) {
        int[] arr = {0,1,0,3,12};
        moveZerosToEnd(arr);
        System.out.println(Arrays.toString(arr));
    }
}
53. Find Two Numbers That Add Up to a Target
java
Copy
Edit
import java.util.HashMap;
import java.util.Arrays;

public class TwoSum {
    public static int[] twoSum(int[] arr, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int i=0; i<arr.length; i++) {
            int complement = target - arr[i];
            if(map.containsKey(complement)) {
                return new int[] {map.get(complement), i};
            }
            map.put(arr[i], i);
        }
        return new int[] {-1, -1};
    }
    public static void main(String[] args) {
        int[] arr = {2,7,11,15};
        int target = 9;
        System.out.println(Arrays.toString(twoSum(arr, target)));
    }
}
54. Find Maximum Sum of a Circular Subarray
java
Copy
Edit
public class MaxCircularSubarraySum {
    public static int maxSubarraySumCircular(int[] arr) {
        int max_kadane = kadane(arr);
        int max_wrap = 0;
        for(int i=0; i<arr.length; i++) {
            max_wrap += arr[i];
            arr[i] = -arr[i];
        }
        max_wrap = max_wrap + kadane(arr);
        return (max_wrap > max_kadane) ? max_wrap : max_kadane;
    }
    private static int kadane(int[] arr) {
        int max_ending_here = arr[0], max_so_far = arr[0];
        for(int i=1; i<arr.length; i++) {
            max_ending_here = Math.max(arr[i], max_ending_here + arr[i]);
            max_so_far = Math.max(max_so_far, max_ending_here);
        }
        return max_so_far;
    }
    public static void main(String[] args) {
        int[] arr = {5, -2, 3, 4};
        System.out.println("Max circular subarray sum: " + maxSubarraySumCircular(arr));
    }
}
55. Find the Length of Longest Increasing Subsequence
java
Copy
Edit
public class LongestIncreasingSubsequence {
    public static int lengthOfLIS(int[] nums) {
        int[] dp = new int[nums.length];
        int maxLen = 1;
        for(int i=0; i<nums.length; i++) {
            dp[i] = 1;
            for(int j=0; j<i; j++) {
                if(nums[i] > nums[j]) {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
            maxLen = Math.max(maxLen, dp[i]);
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {10,9,2,5,3,7,101,18};
        System.out.println("Length of LIS: " + lengthOfLIS(arr));
    }
}
56. Find Minimum Number of Jumps to Reach End
java
Copy
Edit
public class MinJumps {
    public static int minJumps(int[] arr) {
        int jumps = 0, currentEnd = 0, farthest = 0;
        for(int i=0; i<arr.length - 1; i++) {
            farthest = Math.max(farthest, i + arr[i]);
            if(i == currentEnd) {
                jumps++;
                currentEnd = farthest;
            }
            if(currentEnd >= arr.length - 1) break;
        }
        return currentEnd >= arr.length - 1 ? jumps : -1;
    }
    public static void main(String[] args) {
        int[] arr = {2,3,1,1,4};
        System.out.println("Minimum jumps: " + minJumps(arr));
    }
}
57. Count Inversions in an Array
java
Copy
Edit
public class CountInversions {
    public static int mergeSort(int[] arr, int l, int r) {
        int count = 0;
        if(l < r) {
            int mid = (l + r) / 2;
            count += mergeSort(arr, l, mid);
            count += mergeSort(arr, mid + 1, r);
            count += merge(arr, l, mid, r);
        }
        return count;
    }
    private static int merge(int[] arr, int l, int m, int r) {
        int[] left = new int[m - l + 1];
        int[] right = new int[r - m];
        System.arraycopy(arr, l, left, 0, left.length);
        System.arraycopy(arr, m + 1, right, 0, right.length);

        int i=0, j=0, k=l, swaps=0;
        while(i < left.length && j < right.length) {
            if(left[i] <= right[j]) arr[k++] = left[i++];
            else {
                arr[k++] = right[j++];
                swaps += (left.length - i);
            }
        }
        while(i < left.length) arr[k++] = left[i++];
        while(j < right.length) arr[k++] = right[j++];
        return swaps;
    }
    public static void main(String[] args) {
        int[] arr = {2, 4, 1, 3, 5};
        System.out.println("Inversion count: " + mergeSort(arr, 0, arr.length - 1));
    }
}
58. Find Longest Consecutive Sequence
java
Copy
Edit
import java.util.HashSet;

public class LongestConsecutiveSequence {
    public static int longestConsecutive(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for(int num : nums) set.add(num);
        int longest = 0;
        for(int num : nums) {
            if(!set.contains(num - 1)) {
                int currentNum = num;
                int currentStreak = 1;
                while(set.contains(currentNum + 1)) {
                    currentNum++;
                    currentStreak++;
                }
                longest = Math.max(longest, currentStreak);
            }
        }
        return longest;
    }
    public static void main(String[] args) {
        int[] arr = {100, 4, 200, 1, 3, 2};
        System.out.println("Longest consecutive sequence: " + longestConsecutive(arr));
    }
}
59. Find Subarray with Given Sum
java
Copy
Edit
import java.util.HashMap;

public class SubarrayWithGivenSum {
    public static int[] subarraySum(int[] arr, int target) {
        int sum = 0;
        HashMap<Integer, Integer> map = new HashMap<>();
        map.put(0, -1);
        for(int i=0; i<arr.length; i++) {
            sum += arr[i];
            if(map.containsKey(sum - target)) {
                return new int[]{map.get(sum - target) + 1, i};
            }
            map.put(sum, i);
        }
        return new int[] {-1, -1};
    }
    public static void main(String[] args) {
        int[] arr = {10, 2, -2, -20, 10};
        int target = -10;
        int[] res = subarraySum(arr, target);
        System.out.println("Subarray with given sum: " + res[0] + " to " + res[1]);
    }
}
60. Find the Pair with Maximum Product in an Array
java
Copy
Edit
import java.util.Arrays;

public class MaxProductPair {
    public static int[] maxProductPair(int[] arr) {
        Arrays.sort(arr);
        int n = arr.length;
        int product1 = arr[0] * arr[1]; // Possibly negative * negative
        int product2 = arr[n-1] * arr[n-2]; // Largest two positives
        if(product1 > product2) return new int[]{arr[0], arr[1]};
        else return new int[]{arr[n-2], arr[n-1]};
    }
    public static void main(String[] args) {
        int[] arr = {-10, -3, 5, 6, -2};
        int[] res = maxProductPair(arr);
        System.out.println("Pair with max product: " + res[0] + ", " + res[1]);
    }
}
61. Find All Missing Numbers in an Array (1 to n)
java
Copy
Edit
import java.util.ArrayList;
import java.util.List;

public class FindMissingNumbers {
    public static List<Integer> findMissing(int[] arr) {
        int i = 0;
        while(i < arr.length) {
            int correct = arr[i] - 1;
            if(arr[i] > 0 && arr[i] <= arr.length && arr[i] != arr[correct]) {
                int temp = arr[i];
                arr[i] = arr[correct];
                arr[correct] = temp;
            } else {
                i++;
            }
        }
        List<Integer> missing = new ArrayList<>();
        for(i = 0; i < arr.length; i++) {
            if(arr[i] != i+1) missing.add(i+1);
        }
        return missing;
    }
    public static void main(String[] args) {
        int[] arr = {4,3,2,7,8,2,3,1};
        System.out.println("Missing numbers: " + findMissing(arr));
    }
}
62. Find Longest Subarray with Sum Divisible by K
java
Copy
Edit
import java.util.HashMap;

public class LongestSubarrayDivisibleByK {
    public static int longestSubarrayDivByK(int[] arr, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();
        map.put(0, -1);
        int maxLen = 0, sum = 0;
        for(int i=0; i<arr.length; i++) {
            sum += arr[i];
            int mod = ((sum % k) + k) % k;
            if(map.containsKey(mod)) {
                maxLen = Math.max(maxLen, i - map.get(mod));
            } else {
                map.put(mod, i);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {2, 7, 6, 1, 4, 5};
        int k = 3;
        System.out.println("Longest subarray divisible by " + k + ": " + longestSubarrayDivByK(arr, k));
    }
}
63. Find Maximum Sum of Non-Adjacent Elements
java
Copy
Edit
public class MaxSumNonAdjacent {
    public static int maxSum(int[] arr) {
        int incl = arr[0], excl = 0;
        for(int i=1; i<arr.length; i++) {
            int new_excl = Math.max(incl, excl);
            incl = excl + arr[i];
            excl = new_excl;
        }
        return Math.max(incl, excl);
    }
    public static void main(String[] args) {
        int[] arr = {3, 2, 7, 10};
        System.out.println("Max sum of non-adjacent elements: " + maxSum(arr));
    }
}
64. Find Element that Appears Once in Array Where Every Other Element Appears Twice
java
Copy
Edit
public class SingleElement {
    public static int findSingle(int[] arr) {
        int result = 0;
        for(int num : arr) result ^= num;
        return result;
    }
    public static void main(String[] args) {
        int[] arr = {2, 3, 5, 4, 5, 3, 4};
        System.out.println("Element appearing once: " + findSingle(arr));
    }
}
65. Find the Largest Three Elements in an Array
java
Copy
Edit
import java.util.Arrays;

public class LargestThreeElements {
    public static void findLargestThree(int[] arr) {
        Arrays.sort(arr);
        System.out.println("Three largest elements: " + arr[arr.length - 1] + ", " + arr[arr.length - 2] + ", " + arr[arr.length - 3]);
    }
    public static void main(String[] args) {
        int[] arr = {10, 4, 3, 50, 23, 90};
        findLargestThree(arr);
    }
}
66. Find Minimum Difference Between Any Two Elements
java
Copy
Edit
import java.util.Arrays;

public class MinDifference {
    public static int minDiff(int[] arr) {
        Arrays.sort(arr);
        int minDiff = Integer.MAX_VALUE;
        for(int i=1; i<arr.length; i++) {
            minDiff = Math.min(minDiff, arr[i] - arr[i-1]);
        }
        return minDiff;
    }
    public static void main(String[] args) {
        int[] arr = {1, 5, 3, 19, 18, 25};
        System.out.println("Minimum difference: " + minDiff(arr));
    }
}
67. Find the Equilibrium Index
java
Copy
Edit
public class EquilibriumIndex {
    public static int findEquilibriumIndex(int[] arr) {
        int totalSum = 0, leftSum = 0;
        for(int num : arr) totalSum += num;
        for(int i=0; i<arr.length; i++) {
            totalSum -= arr[i];
            if(leftSum == totalSum) return i;
            leftSum += arr[i];
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = { -7, 1, 5, 2, -4, 3, 0 };
        System.out.println("Equilibrium index: " + findEquilibriumIndex(arr));
    }
}
68. Check If Array Can Be Sorted by At Most One Swap

public class OneSwapSort {
    public static boolean canBeSortedByOneSwap(int[] arr) {
        int n = arr.length;
        int first = -1, second = -1;
        for(int i=0; i<n-1; i++) {
            if(arr[i] > arr[i+1]) {
                first = i;
                break;
            }
        }
        if(first == -1) return true;
        for(int j=n-1; j>0; j--) {
            if(arr[j] < arr[j-1]) {
                second = j;
                break;
            }
        }
        swap(arr, first, second);
        boolean sorted = true;
        for(int i=0; i<n-1; i++) {
            if(arr[i] > arr[i+1]) {
                sorted = false;
                break;
            }
        }
        swap(arr, first, second); // revert swap
        return sorted;
    }
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i]; arr[i] = arr[j]; arr[j] = temp;
    }
    public static void main(String[] args) {
        int[] arr = {1, 5, 3, 3, 7};
        System.out.println("Can be sorted by one swap: " + canBeSortedByOneSwap(arr));
    }
}
69. Find the Maximum Length of Repeated Subarray
java
Copy
Edit
public class MaxLengthRepeatedSubarray {
    public static int findLength(int[] A, int[] B) {
        int maxLen = 0;
        int[][] dp = new int[A.length+1][B.length+1];
        for(int i=1; i<=A.length; i++) {
            for(int j=1; j<=B.length; j++) {
                if(A[i-1] == B[j-1]) {
                    dp[i][j] = dp[i-1][j-1] + 1;
                    maxLen = Math.max(maxLen, dp[i][j]);
                }
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] A = {1,2,3,2,1};
        int[] B = {3,2,1,4,7};
        System.out.println("Max length of repeated subarray: " + findLength(A, B));
    }
}
70. Count Pairs with Given Sum
java
Copy
Edit
import java.util.HashMap;

public class CountPairsWithSum {
    public static int countPairs(int[] arr, int sum) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int count = 0;
        for(int num : arr) {
            int complement = sum - num;
            if(map.containsKey(complement)) {
                count += map.get(complement);
            }
            map.put(num, map.getOrDefault(num, 0) + 1);
        }
        return count;
    }
    public static void main(String[] args) {
        int[] arr = {1,5,7,-1,5};
        int sum = 6;
        System.out.println("Count of pairs with sum " + sum + ": " + countPairs(arr, sum));
    }
}
71. Find the Missing Number in 1 to N
java
Copy
Edit
public class MissingNumber {
    public static int findMissing(int[] arr, int n) {
        int total = n * (n+1) / 2;
        int sum = 0;
        for(int num : arr) sum += num;
        return total - sum;
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 6, 3, 7, 8};
        int n = 8;
        System.out.println("Missing number: " + findMissing(arr, n));
    }
}
72. Rearrange Array Alternately (max at even, min at odd positions)
java
Copy
Edit
import java.util.Arrays;

public class RearrangeArray {
    public static void rearrange(int[] arr) {
        int[] temp = arr.clone();
        Arrays.sort(temp);
        int left = 0, right = arr.length - 1;
        for(int i = 0; i < arr.length; i++) {
            if(i % 2 == 0) arr[i] = temp[right--];
            else arr[i] = temp[left++];
        }
    }
    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5, 6};
        rearrange(arr);
        System.out.println(Arrays.toString(arr));
    }
}
73. Find Peak Element in an Array
java
Copy
Edit
public class PeakElement {
    public static int findPeak(int[] arr) {
        int left = 0, right = arr.length - 1;
        while(left < right) {
            int mid = left + (right - left) / 2;
            if(arr[mid] < arr[mid + 1]) left = mid + 1;
            else right = mid;
        }
        return left;
    }
    public static void main(String[] args) {
        int[] arr = {1, 3, 20, 4, 1, 0};
        System.out.println("Peak element index: " + findPeak(arr));
    }
}
74. Find Longest Subarray of 1s After K Flips
java
Copy
Edit
public class LongestOnesAfterKFlips {
    public static int longestOnes(int[] arr, int k) {
        int left = 0, maxLen = 0, zeroCount = 0;
        for(int right = 0; right < arr.length; right++) {
            if(arr[right] == 0) zeroCount++;
            while(zeroCount > k) {
                if(arr[left] == 0) zeroCount--;
                left++;
            }
            maxLen = Math.max(maxLen, right - left + 1);
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {1,1,1,0,0,0,1,1,1,1,0};
        int k = 2;
        System.out.println("Longest subarray of 1s after flipping " + k + " zeros: " + longestOnes(arr, k));
    }
}
75. Find the Smallest Missing Positive Integer
java
Copy
Edit
public class SmallestMissingPositive {
    public static int findMissingPositive(int[] arr) {
        int n = arr.length;
        for(int i=0; i<n; i++) {
            while(arr[i] > 0 && arr[i] <= n && arr[i] != arr[arr[i]-1]) {
                int temp = arr[i];
                arr[i] = arr[temp - 1];
                arr[temp - 1] = temp;
            }
        }
        for(int i=0; i<n; i++) {
            if(arr[i] != i+1) return i+1;
        }
        return n+1;
    }
    public static void main(String[] args) {
        int[] arr = {3, 4, -1, 1};
        System.out.println("Smallest missing positive: " + findMissingPositive(arr));
    }
}
76. Find Maximum Product Subarray
java
Copy
Edit
public class MaxProductSubarray {
    public static int maxProduct(int[] arr) {
        int maxSoFar = arr[0], minSoFar = arr[0], result = arr[0];
        for(int i=1; i<arr.length; i++) {
            if(arr[i] < 0) {
                int temp = maxSoFar;
                maxSoFar = minSoFar;
                minSoFar = temp;
            }
            maxSoFar = Math.max(arr[i], maxSoFar * arr[i]);
            minSoFar = Math.min(arr[i], minSoFar * arr[i]);
            result = Math.max(result, maxSoFar);
        }
        return result;
    }
    public static void main(String[] args) {
        int[] arr = {2,3,-2,4};
        System.out.println("Maximum product subarray: " + maxProduct(arr));
    }
}
77. Find the Length of the Longest Palindromic Substring
java
Copy
Edit
public class LongestPalindromeSubstring {
    public static int longestPalindrome(String s) {
        int maxLen = 1;
        for(int i=0; i<s.length(); i++) {
            maxLen = Math.max(maxLen, expandAroundCenter(s, i, i));
            maxLen = Math.max(maxLen, expandAroundCenter(s, i, i+1));
        }
        return maxLen;
    }
    private static int expandAroundCenter(String s, int left, int right) {
        while(left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)) {
            left--; right++;
        }
        return right - left - 1;
    }
    public static void main(String[] args) {
        String str = "babad";
        System.out.println("Length of longest palindromic substring: " + longestPalindrome(str));
    }
}
78. Find the Number of Islands in a 2D Grid
java
Copy
Edit
public class NumberOfIslands {
    private static int rows, cols;
    public static int numIslands(char[][] grid) {
        if(grid == null || grid.length == 0) return 0;
        rows = grid.length;
        cols = grid[0].length;
        int count = 0;
        for(int i=0; i<rows; i++) {
            for(int j=0; j<cols; j++) {
                if(grid[i][j] == '1') {
                    count++;
                    dfs(grid, i, j);
                }
            }
        }
        return count;
    }
    private static void dfs(char[][] grid, int r, int c) {
        if(r < 0 || c < 0 || r >= rows || c >= cols || grid[r][c] == '0') return;
        grid[r][c] = '0';
        dfs(grid, r+1, c);
        dfs(grid, r-1, c);
        dfs(grid, r, c+1);
        dfs(grid, r, c-1);
    }
    public static void main(String[] args) {
        char[][] grid = {
            {'1','1','0','0','0'},
            {'1','1','0','0','0'},
            {'0','0','1','0','0'},
            {'0','0','0','1','1'}
        };
        System.out.println("Number of islands: " + numIslands(grid));
    }
}
79. Find the Maximum Length of Subarray with Equal Number of 0s and 1s
java
Copy
Edit
import java.util.HashMap;

public class MaxLengthEqualZeroOne {
    public static int findMaxLength(int[] nums) {
        HashMap<Integer, Integer> map = new HashMap<>();
        map.put(0, -1);
        int maxLen = 0, count = 0;
        for(int i=0; i<nums.length; i++) {
            count += (nums[i] == 1) ? 1 : -1;
            if(map.containsKey(count)) {
                maxLen = Math.max(maxLen, i - map.get(count));
            } else {
                map.put(count, i);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] nums = {0,1,0,1,0,1,1};
        System.out.println("Maximum length of subarray with equal 0 and 1: " + findMaxLength(nums));
    }
}
80. Find the Maximum Length of Subarray with Sum K
java
Copy
Edit
import java.util.HashMap;

public class MaxLengthSubarraySumK {
    public static int maxLength(int[] arr, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int sum = 0, maxLen = 0;
        map.put(0, -1);
        for(int i=0; i<arr.length; i++) {
            sum += arr[i];
            if(map.containsKey(sum - k)) {
                maxLen = Math.max(maxLen, i - map.get(sum - k));
            }
            if(!map.containsKey(sum)) {
                map.put(sum, i);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] arr = {1, -1, 5, -2, 3};
        int k = 3;
        System.out.println("Maximum length of subarray with sum " + k + ": " + maxLength(arr, k));
    }
}
81. Find All Duplicates in an Array
java
Copy
Edit
import java.util.ArrayList;
import java.util.List;

public class FindDuplicates {
    public static List<Integer> findDuplicates(int[] nums) {
        List<Integer> duplicates = new ArrayList<>();
        for(int i=0; i<nums.length; i++) {
            int index = Math.abs(nums[i]) - 1;
            if(nums[index] < 0) duplicates.add(index + 1);
            else nums[index] = -nums[index];
        }
        return duplicates;
    }
    public static void main(String[] args) {
        int[] nums = {4,3,2,7,8,2,3,1};
        System.out.println("Duplicates: " + findDuplicates(nums));
    }
}
82. Move Zeroes to End of Array
java
Copy
Edit
import java.util.Arrays;

public class MoveZeroes {
    public static void moveZeroes(int[] nums) {
        int j = 0;
        for(int num : nums) {
            if(num != 0) nums[j++] = num;
        }
        while(j < nums.length) {
            nums[j++] = 0;
        }
    }
    public static void main(String[] args) {
        int[] nums = {0,1,0,3,12};
        moveZeroes(nums);
        System.out.println(Arrays.toString(nums));
    }
}
83. Rotate Array by K Steps (Right Rotation)
java
Copy
Edit
import java.util.Arrays;

public class RotateArray {
    public static void rotate(int[] nums, int k) {
        k = k % nums.length;
        reverse(nums, 0, nums.length - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.length - 1);
    }
    private static void reverse(int[] nums, int start, int end) {
        while(start < end) {
            int temp = nums[start];
            nums[start++] = nums[end];
            nums[end--] = temp;
        }
    }
    public static void main(String[] args) {
        int[] nums = {1,2,3,4,5,6,7};
        rotate(nums, 3);
        System.out.println(Arrays.toString(nums));
    }
}
84. Find the Majority Element (> n/2 times)
java
Copy
Edit
public class MajorityElement {
    public static int majorityElement(int[] nums) {
        int count = 0, candidate = 0;
        for(int num : nums) {
            if(count == 0) candidate = num;
            count += (num == candidate) ? 1 : -1;
        }
        return candidate;
    }
    public static void main(String[] args) {
        int[] nums = {2,2,1,1,1,2,2};
        System.out.println("Majority element: " + majorityElement(nums));
    }
}
85. Find Minimum in Rotated Sorted Array
java
Copy
Edit
public class MinInRotatedArray {
    public static int findMin(int[] nums) {
        int left = 0, right = nums.length - 1;
        while(left < right) {
            int mid = left + (right - left) / 2;
            if(nums[mid] > nums[right]) left = mid + 1;
            else right = mid;
        }
        return nums[left];
    }
    public static void main(String[] args) {
        int[] nums = {4,5,6,7,0,1,2};
        System.out.println("Minimum element: " + findMin(nums));
    }
}
86. Find Peak Index in a Mountain Array
java
Copy
Edit
public class PeakIndexMountain {
    public static int peakIndexInMountainArray(int[] arr) {
        int left = 0, right = arr.length - 1;
        while(left < right) {
            int mid = left + (right - left) / 2;
            if(arr[mid] < arr[mid + 1]) left = mid + 1;
            else right = mid;
        }
        return left;
    }
    public static void main(String[] args) {
        int[] arr = {0,2,1,0};
        System.out.println("Peak index: " + peakIndexInMountainArray(arr));
    }
}
87. Maximum Subarray Sum (Kadane's Algorithm)
java
Copy
Edit
public class MaxSubarraySum {
    public static int maxSubArray(int[] nums) {
        int maxSoFar = nums[0], maxEndingHere = nums[0];
        for(int i=1; i<nums.length; i++) {
            maxEndingHere = Math.max(nums[i], maxEndingHere + nums[i]);
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }
        return maxSoFar;
    }
    public static void main(String[] args) {
        int[] nums = {-2,1,-3,4,-1,2,1,-5,4};
        System.out.println("Maximum subarray sum: " + maxSubArray(nums));
    }
}
88. Find Intersection of Two Arrays
java
Copy
Edit
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class IntersectionArrays {
    public static int[] intersection(int[] nums1, int[] nums2) {
        Set<Integer> set1 = new HashSet<>();
        for(int num : nums1) set1.add(num);
        Set<Integer> intersection = new HashSet<>();
        for(int num : nums2) {
            if(set1.contains(num)) intersection.add(num);
        }
        int[] result = new int[intersection.size()];
        int i=0;
        for(int num : intersection) result[i++] = num;
        return result;
    }
    public static void main(String[] args) {
        int[] nums1 = {1,2,2,1};
        int[] nums2 = {2,2};
        System.out.println(Arrays.toString(intersection(nums1, nums2)));
    }
}
89. Find Two Sum (Indices)
java
Copy
Edit
import java.util.HashMap;

public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int i=0; i<nums.length; i++) {
            int complement = target - nums[i];
            if(map.containsKey(complement)) return new int[]{map.get(complement), i};
            map.put(nums[i], i);
        }
        return new int[]{-1, -1};
    }
    public static void main(String[] args) {
        int[] nums = {2,7,11,15};
        int target = 9;
        int[] res = twoSum(nums, target);
        System.out.println("Indices: [" + res[0] + ", " + res[1] + "]");
    }
}
90. Find Subarray with Given Sum (Positive Numbers)
java
Copy
Edit
public class SubarraySum {
    public static int[] subarraySum(int[] nums, int target) {
        int start = 0, sum = 0;
        for(int end=0; end<nums.length; end++) {
            sum += nums[end];
            while(sum > target) {
                sum -= nums[start++];
            }
            if(sum == target) {
                return new int[]{start, end};
            }
        }
        return new int[]{-1, -1};
    }
    public static void main(String[] args) {
        int[] nums = {1,2,3,7,5};
        int target = 12;
        int[] res = subarraySum(nums, target);
        System.out.println("Subarray indices: [" + res[0] + ", " + res[1] + "]");
    }
}
91. Find the First Missing Positive Number
java
Copy
Edit
public class FirstMissingPositive {
    public static int firstMissingPositive(int[] nums) {
        int n = nums.length;
        for(int i=0; i<n; i++) {
            while(nums[i] > 0 && nums[i] <= n && nums[nums[i]-1] != nums[i]) {
                int temp = nums[nums[i]-1];
                nums[nums[i]-1] = nums[i];
                nums[i] = temp;
            }
        }
        for(int i=0; i<n; i++) {
            if(nums[i] != i+1) return i+1;
        }
        return n+1;
    }
    public static void main(String[] args) {
        int[] nums = {3,4,-1,1};
        System.out.println("First missing positive: " + firstMissingPositive(nums));
    }
}
92. Check if Array is Monotonic
java
Copy
Edit
public class MonotonicArray {
    public static boolean isMonotonic(int[] nums) {
        boolean increasing = true, decreasing = true;
        for(int i=1; i<nums.length; i++) {
            if(nums[i] > nums[i-1]) decreasing = false;
            if(nums[i] < nums[i-1]) increasing = false;
        }
        return increasing || decreasing;
    }
    public static void main(String[] args) {
        int[] nums = {1,2,2,3};
        System.out.println("Is monotonic: " + isMonotonic(nums));
    }
}
93. Find Maximum Gap Between Sorted Adjacent Elements
java
Copy
Edit
import java.util.Arrays;

public class MaximumGap {
    public static int maximumGap(int[] nums) {
        if(nums.length < 2) return 0;
        Arrays.sort(nums);
        int maxGap = 0;
        for(int i=1; i<nums.length; i++) {
            maxGap = Math.max(maxGap, nums[i] - nums[i-1]);
        }
        return maxGap;
    }
    public static void main(String[] args) {
        int[] nums = {3,6,9,1};
        System.out.println("Maximum gap: " + maximumGap(nums));
    }
}
94. Find Elements That Appear Once in an Array Where Others Appear Twice
java
Copy
Edit
public class SingleNumber {
    public static int singleNumber(int[] nums) {
        int result = 0;
        for(int num : nums) {
            result ^= num;
        }
        return result;
    }
    public static void main(String[] args) {
        int[] nums = {4,1,2,1,2};
        System.out.println("Single number: " + singleNumber(nums));
    }
}
95. Sort Array by Parity (Even numbers first)
java
Copy
Edit
import java.util.Arrays;

public class SortArrayByParity {
    public static int[] sortArrayByParity(int[] nums) {
        int left = 0, right = nums.length - 1;
        while(left < right) {
            if(nums[left] % 2 > nums[right] % 2) {
                int temp = nums[left];
                nums[left] = nums[right];
                nums[right] = temp;
            }
            if(nums[left] % 2 == 0) left++;
            if(nums[right] % 2 == 1) right--;
        }
        return nums;
    }
    public static void main(String[] args) {
        int[] nums = {3,1,2,4};
        System.out.println(Arrays.toString(sortArrayByParity(nums)));
    }
}
96. Find the Longest Consecutive Sequence
java
Copy
Edit
import java.util.HashSet;

public class LongestConsecutiveSequence {
    public static int longestConsecutive(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for(int num : nums) set.add(num);
        int maxLen = 0;
        for(int num : nums) {
            if(!set.contains(num - 1)) {
                int currentNum = num;
                int currentLen = 1;
                while(set.contains(currentNum + 1)) {
                    currentNum++;
                    currentLen++;
                }
                maxLen = Math.max(maxLen, currentLen);
            }
        }
        return maxLen;
    }
    public static void main(String[] args) {
        int[] nums = {100,4,200,1,3,2};
        System.out.println("Longest consecutive sequence length: " + longestConsecutive(nums));
    }
}
97. Find Duplicate Number (One number repeated)
java
Copy
Edit
public class FindDuplicate {
    public static int findDuplicate(int[] nums) {
        int slow = nums[0], fast = nums[0];
        do {
            slow = nums[slow];
            fast = nums[nums[fast]];
        } while(slow != fast);
        slow = nums[0];
        while(slow != fast) {
            slow = nums[slow];
            fast = nums[fast];
        }
        return slow;
    }
    public static void main(String[] args) {
        int[] nums = {1,3,4,2,2};
        System.out.println("Duplicate number: " + findDuplicate(nums));
    }
}
98. Find the Minimum Window Subarray Containing All Elements of Another Array
java
Copy
Edit
import java.util.HashMap;

public class MinWindowSubarray {
    public static int[] minWindow(int[] nums, int[] target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int num : target) map.put(num, map.getOrDefault(num, 0) + 1);
        int left = 0, count = target.length, minLen = Integer.MAX_VALUE, start = 0;
        for(int right=0; right<nums.length; right++) {
            if(map.containsKey(nums[right])) {
                map.put(nums[right], map.get(nums[right]) - 1);
                if(map.get(nums[right]) >= 0) count--;
            }
            while(count == 0) {
                if(right - left + 1 < minLen) {
                    minLen = right - left + 1;
                    start = left;
                }
                if(map.containsKey(nums[left])) {
                    map.put(nums[left], map.get(nums[left]) + 1);
                    if(map.get(nums[left]) > 0) count++;
                }
                left++;
            }
        }
        return minLen == Integer.MAX_VALUE ? new int[]{} : new int[]{start, start + minLen - 1};
    }
    public static void main(String[] args) {
        int[] nums = {7,5,9,0,2,1,3,5,7,9,1,1,5,8,8,9,7};
        int[] target = {1,5,9};
        int[] res = minWindow(nums, target);
        if(res.length == 0) System.out.println("No valid window");
        else System.out.println("Minimum window: [" + res[0] + ", " + res[1] + "]");
    }
}
99. Find the Maximum Product of Three Numbers
java
Copy
Edit
import java.util.Arrays;

public class MaxProductThreeNumbers {
    public static int maximumProduct(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;
        return Math.max(nums[n-1]*nums[n-2]*nums[n-3], nums[0]*nums[1]*nums[n-1]);
    }
    public static void main(String[] args) {
        int[] nums = {1,2,3,4};
        System.out.println("Maximum product of three numbers: " + maximumProduct(nums));
    }
}
100. Sort Colors (Dutch National Flag Problem)
java
Copy
Edit
import java.util.Arrays;

public class SortColors {
    public static void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;
        while(mid <= high) {
            if(nums[mid] == 0) {
                int temp = nums[low];
                nums[low++] = nums[mid];
                nums[mid++] = temp;
            } else if(nums[mid] == 1) {
                mid++;
            } else {
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high--] = temp;
            }
        }
    }
    public static void main(String[] args) {
        int[] nums = {2,0,2,1,1,0};
        sortColors(nums);
        System.out.println(Arrays.toString(nums));
    }
}




