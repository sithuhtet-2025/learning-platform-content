In Java, an array is a linear data structure that has a collection of the same data type. These elements are stored in a contiguous memory location. In this section, we will discuss a variety of array programs, including array operations, manipulation, sorting, searching, etc.

## Java Array Programs

Here you will find the top 30 Java array programs based on different operations, along with source code, output, and proper explanation.

### 1. Java program to find the sum of the array elements.

To find the sum of the array's elements, first we have defined and declared an array. After that, we have defined a sum() method that adds array elements. Inside this method, the loop iterates over each element of the array and adds an element to the sum variable, repeatedly. In the main() method, we have called the sum() method that returns the sum of the array elements.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. class Main {  
2.     static int arr[] = { 7, 4, 10, 9, 13, 26 };  
3.     // method for the sum of elements   
4.     static int sum()  
5.     {  
6.         int i, sum = 0;   
7.         // Iterate through all elements and add them to the sum  
8.         for (i = 0; i < arr.length; i++)  
9.             sum += arr[i];  
10.         return sum;  
11.     }  
12.     public static void main(String[] args)  
13.     {  
14.         System.out.println("The sum of the given array is: "+ sum());  
15.     }  
16. }  

**Output:**

The sum of the given array is: 69

### 2. Java program to find the reverse of an array.

Reversing an array means writing an array from the last element to the first element. First, we have initializead an array. The loop iterates over the array until the array is reversed. We swap the first element with the last, the second with the second last, and so on. At last, we convert the array into a string and print the reversed array.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {       
4.         int[] arr = {1, 2, 3, 4, 5};  
5.         // Swap elements from start to end  
6.         for (int i = 0; i < arr.length / 2; i++) {  
7.             int t = arr[i];  
8.             arr[i] = arr[arr.length - 1 - i];  
9.             arr[arr.length - 1 - i] = t;  
10.         }  
11.         System.out.println("" + Arrays.toString(arr));  
12.     }  
13. }  

**Output:**

[5, 4, 3, 2, 1]

### 3. Java program to merge two arrays.

There are various ways to merge two arrays. But in this program, we have used user-defined logic to merge two arrays. This method is useful when we need full control over the merging process without relying on built-in functions. It directly merges the arrays.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         int arr1[] = { 23, 45, 56, 78, 90};  
5.         int arr2[] = { 3, 4, 6, 8, 9, 0, 7};  
6.         // determining the length of both arrays  
7.         int sizearr1 = arr1.length;  
8.         int sizearr2 = arr2.length;  
9.         // resultant array size  
10.         int sizearr3 = sizearr1 + sizearr2;  
11.         // Creating a new array   
12.         int[] arr3 = new int[sizearr3];  
13.         // Loop to store the elements of the first array into the resultant array  
14.         for (int i = 0; i < sizearr1; i = i + 1) {    
15.             // Storing the elements in the resultant array  
16.             arr3[i] = arr1[i];  
17.         }  
18.         // Loop to concatenate the elements of the second array into the resultant array  
19.         for (int i = 0; i < sizearr2; i = i + 1) {  
20.             // Storing the elements in the resultant array  
21.             arr3[sizearr1 + i] = arr2[i];  
22.         }  
23.         System.out.println("" + Arrays.toString(arr3));  
24.     }  
25. }  

**Output:**

[23, 45, 56, 78, 90, 3, 4, 6, 8, 9, 0, 7]

### 4. Java program to find the second most significant element in a sorted matrix.

In a sorted matrix, the rows and columns of the elements are placed in ascending order. We can navigate the matrix and note the largest and second-largest elements to determine the second-largest element. The second-largest element will have been stored when the traverse is complete.

The program uses a simple approach to find the second-largest element in a sorted matrix. It applies a nested loop to traverse the matrix in reverse order and compares each element with the largest and second-largest elements found so far. The program updates the largest and second-largest variables accordingly. Finally, it prints the value of the second-largest element.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main  
2. {    
3.     public static void main(String[] args)     
4.     {    
5.         int[][] matrix =     
6.         {    
7.             {1,2,3},    
8.             {4,5,6},    
9.             {7,8,9}    
10.         };    
11.         int rows=matrix.length;    
12.         int cols=matrix[0].length;    
13.         int largest=matrix[rows-1][cols-1]; // Initialize largest with the bottom-right element    
14.         int secondLargest=matrix[rows-1][cols-2]; // Initialize secondLargest with the element before largest    

15.         // Traverse the matrix in reverse order    
16.         for (int i=rows-1;i>=0;i--)     
17.         {    
18.             for (int j=cols-1;j>=0;j--)     
19.             {    
20.                 if (matrix[i][j]>largest)     
21.                 {    
22.                     secondLargest=largest; // Update secondLargest to the previous largest    
23.                     largest=matrix[i][j]; // Update largest to the new largest element    
24.                 }     
25.               else if(matrix[i][j]>secondLargest&&matrix[i][j]<largest)     
26.                 {    
27.                     secondLargest=matrix[i][j];     
28.                 }    
29.             }    
30.         }    
31.         System.out.println("Second largest element in the sorted matrix is: "+secondLargest);    
32.     }    
33. }    

**Output:**

Second largest element in the sorted matrix is: 8

**Complexity Analysis**

**Time Complexity:** O(rows * cols), where rows and cols are the dimensions of the matrix.

**Space Complexity:** O(1), as we use constant additional space.

### 5. Java program to find the k-th smallest element in a sorted matrix.

In a sorted matrix, elements are arranged in ascending order, both row-wise and column-wise. The task is to find the kth smallest element in the matrix.

