1550. Three Consecutive Odds


Given an integer array arr, return true if there are three consecutive odd numbers in the array. Otherwise, return false.


import java.util.*;
class Solution {
    public int[] findEvenNumbers(int[] digits) {
        Set<Integer> result = new TreeSet<>();
        int n = digits.length;
        for (int i = 0; i < n; i++) {
            if (digits[i] == 0) continue; 
            for (int j = 0; j < n; j++) {
                if (j == i) continue;
                for (int k = 0; k < n; k++) {
                    if (k == i || k == j) continue;
                    int num = digits[i] * 100 + digits[j] * 10 + digits[k];
                    if (num % 2 == 0) {
                        result.add(num);
                    }
                }
            }
        }
        int[] output = new int[result.size()];
        int index = 0;
        for (int num : result) {
            output[index++] = num;
        }
        return output;
    }
}
