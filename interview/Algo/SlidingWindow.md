Patterns of sliding window concepts

1. Sum of the asked number of array elements and check them in every window.
2. Provided a sum. Move the window according to greater or equal the sum of continuous elements.
3. The longest substring is no more than K, a distinct character. Use a HashMap/Array[26] to track the number of distinct chars and find the substring
4. Longest substring with distinct character. Keep track of the right char index position in a hashmap. Also, change the window start if the  right char repeats. It should update with the latest right char position.
5. Longest Substring with Same Letters after Replacement. We have to track max repeated letter count. So that we can find which is the max repeated char in a window based on that we can remove some char from the beginning.
6. string contains any permutation of the pattern. We have to create a frequency map of the pattern string. Then we can check each window by adding a single character in a window. return true/false if based on finding.
7. Smallest Window containing Substring.In this problem, we need to find a substring having all characters of the pattern which means that the required substring can have some additional characters and doesn’t need to be a permutation of the pattern. To handle this we have to shrink the window from the start when all characters are found. Otherwise, keep growing the window from the end.
8. concatenation of all the given words exactly once without any overlapping of words. To solve this issue we have to start a loop from which will add a single character in each iteration and also start another loop that will extract the word and check in the map whether it exists or not and also check the count. 