The program uses a min-heap implemented with a PriorityQueue to find the kth smallest element in a sorted matrix. The findKthSmallest() method initializes the minHeap and adds the elements from the first column. It then performs k-1 iterations, extracting the minimum element, finding its indices, and adding the next element from the same row to the minHeap. Finally, the method returns the kth smallest element. The main function showcases the method by providing a sample matrix and k value.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.*;    
2. public class Main    
3. {    
4.     public static int findKthSmallest(int[][] matrix,int k)     
5.     {    
6.         int rows=matrix.length;    
7.         int cols=matrix[0].length;    
8.         PriorityQueue<Integer> minHeap=new PriorityQueue<>();    
9.         for (int i=0;i<rows;i++) {    
10.             minHeap.add(matrix[i][0]);    
11.         }    
12.         // Perform k-1 iterations    
13.         for (int i=0;i<k-1;i++)     
14.         {    
15.             int minElement=minHeap.poll(); // Extract the minimum element    
16.             // Get the row and column index of the extracted element    
17.             int rowIndex=-1;    
18.             int colIndex=-1;    
19.             for (int j=0;j<rows;j++)     
20.             {    
21.                 for (int p=0;p<cols;p++)     
22.                 {    
23.                     if (matrix[j][p]==minElement)     
24.                     {    
25.                         rowIndex=j;    
26.                         colIndex=p+1;    
27.                         break;    
28.                     }    
29.                 }    
30.             }    
31.             // Add the next element from the same row to the min-heap    
32.             if (colIndex<cols) {    
33.                 minHeap.add(matrix[rowIndex][colIndex]);    
34.             }    
35.         }    
36.         return minHeap.peek(); // Return the kth smallest element    
37.     }    
38.     public static void main(String[] args)     
39.     {    
40.         int[][] matrix={    
41.             {1,3,5},    
42.             {6,7,12},    
43.             {11,14,14}    
44.         };    
45.         int k=4;    
46.         int kthSmallest=findKthSmallest(matrix,k);    
47.         System.out.println("The "+ k+"-th smallest element in the sorted matrix is: "+kthSmallest);    
48.     }    
49. }    

**Output:**

The 4-th smallest element in the sorted matrix is: 6

**Complexity Analysis**

**Time Complexity:** The time complexity is O(k * log(rows)).

**Space Complexity:** The space complexity is O(rows) for storing the elements in the min-heap.

### 6. Java program to remove duplicate elements from a sorted array.

In a sorted array, duplicate elements may occur consecutively. To put off duplicates from a looked-after array, we need to adjust the array in-place, making sure that each detail appears as effective as soon as. The Java program removes duplicates from a sorted array using the "RemoveDuplicates" class. The method "removeDuplicates" returns the new length of the modified array without duplicates. It checks if the array is empty, initializes "nextUnique" to 1, and traverses the array starting from the second element. It assigns unique elements to the position of "nextUnique" and increments it. After the loop, "nextUnique" represents the new length. The "main" function showcases the method by printing the modified array.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.*;    
2. public class Main    
3. {    
4.     public static int removeDuplicates(int[] nums)     
5.     {    
6.         int n=nums.length;    
7.         if (n==0)     
8.         {    
9.             return 0;     
10.         }    
11.         int nextUnique=1;     
12.         // Pointer to track the position of the next unique element    
13.         // Traverse the array starting from the second element    
14.         for (int current=1;current<n;current++)     
15.         {    
16.             // Compare the current element with the element at the next unique - 1    
17.             if (nums[current]!=nums[nextUnique-1])     
18.             {    
19.    nums[nextUnique]=nums[current]; // Assign current element to nextUnique position    
20.                 nextUnique++; // Increment nextUnique    
21.             }    
22.         }    
23.         return nextUnique;     
24.     }    
25.     public static void main(String[] args)     
26.     {    
27.         int[] nums={1,1,2,2,3,4,4,5};    
28.         int length=removeDuplicates(nums);    
29.         System.out.print("Modified Array: ");    
30.         for (int i=0;i<length;i++)     
31.         {    
32.             System.out.print(nums[i]+" ");    
33.         }    
34.     }    
35. }    

**Output:**

Modified Array: 1 2 3 4 5

**Complexity Analysis**

Time Complexity is O(n), where n is the array's element count.

Space complexity is O(1) since the array is modified directly without additional data structures.

### 7. Java program to find the frequency of each word in a string array.

We shall calculate the frequency of each word in a string array using a Java program. In a list of strings, we want to know how frequently each word appears. To calculate the frequency of each word in a string array, the program employs a hash map.

A simple approach separates each string into words, and the number of each word is then saved in the hash map. After initializing a blank HashMap, the program loops through each string in the array. It determines if a word is present in the HashMap for each one it encounters.

If it does, the frequency increases; if not, it is set to 1, and the word is added to the hash map. Finally, the program prints the word-frequency pairs stored in the HashMap. The approach efficiently tracks and counts the occurrences of each word, allowing for accurate frequency analysis of the words in the string array.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.*;    
2. public class Main   
3. {    
4.     public static void main(String[] args)     
5.     {    
6.         String[] strings={"Hello world","Hello Java","Java is great","Java is powerful"};         // Create a HashMap to store word-frequency pairs    
7.         Map<String,Integer> frequencyMap=new HashMap<>();    
8.         for (String str:strings)     
9.         {    
10.             // Split the string into words using whitespace as the delimiter    
11.             String[] words=str.split("\\s+");    
12.             // Count the occurrences of each word    
13.             for (String word:words)     
14.             {    
15.                 // Check if the word already exists in the HashMap    
16.                 if (frequencyMap.containsKey(word))     
17.                 {    
18.                     // If it exists, increment its frequency by 1    
19.                     frequencyMap.put(word,frequencyMap.get(word)+1);    
20.                 } else {    
21.                     // If it does not exist, add it to the HashMap with a frequency of 1    
22.                     frequencyMap.put(word,1);    
23.                 }    
24.             }    
25.         }    
26.         // Print the word-frequency pairs    
27.         for (Map.Entry<String, Integer> entry : frequencyMap.entrySet()) {    
28.             System.out.println("Word: " + entry.getKey() + ", Frequency: " + entry.getValue());    
29.         }    
30.     }    
31. }    

**Output:**

Word: Java, Frequency: 3
Word: world, Frequency: 1
Word: Hello, Frequency: 2
Word: powerful, Frequency: 1
Word: is, Frequency: 2
Word: great, Frequency: 1

**Complexity Analysis**

The time complexity is O(n*m), where n represents the number of strings within the array and m is the maximum common sort of phrase in every string.

The space complexity of the program is O(n), where n is the total wide variety of words inside the array.

### 8. Java program to find the missing number in a sorted array of consecutive integers.

Using the binary search method, we locate the missing integer in a sorted array of succeeding integers. The first detail's index is low, and the remaining is high. We determine whether or not the missing integer is on the left or proper side of the array by computing the expected value for the middle element, which ought to be the same as the first element plus the centre index. The operation is repeated until there is only one element left in the search space, at which point we update low or high as necessary. The missing number will be the expected value at the index low.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main   
2. {    
3.     public static int findMissingNumber(int[] nums)     
4.     {    
5.         int low=0;    
6.         int high=nums.length-1;    
7.         // Perform binary search    
8.         while (low<=high)     
9.         {    
10.             int mid=low+(high-low)/2;    
11.             int expectedValue=nums[0]+mid;    
12.             if (nums[mid]==expectedValue)     
13.             {    
14.                 // Missing number lies in the right half    
15.                 low=mid+1;    
16.             } else     
17.             {    
18.                 // Missing number lies in the left half    
19.                 high=mid-1;    
20.             }    
21.         }    
22.         // Return the missing number    
23.         return nums[0]+low;    
24.     }    
25.     public static void main(String[] args)     
26.     {    
27.         int[] nums={1,2,3,4,6,7,8,9};    
28.         int missingNumber=findMissingNumber(nums);    
29.         System.out.println("Missing number: "+missingNumber);    
30.     }    
31. }    

**Output:**

Missing number: 5

**Complexity Analysis**

**Time Complexity:** The binary search approach has a time complexity of O(log n), where n is the size of the array

**Space Complexity:** The program has a space complexity of O(1), only using a few variables to track the low, high, and mid indices and the expected value.

### 9. Java program to find the element that appears only once in an array.

The technique used to find the element that appears most effectively at least once in an array is primarily based on the XOR operation. By XORing all the factors within the array, the factors that seem a fair number of instances will cancel out, leaving only the detail that appears best once. To enforce this approach, we initialize a variable 'unique' to zero. Then, we iterate through each detail inside the array and XOR it with the 'particular' variable. The result is stored back in 'unique.' At the end of the iteration, 'unique' will hold the element's value that appears only once.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main     
2. {    
3.     public static int findUnique(int[] nums)     
4.     {    
5.         int unique=0;    
6.         for (int num:nums)     
7.         {    
8.             unique^=num; // XOR the current element with 'unique'    
9.         }    
10.         return unique;    
11.     }    

12.     public static void main(String[] args)     
13.     {    
14.         int[] nums = {1,2,3,4,3,2,1};    
15.         int uniqueElement=findUnique(nums);    
16.         System.out.println("The element that appears only once: " + uniqueElement);    
17.     }    
18. }    

**Output:**

The element that appears only once: 4

**Complexity Analysis**

**Time Complexity:** The time complexity of this technique is O(n), where n is the length of the array.

**Space Complexity:** The Space complexity is O(1) because we simplest use a single variable to keep the result.

### 10. Java program to check if an array is a palindrome.

To check if an array is a palindrome, we will use a pointer method where one pointer starts evolving at the start of the array and the alternative at the end. The elements are as compared to those suggestions, and we move them closer and nearer collectively until they meet at the centre. We conclude that the array is not a palindrome if the elements at any point at the pointers are not equal. Otherwise, if the loop completes without finding any unequal elements, then the array is a palindrome. The two-pointer approach allows us to efficiently check for palindromicity by eliminating the need for additional space.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main  
2. {    
3.     public static boolean isPalindrome(int[] nums)     
4.     {    
5.         int left=0;                     // Initialize the left pointer at the beginning of the array    
6.         int right=nums.length-1;      // Initialize the right pointer at the end of the array    
7. while (left<=right) {      // Continue the loop until the pointers meet or cross each other    
8.  if (nums[left]!=nums[right])     
9. {    
10.    return false;             // If the elements at the pointers are not equal, the array is not a palindrome    
11.             }    
12.             left++;                           
13.             right--;                          
14.         }    
15.  return true;    // If the loop completes without finding unequal elements, the array is a palindrome    
16.     }    
17.     public static void main(String[] args) {    
18.         int[] nums={1,2,3,2,1};       
19.         boolean isPalindrome=isPalindrome(nums);      
20.         if (isPalindrome)     
21.        {    
22.             System.out.println("The array is a palindrome.");    
23.         }     
24.        else     
25.        {    
26.             System.out.println("The array is not a palindrome.");    
27.         }    
28.     }    
29. }  

**Output:**

The array is a palindrome.

**Complexity Analysis**

The time complexity of the above approach is O(n), where n is the length of the array.

The space complexity is O(1) as we are not using any extra space.

### 11. Java program to shuffle elements of an array.

To shuffle the elements of an array, we use the Fisher-Yates shuffle algorithm is commonly used. The procedure ensures that each array's item is randomly permuted. Starting with the final entry in the array, the process iterates through the array in reverse order to get started. Each time, the current element is added to the range of the remaining unshrunk elements to create a random index. The element at the current index is then swapped with the element at the randomly generated index. The swapping continues until the first element is reached, resulting in a shuffled array with elements in random order.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.Random;    
2. public class Main     
3. {    
4.     public static void shuffle(int[] nums)     
5.     {    
6.         Random rand=new Random();    
7.         for (int i=nums.length-1;i>=1;i--)     
8.         {    
9.             int j=rand.nextInt(i+1);    
10.             // Swap the current element with the randomly selected element    
11.             int temp=nums[i];    
12.             nums[i]=nums[j];    
13.             nums[j]=temp;    
14.         }    
15.     }    
16.     public static void main(String[] args)     
17.     {    
18.         int[] nums = {1,2,3,4,5};    
19.         System.out.println("Original array: ");    
20.         for (int num:nums)     
21.       {    
22.             System.out.print(num + " ");    
23.         }    
24.         shuffle(nums);    
25.         System.out.println("\nShuffled array: ");    
26.         for (int num:nums)     
27.       {    
28.             System.out.print(num + " ");    
29.         }    
30.     }    
31. }    

**Output:**

Original array:
1 2 3 4 5
Shuffled array:
5 2 1 3 4

**Complexity Analysis**

The time complexity of this technique is O(N), where N is the size of the array.

The space complexity is O(1) since we use a consistent quantity of extra space for the random variety.

### 12. Java program to check if two matrices are orthogonal.

To examine if two matrices are orthogonal, we evaluate the dot manufactured of corresponding rows or columns of the matrices. The matrices are said to be orthogonal if the dot product is 0 for all pairs. The algorithm iterates through the rows or columns, then calculates the dot product and returns false if any dot product is non-zero. It then checks for appropriate dimensions. If all dot products are zero, it returns true to indicate that the matrices are orthogonal.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main    
2. {    
3.     public static boolean areMatricesOrthogonal(int[][] matrix1,int[][] matrix2)     
4. {    
5.         int rows1=matrix1.length;    
6.         int cols1=matrix1[0].length;    
7.         int rows2=matrix2.length;    
8.         int cols2=matrix2[0].length;    
9.         // Check if matrices have compatible dimensions    
10.         if (rows1 != rows2 || cols1 != cols2) {    
11.             return false;    
12.         }    
13.         // Check the dot product for each row/column pair    
14.         for (int i=0;i<rows1;i++) {    
15.             int dotProduct = 0;    
16.             for (int j=0;j<cols1;j++) {    
17.                 dotProduct += matrix1[i][j] * matrix2[i][j];    
18.             }    
19.             if (dotProduct!=0)     
20.             {    
21.                 return false;    
22.             }    
23.         }    
24.         return true;    
25.     }    
26.     public static void main(String[] args) {    
27.         int[][] matrix1={{1,2},{3,4}};    
28.         int[][] matrix2={{0,1},{-1,0}};    

29.         boolean areOrthogonal = areMatricesOrthogonal(matrix1, matrix2);    
30.         if (areOrthogonal) {    
31.             System.out.println("The matrices are orthogonal.");    
32.         } else {    
33.             System.out.println("The matrices are not orthogonal.");    
34.         }    
35.     }    
36. }    

**Output:**

The matrices are not orthogonal.

**Complexity Analysis:**

The time complexity of this technique is O(n), where n is the range of rows or columns in the matrices.

The space complexity is O(1), as no additional data structures are used.

### 13. Java program to find the maximum element in a two-dimensional array.

We initialize the variable ' max' with the smallest value conceivable given the data type of the array elements to determine the greatest element in a two-dimensional array. The next step is to loop separately via the array's rows and factors. Every element is compared to the modern fee of "max," and if the detail is more, "max" is up to date. The maximum element in the two-dimensional array will be contained in 'max' once all items have been iterated through. By comparing each element to the current maximum value, the method enables us to determine the maximum element quickly.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main  
2. {    
3.     public static int findMaximumElement(int[][] array) {    
4.         int max=Integer.MIN_VALUE; // Initialize max with the minimum value    
5.         for (int i=0;i<array.length;i++)     
6.         {    
7.             // Iterate through each element of the row    
8.             for (int j=0;j<array[i].length;j++)     
9.             {    
10.                 // Compare the current element with the current max value    
11.                 if (array[i][j] > max) {    
12.                     max=array[i][j];     
13.                 }    
14.             }    
15.         }    
16.         return max; // Return the maximum element    
17.     }    
18.     public static void main(String[] args) {    
19.         int[][] array={    
20.             {1, 2, 3},    
21.             {4, 5, 6},    
22.             {7, 8, 9}    
23.         };    
24.         int maximum=findMaximumElement(array);    
25.         System.out.println("The maximum element in the array is: "+maximum);    
26.     }    
27. }    

**Output:**

The maximum element in the array is: 9

**Complexity Analysis**

The time complexity of this approach is O(n * m), where n is the number of rows and m is the number of columns in the two-dimensional array.

The space complexity is O(1) when you consider that we are not the usage of any extra area that grows with the entered size.

### 14. Java program to find the sum of each diagonal in a matrix.

To find the sum of each diagonal in a matrix, we iterate through the elements and calculate the diagonal index of every component by summing its row and column indices. We then add the element's value to the corresponding diagonal sum in an array. After processing all elements, the array will contain the sum of each diagonal.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {    
2.     public static int[] getDiagonalSums(int[][] matrix) {    
3.         int rows=matrix.length;    
4.         int cols=matrix[0].length;    
5.         int numDiagonals=rows+cols-1;    
6.         int[] sums=new int[numDiagonals];    
7.         for (int i=0;i<rows;i++)   {    
8.             for (int j=0;j<cols;j++)    {    
9.                 int diagonalIndex=i+j;    
10.                 sums[diagonalIndex]+=matrix[i][j];    
11.             }    
12.         }    
13.         return sums;    
14.     }    
15.     public static void main(String[] args) {    
16.         int[][] matrix={    
17.             {1, 2, 3},    
18.             {4, 5, 6},    
19.             {7, 8, 9}    
20.         };    
21.         int[] diagonalSums=getDiagonalSums(matrix);    
22.         System.out.println("Sum of each diagonal:");    
23.         for (int sum:diagonalSums)  {    
24.             System.out.println(sum);    
25.         }    
26.     }    
27. }    

**Output:**

Sum of each diagonal:
1
6
15
14
9

**Complexity Analysis**

The approach has a time complexity of O(m*n), where m is the number of rows and n is the number of columns in the matrix.

The space complexity is O(m + n), as we must store the diagonal sums in an array.

### 15. Java program to find the element with the maximum frequency in an array.

We use a HashMap to record the frequency of each element in the array to locate the element with the highest frequency. The element with the highest frequency can be recognized via looping through the array and updating the frequency within the hash map. Then, by comparing the frequency counts in the HashMap, we identify the element with the maximum frequency. The approach allows us to efficiently find the element with the highest frequency in the array.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.*;  
2. public class Main {  
3.     public static int findMaxFrequencyElement(int[] nums) {  
4.         Map<Integer, Integer> frequencyMap = new HashMap<>();  
5.         for (int num : nums) {  
6.             frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);  
7.         }  
8.         return Collections.max(frequencyMap.entrySet(), Map.Entry.comparingByValue()).getKey();  
9.     }  
10.     public static void main(String[] args) {  
11.         int[] nums = {1, 2, 3, 2, 1, 2, 3, 3, 3};  
12.         System.out.println("Element with maximum frequency is: " + findMaxFrequencyElement(nums));  
13.     }  
14. }  

**Output:**

Element with maximum frequency is: 3

**Complexity Analysis**

The time complexity of this technique is O(n), where n is the size of the array.

The area complexity is O(n) because a HashMap can save up to n unique elements in the worst case.

### 16. Java program to rotate a two-dimensional array clockwise.

To rotate a two-dimensional array clockwise, we can follow a two-step approach: transposing the array and reversing each row. First, we iterate via the array and switch each detail at function (i, j) with the detail at the role (j, i), then successfully transpose the array. After, we iterate through each row of the transposed array and reverse it by swapping the elements from the start and end of the row until they meet in the middle. The process rotates the array clockwise.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main  {    
2.     public static void rotateClockwise(int[][] matrix)  {    
3.         int rows=matrix.length;    
4.         int cols=matrix[0].length;    
5.         // Transpose the array    
6.         for (int i=0;i<rows;i++)    {    
7.             for (int j=i;j<cols;j++)   {    
8.                 int temp=matrix[i][j];    
9.                 matrix[i][j]=matrix[j][i];    
10.                 matrix[j][i]=temp;    
11.             }    
12.         }    
13.         // Reverse each row    
14.         for (int i=0;i<rows;i++)   {    
15.             int left=0;    
16.             int right=cols-1;    
17.             while (left<right)    {    
18.                 int temp=matrix[i][left];    
19.                 matrix[i][left]=matrix[i][right];    
20.                 matrix[i][right]=temp;    
21.                 left++;    
22.                 right--;    
23.             }    
24.         }    
25.     }    
26.     public static void main(String[] args) {    
27.         int[][] matrix = {    
28.             {1, 2, 3},    
29.             {4, 5, 6},    
30.             {7, 8, 9}    
31.         };    
32.         System.out.println("Original Matrix:");    
33.         printMatrix(matrix);    
34.         rotateClockwise(matrix);    
35.         System.out.println("Rotated Matrix:");    
36.         printMatrix(matrix);    
37.     }    
38.     public static void printMatrix(int[][] matrix) {    
39.         int rows=matrix.length;    
40.         int cols=matrix[0].length;    
41.         for (int i=0;i<rows;i++)   {    
42.             for (int j=0;j<cols;j++)       {    
43.                 System.out.print(matrix[i][j]+" ");    
44.             }    
45.             System.out.println();    
46.         }    
47.         System.out.println();    
48.     }    
49. }   

**Output:**

Original Matrix:
1 2 3
4 5 6
7 8 9

Rotated Matrix:
7 4 1
8 5 2
9 6 3

**Complexity Analysis**

The time complexity of this approach is O(n2), where n is the size of the array.

The space complexity is O(1) as we carry out the rotation in-place without using any additional storage systems.

### 17. Java program to sort a two-dimensional array across columns.

We construct a custom comparator that compares rows based on the required column to sort a two-dimensional array across columns. The Arrays.sort() method is called with the custom comparator as an argument. The sorting algorithm employs a comparator to compare rows according to the selected column and arrange them correctly. We can quickly sort the two-dimensional array across columns using this method.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.Arrays;    
2. import java.util.Comparator;    
3. public class Main {    
4.     public static void sortByColumn(int[][] matrix, int column) {    
5.         // Use Arrays.sort() with a custom comparator to sort the matrix by the specified column    
6.         Arrays.sort(matrix,Comparator.comparingInt(row -> row[column]));    
7.     }    
8.     public static void main(String[] args) {    
9.         int[][] matrix = {    
10.             {13, 12, 11},    
11.             {6, 5, 4},    
12.             {19, 18, 17}    
13.         };    
14.         int columnToSortBy=1;    
15.         System.out.println("Original Matrix:");    
16.         printMatrix(matrix);    
17.         sortByColumn(matrix,columnToSortBy);    
18.         System.out.println("Sorted Matrix by Column " + columnToSortBy + ":");    
19.         printMatrix(matrix);    
20.     }    
21.     public static void printMatrix(int[][] matrix) {    
22.         int rows=matrix.length;    
23.         int cols=matrix[0].length;    
24.         for (int i=0;i<rows;i++)   {    
25.             for (int j=0;j<cols;j++)   {    
26.                 System.out.print(matrix[i][j]+" ");    
27.             }    
28.             System.out.println();    
29.         }    
30.         System.out.println();    
31.     }    
32. }    

**Output:**

Original Matrix:
13 12 11
6 5 4
19 18 17

Sorted Matrix by Column 1:
6 5 4
13 12 11
19 18 17

**Complexity Analysis**

The time complexity of this approach is O(n log n), where n is the number of rows in the matrix.

The space complexity is O(1) since the sorting is done in place.

### 18. Java program to perform matrix exponentiation to compute Fibonacci numbers efficiently.

We might also describe the Fibonacci sequence as a matrix and calculate matrix multiplication to compute the Fibonacci numbers using matrix exponentiation speedily. The manner includes creating a transformation matrix that represents the Fibonacci series, utilizing matrix multiplication and exponentiation strategies, and then elevating the matrix to the necessary power using the powerMatrix approach. By deleting the Fibonacci number from the following matrix, we can also quickly calculate Fibonacci numbers.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {    
2.     public static long computeFibonacci(int n)   {    
3.         if (n<=0)   {    
4.             return 0;    
5.         }    
6.         // Fibonacci transformation matrix    
7.         long[][] fibMatrix = {{1, 1}, {1, 0}};    
8.         // Raise fibMatrix to the power of (n-1)    
9.         fibMatrix = powerMatrix(fibMatrix, n - 1);    
10.         // Extract the Fibonacci number from the matrix    
11.         return fibMatrix[0][0];    
12.     }    
13.     private static long[][] powerMatrix(long[][] matrix, int power) {    
14.         if (power == 0) {    
15.             // Identity matrix    
16.             return new long[][]{{1, 0}, {0, 1}};    
17.         }    
18.         if (power == 1) {    
19.             return matrix;    
20.         }    
21.         long[][] result = powerMatrix(matrix, power / 2);    
22.         result = multiplyMatrices(result, result);    
23.         if (power % 2 != 0) {    
24.             result = multiplyMatrices(result, matrix);    
25.         }    
26.         return result;    
27.     }    
28.     private static long[][] multiplyMatrices(long[][] matrix1,long[][] matrix2)    {    
29.         long[][] result=new long[2][2];    
30.         result[0][0]=matrix1[0][0]*matrix2[0][0]+matrix1[0][1]*matrix2[1][0];    
31.         result[0][1]=matrix1[0][0]*matrix2[0][1]+matrix1[0][1]*matrix2[1][1];    
32.         result[1][0]=matrix1[1][0]*matrix2[0][0]+matrix1[1][1]*matrix2[1][0];    
33.         result[1][1]=matrix1[1][0]*matrix2[0][1]+matrix1[1][1]*matrix2[1][1];    
34.         return result;    
35.     }    
36.     public static void main(String[] args)    {    
37.         int n=10;    
38.         long fibonacci=computeFibonacci(n);    
39.         System.out.println("Fibonacci number at position "+n+" is: "+fibonacci);    
40.     }    
41. }    

**Output:**

Fibonacci number at position 10 is: 55

**Complexity Analysis**

The time complexity of this approach is O(log n) since we perform matrix multiplication using the exponentiation by squaring technique.

The space complexity is O(1) since we only need a fixed-size matrix and a few additional variables.

### 19. Given an array of integers, rearrange the array such that all even numbers appear before all odd numbers.

#### Note: Maintaining the relative order is not relevant for this problem.

We can use a two-pointer technique to reorder an array so that all even numbers appear before all odd numbers. While the right pointer begins at the end and advances backwards, the left pointer moves ahead from the beginning. The elements pointed by the left and right pointers are examined at each step, and swaps are made as needed. All even numbers will be arranged before odd numbers by the time the loop is complete.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main     
2. {    
3.     public static void rearrangeArray(int[] arr)     
4.     {    
5.         int left=0;    
6.         int right=arr.length-1;    
7.         while (left<=right)   {    
8.             if (arr[left]%2==0)    {    
9.                 left++; // Move the left pointer forward if the element is even    
10.             } else if (arr[right]%2==1)   {    
11.                 right--; // Move the right pointer backwards if the element is odd    
12.             } else {    
13.     swap(arr,left,right); // Swap the elements if the left element is odd and the right element is even    
14.                 left++; // Move the left pointer forward    
15.                 right--; // Move the right pointer backwards    
16.             }    
17.         }    
18.     }    
19.     public static void swap(int[] arr,int i,int j)   {    
20.         int temp=arr[i];    
21.         arr[i]=arr[j];    
22.         arr[j]=temp;    
23.     }    
24.     public static void main(String[] args)    {    
25.         int[] arr = {1,2,3,4,5,6,7,8,9};    
26.         System.out.println("Original Array: ");    
27.         printArray(arr);    
28.         rearrangeArray(arr);    
29.         System.out.println("Rearranged Array: ");    
30.         printArray(arr);    
31.     }    
32.     public static void printArray(int[] arr)   {    
33.         for (int num:arr)   {    
34.             System.out.print(num+" ");    
35.         }    
36.         System.out.println();    
37.     }    
38. }    

**Output:**

Original Array:
1 2 3 4 5 6 7 8 9
Rearranged Array:
8 2 6 4 5 3 7 1 9

**Complexity Analysis**

The time complexity of this approach is O(n), where n is the number of elements in the array.

The space complexity is O(1) as we perform the rearrangement in place without using any additional data structures.

### 20. Java program to find the smallest missing positive number in an unsorted array.

We can rearrange the array by assigning each positive integer to its appropriate index to discover the smallest missing positive number in an unsorted array. You can accomplish this by looping through the array and switching each element with a positive integer with the one at the desired index. The array is iterated once more to locate the first index where an element no longer corresponds to the required value after the rearrangement. The index corresponds to the smallest missing positive number. If all elements match their desired values, the smallest missing positive number is the next positive integer after the array size.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main    
2. {    
3.     public static int findSmallestMissingPositive(int[] nums)    
4.     {    
5.         int n=nums.length;    
6.         // Rearrange the array    
7.         for (int i=0;i<n;i++)     
8.         {    
9.             while (nums[i]>0&&nums[i]<=n&&nums[nums[i]-1]!=nums[i])     
10.             {    
11.                 swap(nums,i,nums[i]-1);    
12.             }    
13.         }    
14.         //Find the smallest missing positive number    
15.         for (int i=0;i<n;i++)     
16.         {    
17.             if (nums[i]!=i+1)     
18.             {    
19.                 return i+1;    
20.             }    
21.         }    
22.         // If all elements match their desired values, return the next positive integer    
23.         return n+1;    
24.     }    
25.     public static void swap(int[] nums,int i,int j)     
26.     {    
27.         int temp=nums[i];    
28.         nums[i]=nums[j];    
29.         nums[j]=temp;    
30.     }    
31.     public static void main(String[] args)     
32.     {    
33.         int[] nums={3,4,-1,1};    
34.         int smallestMissingPositive = findSmallestMissingPositive(nums);    
35.         System.out.println("Smallest Missing Positive Number: "+smallestMissingPositive);    
36.     }    
37. }   

**Output:**

Smallest Missing Positive Number: 2

**Complexity Analysis**

The approach ensures a time complexity of O(n) and a space complexity of O(1) as we perform the rearrangement and search in place without additional data structures.

### 21. Java program to find the intersection of two arrays.

The best approach to finding the intersection of two arrays is to use a HashSet data structure. We create a HashSet and add all elements from one array to it. Then, we iterate through the second array and check if each element exists in the HashSet. If it does, we add it to the result ArrayList and remove it from the HashSet to avoid duplicates.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.ArrayList;    
2. import java.util.HashSet;    
3. import java.util.List;    
4. public class Main{    
5.     public static List<Integer> intersection(int[] nums1, int[] nums2) {    
6.         HashSet<Integer> set=new HashSet<>();    
7.         List<Integer> result=new ArrayList<>();    
8.         // Add elements of nums1 to the set    
9.         for (int num:nums1)  {    
10.             set.add(num);    
11.         }    
12.         // Check for intersection in nums2    
13.         for (int num:nums2)   {    
14.             if (set.contains(num))   {    
15.                 result.add(num);    
16.                 set.remove(num);    
17.             }    
18.         }    
19.         return result;    
20.     }    
21.     public static void main(String[] args) {    
22.         int[] nums1 = {1, 2, 2, 1};    
23.         int[] nums2 = {2, 2};    
24.         List<Integer> intersection=intersection(nums1, nums2);    
25.         System.out.println("Intersection: "+intersection);    
26.     }    
27. }    

**Output:**

Intersection: [2]

**Complexity Analysis**

The time complexity of this approach is O(n), where n is the size of the larger array.

The space complexity is O(m), where m is the size of the HashSet.

### 22. Java program to find the longest subarray with an equal number of 0s and 1s.

Utilizing the prefix sum method, we can determine the longest subarray that contains an equal number of 0s and 1s. We can calculate the running sum while traversing the array by assigning a value of 1 for every 1 and -1 for every 0. When the running sum reaches zero, the number of 0s and 1s we have seen thus far is equal. To find the longest subarray, we store the running sum in a HashMap and its corresponding index. If the same running sum appears again, we update the maximum length by subtracting the stored index from the current index. By keeping track of the maximum length throughout the iteration, we can find the longest subarray with equal 0s and 1s.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.HashMap;    
2. public class Main {    
3.     public static int findMaxLength(int[] nums)   {    
4.         int maxLength=0;    
5.         int runningSum=0;    
6.         HashMap<Integer,Integer> sumMap=new HashMap<>();    
7.         sumMap.put(0,-1); // Handle the case when the subarray starts from the beginning    
8.         for (int i=0;i<nums.length;i++)   {    
9.             runningSum+=nums[i]==0?-1:1;    
10.             if (sumMap.containsKey(runningSum))    {    
11.                 int startIndex=sumMap.get(runningSum);    
12.                 maxLength=Math.max(maxLength,i-startIndex);    
13.             } else {    
14.                 sumMap.put(runningSum,i);    
15.             }    
16.         }    
17.         return maxLength;    
18.     }    
19.     public static void main(String[] args)    {    
20.         int[] nums = {0, 1, 0, 0, 1, 1, 0};    
21.         int maxLength=findMaxLength(nums);    
22.   System.out.println("Length of the longest subarray with equal 0s and 1s is: "+maxLength);    
23.     }    
24. }    

**Output:**

Length of the longest subarray with equal 0s and 1s: 6

**Complexity Analysis**

The time complexity of this approach is O(n) since we iterate through the array once.

The space complexity is O(n) as we store the running sum and its corresponding index in the HashMap.

### 23. Java program to find the maximum product of two integers in an array.

To find the maximum product of two integers in an array, we iterate through the array and keep track of the maximum and second maximum elements. We initialize max1 and max2 to the smallest possible integer values. Then, for each element, we compare it with max1 and update max2 and max1 accordingly. After iterating through the array, the maximum product is the product of max1 and max2, as max1 will hold the largest element and max2 will hold the second largest element.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {    
2.     public static int findMaximumProduct(int[] arr)  {    
3.       int max1=Integer.MIN_VALUE; // Initialize the maximum element to the smallest possible value    
4.         int max2=Integer.MIN_VALUE; // Initialize the second maximum element to the smallest possible value    
5.         for (int num:arr)    {    
6.             if (num>max1)    {    
7.                 max2=max1; // Update the second maximum element    
8.                 max1=num; // Update the maximum element    
9.             }     
10.             else if (num>max2)    {    
11.                 max2=num; // Update the second maximum element    
12.             }    
13.         }    
14.         return max1*max2; // Return the maximum product    
15.     }    
16.     public static void main(String[] args)    {    
17.         int[] arr={1,2,3,4,5};    
18.         int maximumProduct=findMaximumProduct(arr);    
19.         System.out.println("Maximum Product: "+maximumProduct);    
20.     }    
21. }    

**Output:**

Maximum Product: 20

**Complexity Analysis**

The time complexity of this approach is O(n), where n is the size of the array.

The space complexity is O(1) since we only use constant extra space to store the maximum and second maximum elements.

### 24. Java program to find the smallest subarray length with a sum greater than a given value.

To find the smallest subarray length with a sum greater than a given value, we can utilize the sliding window technique. The approach involves maintaining a window that expands and contracts while calculating the current sum. We start with an empty window and gradually expand it by adding elements from the right end. If the current sum exceeds the given value, we update the minimum length of the subarray. Then, until the current total is less than or equal to the specified value, we contract the window from the left end by eliminating items. Until we reach the end of the array, we keep doing this.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main{    
2.     public static int findSmallestSubarray(int[] arr,int target)   {    
3.         int minLength=Integer.MAX_VALUE; // Variable to store the minimum length of the subarray    
4.         int currentSum=0; // Variable to track the current sum of the subarray    
5.         int left=0; // Left pointer to mark the start of the subarray    
6.         int right=0; // Right pointer to mark the end of the subarray    
7.         while (right<arr.length) {    
8.         currentSum+=arr[right]; // Add the element at the right pointer to the current sum            while (currentSum>target)   {    
9.   minLength=Math.min(minLength,rightleft+1); // Update the minimum length if necessary    
10.     currentSum=arr[left]; // Subtract the element at the left pointer from the current sum  
11.                 left++; // Move the left pointer to the right to contract the window    
12.             }    
13.             right++; // Move the right pointer to the right to expand the window    
14.         }    
15.         return (minLength==Integer.MAX_VALUE)?-1:minLength;     
16.     }    
17.     public static void main(String[] args)   {    
18.         int[] arr={1, 4, 45, 6, 0, 19};    
19.         int target=51;    
20.         int smallestSubarrayLength=findSmallestSubarray(arr,target);    
21.         System.out.println("Smallest Subarray Length: "+smallestSubarrayLength);    
22.     }    
23. }    

**Output:**

Smallest Subarray Length: 3

**Complexity Analysis**

The time complexity of this approach is O(n), where n is the size of the array.

The space complexity is O(1) since we only use constant extra space to store variables.

### 25. Java program to find the triplet with the smallest sum in an array.

We can take the help of three variables (an integer array of size three will also do the work), and using a loop, we can find the minimum elements present in the given array. We will be looking for the minimum elements as we have to find the smallest sum.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main   {    
2. public static void findSmallestTripletSum(int[] arr)  {    
3. int n = arr.length; // finding the size    
4. // for storing the first three minimum values present in the given array.    
5. int fMin = Integer.MAX_VALUE;    
6. int sMin = Integer.MAX_VALUE;    
7. int tMin = Integer.MAX_VALUE;     
8. for (int i = 0; i < n; i++)   {     
9. // getting the first, second and third minimum elements     
10. if (arr[i] < fMin)   {     
11.     tMin = sMin;     
12.     sMin = fMin;     
13.     fMin = arr[i];     
14. }     
15. // updating the second and third minimum elements     
16. else if (arr[i] < sMin)   {     
17.     tMin = sMin;     
18.     sMin = arr[i];     
19. }     
20. else if (arr[i] < tMin)   {     
21.     tMin = arr[i];     
22. }     
23. }    
24. // print statement    
25. System.out.println("The Triplet with the smallest sum is: {"+ fMin + ", " + sMin + ", " + tMin + "}");    
26. }    
27. // main method    
28. public static void main(String[] args)   {    
29. int[] arr = {5, 1, -3, -4, -2, 6};    
30. findSmallestTripletSum(arr);    
31. }    
32. }    

**Output:**

The Triplet with the smallest sum is: {-4, -3, -2}

**Complexity Analysis**

The time complexity of this approach is O(n) since we are only using one loop in the program.

The space complexity is O(1), as we are not using any extra space that grows with the input size.

### 26. Java program to increment all elements of an array by one.

The input array is defined as {1, 2, 3, 4, 5}. The method incrementArrayElements(int[] array) accepts an array as an argument. It then uses a for loop to iterate over each element in the array. Increment Operation: Inside the loop, the code array[i]++ increments each element by one. The final output is printed in the main() method, where the incremented array elements are displayed.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         int[] array = {1, 2, 3, 4, 5};    
4.         incrementArrayElements(array);    
5.         // Print the incremented array    
6.         for (int i = 0; i < array.length; i++) {    
7.             System.out.print(array[i] + " ");    
8.         }    
9.     }    
10.     public static void incrementArrayElements(int[] array) {    
11.         for (int i = 0; i < array.length; i++) {    
12.             array[i]++;    
13.         }    
14.     }    
15. }   

**Output:**

2 3 4 5 6

### 27. Java program to move all zeroes to the end of the array.

For this approach, we traverse the array twice. In the first traversal, we do the following:

- Iterate through the array while counting non-zero elements. Initialize the count at 0, which also indicates the position for the next non-zero element in the array.
- For each non-zero element, position it at arr[count] and then increase the count by 1.
- Once all elements have been processed, all non-zero entries will be moved to the front, keeping their original sequence.

In the second traversal, we do the following:

- Following the initial traversal, all non-zero elements will occupy the beginning of the array, while the variable 'count' will indicate the position for the first zero.
- Proceed from 'count' to the end of the array, filling all subsequent indices with 0.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         int[] arr = {1, 0, 2, 0, 3, 0, 4, 0};  
4.         int n = arr.length;  //finding array length  
5.         int count = 0;  
6.         for (int i = 0; i < n; i++) { //loop iterate over the array  
7.             if (arr[i] != 0) {  //compare if the array element is equals to zero or not  
8.                 arr[count++] = arr[i];  //  
9.             }  
10.         }  
11.         while (count < n) {  
12.             arr[count++] = 0;  
13.         }  
14.         System.out.println("Array after moving zeroes: " + java.util.Arrays.toString(arr));  
15.     }  
16. }  

**Output:**

Array after moving zeroes: [1, 2, 3, 4, 0, 0, 0, 0]

### 28. Reverse an array without changing the position of zeroes.

To solve the problem, the method involves moving through the array from both ends and swapping non-zero elements until reaching the centre. Throughout this procedure, the positions of zeroes are left intact. The code employs a while loop to bypass zeroes while decrementing the index from the end. When a non-zero element is detected, it gets swapped with the corresponding non-zero element from the opposite end. This swapping continues until the centre of the array is reached.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3. // Print function  
4. public static void printReverse(int[] arr) {  
5.     // Print the original array  
6.     System.out.print("Original array: ");  
7.     System.out.println(Arrays.toString(arr));  
8.     // Reverse the array without changing the position of zeroes  
9.     // Initialize the index to the last element  
10.     int j = arr.length - 1;  
11.     for (int i = 0; i < j; i++) {  
12.     // If the current element is zero, skip to the next element  
13.     if (arr[i] == 0) {  
14.         continue;  
15.     }  
16.     // If the current element is zero from the end  
17.     while (j > i && arr[j] == 0) {  
18.         // Decrement the index to the previous element  
19.         j--;  
20.     }  
21.     // Swap the elements  
22.     int temp = arr[i];  
23.     arr[i] = arr[j];  
24.     arr[j] = temp;  
25.     // Decrement the index to the previous element  
26.     j--;  
27.     }  
28.     // Prints the reversed array  
29.     System.out.print("Reversed array: ");  
30.     System.out.println(Arrays.toString(arr));  
31. }  
32. public static void main(String[] args) {  
33.     int[] arr = { 6, 0, 8, 0, 2, 0, 1 };  
34.     printReverse(arr);  
35. }  
36. }  

**Output:**

Original array: [6, 0, 8, 0, 2, 0, 1]
Reversed array: [1, 0, 2, 0, 8, 0, 6]

### 29. Java program to find the leader element in an array.

Given an array **arr[]** of size **n**, the task is to find all the Leaders in the array. An element is a Leader if it is greater than or equal to all the elements to its right side.

#### Note: The rightmost element is always a leader.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         int[] arr = {12, 11, 4, 7, 9, 6, 8, 15};  
4.         int n = arr.length;  
5.         int maxFromRight = arr[n - 1];  
6.         System.out.print("Leader is: " + maxFromRight + " ");  
7.         for (int i = n - 2; i >= 0; i--) {  
8.             if (arr[i] > maxFromRight) {  
9.                 maxFromRight = arr[i];  
10.                 System.out.print(maxFromRight + " ");  
11.             }  
12.         }  
13.     }  
14. }  

**Output:**

Leader is: 15

### 30. Java program to find all the non-empty subarrays.

To create a subarray, we first need a starting index from the original array. We can choose this starting index by looping through the range [0 to n-1] and treating each index i as a potential starting point. For each selected starting index i, we then determine an ending index from the range [i to n-1]. A nested loop, running from [i to n-1], will assist in selecting the ending index. Once both the starting and ending indices are established, an innermost loop will be required to print the elements of the subarray.

#### Code

[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)[](https://www.tpointtech.com/array-programs-in-java#)

1. import java.util.ArrayList;  
2. public class Main {  
3.     //Prints all subarrays in arr[0..n-1]  
4.     static void findSubArray(ArrayList<Integer> arr) {  
5.         int n = arr.size();  
6.         // Pick starting point  
7.         for (int i = 0; i < n; i++) {           
8.             // Pick ending point  
9.             for (int j = i; j < n; j++) {               
10.                 // Print subarray between current starting and ending points  
11.                 for (int k = i; k <= j; k++) {  
12.                     System.out.print(arr.get(k) + " ");  
13.                 }  
14.                 System.out.println();  
15.             }  
16.         }  
17.     }  
18.     public static void main(String[] args) {  
19.         ArrayList<Integer> arr = new ArrayList<>();  
20.         arr.add(1);  
21.         arr.add(2);  
22.         arr.add(3);  
23.         System.out.println("Subarrays are:");  
24.         findSubArray(arr);  
25.     }  
26. }  

**Output:**

Subarrays are:
1
1 2
1 2 3
2
2 3
3