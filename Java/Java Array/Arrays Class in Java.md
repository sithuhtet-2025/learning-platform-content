In [Java](https://www.tpointtech.com/java-tutorial), the **Arrays class** is a utility class that is a member of the [Java collection framework](https://www.tpointtech.com/collections-in-java). It belongs to **java.util** package. The class provides various static methods for manipulating arrays efficiently. It simplifies common operations (like searching, sorting, copying and comparison) on the arrays.

To read more [Java Arrays](https://www.tpointtech.com/java-arrays)

## Why Use the Java Arrays Class?

The main reason for using the Java Arrays class is that it provides ready-made methods for complex logic. Here are some reasons why developers use it often.

1. **Convenience:** The Arrays class is convenience for array manipulation because it provides various ready-made static methods to perform complex logic. It eliminates the need to write complex code for array operations.
2. **Efficiency:** Methods in this class provide highly optimized algorithms (Dual-Pivot Quicksort for primitives and TimSort for objects). It offers better performance that increases efficiency.
3. **Readability:** The methods of the Arrays class follow intuitive names (names that are easy to pronounce, spell, and understand, often having a straightforward and familiar sound) and behaviors that make code easier to read, understand, and maintain.
4. **Streamlining Code:** By using the Arrays class, the code becomes cleaner and more concise. We can use the Arrays.toString() method to convert arrays into a String instead of writing a loop.
5. **Enhanced Functionality:** The class provides advance capabilities like deep comparison by using the Arrays.deepEquals() method, filling arrays efficiently by using the Arrays,fill() method, and working with streams by using the Arrays.stream() method.
6. **Collection Compatibility:** The class allows seamless conversion of arrays to lists, which makes it easier to work with the collection framework.

## Java Arrays Class Methods

There are several Arrays Class Methods in Java. Here, we are going to discuss one by one.

### 1. Sorting Methods

The following table lists all sorting related methods of Array class:

|Method Signature|Description|
|---|---|
|sort(byte[] a)|Sorts the specified array into ascending numerical order.|
|sort(byte[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(char[] a)|Sorts the specified array into ascending numerical order.|
|sort(char[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(double[] a)|Sorts the specified array into ascending numerical order.|
|sort(double[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(float[] a)|Sorts the specified array into ascending numerical order.|
|sort(float[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(int[] a)|Sorts the specified array into ascending numerical order.|
|sort(int[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(long[] a)|Sorts the specified array into ascending numerical order.|
|sort(long[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(short[] a)|Sorts the specified array into ascending numerical order.|
|sort(short[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending order.|
|sort(Object[] a)|Sorts the specified array of objects into ascending order, according to the natural ordering of its elements.|
|sort(Object[] a, int fromIndex, int toIndex)|Sorts the specified range of the specified array of objects into ascending order, according to the natural ordering of its elements.|
|sort(T[] a, int fromIndex, int toIndex, Comparator<? super T> c)|Sorts the specified range of the specified array of objects according to the order induced by the specified comparator.|
|sort(T[] a, Comparator<? super T> c)|Sorts the specified array of objects according to the order induced by the specified comparator.|

### 2. Searching Methods

The following table lists all searching related methods of Array class:

|Method Signature|Description|
|---|---|
|binarySearch(byte[] a, byte key)|Searches the specified array of bytes for the specified value using the binary search algorithm.|
|binarySearch(byte[] a, int fromIndex, int toIndex, byte key)|Searches a range of the specified array of bytes for the specified value using the binary search algorithm.|
|binarySearch(char[] a, char key)|Searches the specified array of chars for the specified value using the binary search algorithm.|
|binarySearch(char[] a, int fromIndex, int toIndex, char key)|Searches a range of the specified array of chars for the specified value using the binary search algorithm.|
|binarySearch(double[] a, double key)|Searches the specified array of doubles for the specified value using the binary search algorithm.|
|binarySearch(double[] a, int fromIndex, int toIndex, double key)|Searches a range of the specified array of doubles for the specified value using the binary search algorithm.|
|binarySearch(float[] a, float key)|Searches the specified array of floats for the specified value using the binary search algorithm.|
|binarySearch(float[] a, int fromIndex, int toIndex, float key)|Searches a range of the specified array of floats for the specified value using the binary search algorithm.|
|binarySearch(int[] a, int key)|Searches the specified array of ints for the specified value using the binary search algorithm.|
|binarySearch(int[] a, int fromIndex, int toIndex, int key)|Searches a range of the specified array of ints for the specified value using the binary search algorithm.|
|binarySearch(long[] a, int fromIndex, int toIndex, long key)|Searches a range of the specified array of longs for the specified value using the binary search algorithm.|
|binarySearch(long[] a, long key)|Searches the specified array of longs for the specified value using the binary search algorithm.|
|binarySearch(short[] a, int fromIndex, int toIndex, short key)|Searches a range of the specified array of shorts for the specified value using the binary search algorithm.|
|binarySearch(short[] a, short key)|Searches the specified array of shorts for the specified value using the binary search algorithm.|
|binarySearch(Object[] a, int fromIndex, int toIndex, Object key)|Searches a range of the specified array for the specified object using the binary search algorithm.|
|binarySearch(Object[] a, Object key)|Searches the specified array for the specified object using the binary search algorithm.|
|binarySearch(T[] a, int fromIndex, int toIndex, T key, Comparator<? super T> c)|Searches a range of the specified array for the specified object using the binary search algorithm.|
|binarySearch(T[] a, T key, Comparator<? super T> c)|Searches the specified array for the specified object using the binary search algorithm.|

### 3. Comparison Methods

The following table lists all comparison related methods of Array class:

|Method Signature|Description|
|---|---|
|deepEquals(Object[] a1, Object[] a2)|Returns true if the two specified arrays are deeply equal to one another.|
|deepHashCode(Object[] a)|Returns a hash code based on the "deep contents" of the specified array.|
|deepToString(Object[] a)|Returns a string representation of the "deep contents" of the specified array.|
|equals(boolean[] a, boolean[] a2)|Returns true if the two specified arrays of booleans are equal to one another.|
|equals(boolean[] a, int aFromIndex, int aToIndex, boolean[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of booleans, over the specified ranges, are equal to one another.|
|equals(byte[] a, byte[] a2)|Returns true if the two specified arrays of bytes are equal to one another.|
|equals(byte[] a, int aFromIndex, int aToIndex, byte[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of bytes, over the specified ranges, are equal to one another.|
|equals(char[] a, char[] a2)|Returns true if the two specified arrays of chars are equal to one another.|
|equals(char[] a, int aFromIndex, int aToIndex, char[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of chars, over the specified ranges, are equal to one another.|
|equals(double[] a, double[] a2)|Returns true if the two specified arrays of doubles are equal to one another.|
|equals(double[] a, int aFromIndex, int aToIndex, double[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of doubles, over the specified ranges, are equal to one another.|
|equals(float[] a, float[] a2)|Returns true if the two specified arrays of floats are equal to one another.|
|equals(float[] a, int aFromIndex, int aToIndex, float[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of floats, over the specified ranges, are equal to one another.|
|equals(int[] a, int[] a2)|Returns true if the two specified arrays of ints are equal to one another.|
|equals(int[] a, int aFromIndex, int aToIndex, int[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of ints, over the specified ranges, are equal to one another.|
|equals(long[] a, int aFromIndex, int aToIndex, long[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of longs, over the specified ranges, are equal to one another.|
|equals(long[] a, long[] a2)|Returns true if the two specified arrays of longs are equal to one another.|
|equals(short[] a, int aFromIndex, int aToIndex, short[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of shorts, over the specified ranges, are equal to one another.|
|equals(short[] a, short[] a2)|Returns true if the two specified arrays of shorts are equal to one another.|
|equals(Object[] a, int aFromIndex, int aToIndex, Object[] b, int bFromIndex, int bToIndex)|Returns true if the two specified arrays of Objects, over the specified ranges, are equal to one another.|
|equals(Object[] a, Object[] a2)|Returns true if the two specified arrays of Objects are equal to one another.|
|equals(T[] a, int aFromIndex, int aToIndex, T[] b, int bFromIndex, int bToIndex, Comparator<? super T> cmp)|Returns true if the two specified arrays of Objects, over the specified ranges, are equal to one another.|
|equals(T[] a, T[] a2, Comparator<? super T> cmp)|Returns true if the two specified arrays of Objects are equal to one another.|
|compare(boolean[] a, boolean[] b)|Compares two boolean arrays lexicographically.|
|compare(boolean[] a, int aFromIndex, int aToIndex, boolean[] b, int bFromIndex, int bToIndex)|Compares two boolean arrays lexicographically over the specified ranges.|
|compare(byte[] a, byte[] b)|Compares two byte arrays lexicographically.|
|compare(byte[] a, int aFromIndex, int aToIndex, byte[] b, int bFromIndex, int bToIndex)|Compares two byte arrays lexicographically over the specified ranges.|
|compare(char[] a, char[] b)|Compares two char arrays lexicographically.|
|compare(char[] a, int aFromIndex, int aToIndex, char[] b, int bFromIndex, int bToIndex)|Compares two char arrays lexicographically over the specified ranges.|
|compare(double[] a, double[] b)|Compares two double arrays lexicographically.|
|compare(double[] a, int aFromIndex, int aToIndex, double[] b, int bFromIndex, int bToIndex)|Compares two double arrays lexicographically over the specified ranges.|
|compare(float[] a, float[] b)|Compares two float arrays lexicographically.|
|compare(float[] a, int aFromIndex, int aToIndex, float[] b, int bFromIndex, int bToIndex)|Compares two float arrays lexicographically over the specified ranges.|
|compare(int[] a, int[] b)|Compares two int arrays lexicographically.|
|compare(int[] a, int aFromIndex, int aToIndex, int[] b, int bFromIndex, int bToIndex)|Compares two int arrays lexicographically over the specified ranges.|
|compare(long[] a, int aFromIndex, int aToIndex, long[] b, int bFromIndex, int bToIndex)|Compares two long arrays lexicographically over the specified ranges.|
|compare(long[] a, long[] b)|Compares two long arrays lexicographically.|
|compare(short[] a, int aFromIndex, int aToIndex, short[] b, int bFromIndex, int bToIndex)|Compares two short arrays lexicographically over the specified ranges.|
|compare(short[] a, short[] b)|Compares two short arrays lexicographically.|
|compare(T[] a, int aFromIndex, int aToIndex, T[] b, int bFromIndex, int bToIndex)|Compares two Object arrays lexicographically over the specified ranges.|
|compare(T[] a, int aFromIndex, int aToIndex, T[] b, int bFromIndex, int bToIndex, Comparator<? super T> cmp)|Compares two Object arrays lexicographically over the specified ranges.|
|compare(T[] a, T[] b)|Compares two Object arrays, within comparable elements, lexicographically.|
|compare(T[] a, T[] b, Comparator<? super T> cmp)|Compares two Object arrays lexicographically using a specified comparator.|
|compareUnsigned(byte[] a, byte[] b)|Compares two byte arrays lexicographically, numerically treating elements as unsigned.|
|compareUnsigned(byte[] a, int aFromIndex, int aToIndex, byte[] b, int bFromIndex, int bToIndex)|Compares two byte arrays lexicographically over the specified ranges, numerically treating elements as unsigned.|
|compareUnsigned(int[] a, int[] b)|Compares two int arrays lexicographically, numerically treating elements as unsigned.|
|compareUnsigned(int[] a, int aFromIndex, int aToIndex, int[] b, int bFromIndex, int bToIndex)|Compares two int arrays lexicographically over the specified ranges, numerically treating elements as unsigned.|
|compareUnsigned(long[] a, int aFromIndex, int aToIndex, long[] b, int bFromIndex, int bToIndex)|Compares two long arrays lexicographically over the specified ranges, numerically treating elements as unsigned.|
|compareUnsigned(long[] a, long[] b)|Compares two long arrays lexicographically, numerically treating elements as unsigned.|
|compareUnsigned(short[] a, int aFromIndex, int aToIndex, short[] b, int bFromIndex, int bToIndex)|Compares two short arrays lexicographically over the specified ranges, numerically treating elements as unsigned.|
|compareUnsigned(short[] a, short[] b)|Compares two short arrays lexicographically, numerically treating elements as unsigned.|

### 4. Copying Methods

The following table lists all copying related methods of Array class:

|Method Signature|Description|
|---|---|
|copyOf(boolean[] original, int newLength)|Copies the specified array, truncating or padding with false (if necessary) so the copy has the specified length.|
|copyOf(byte[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(char[] original, int newLength)|Copies the specified array, truncating or padding with null characters (if necessary) so the copy has the specified length.|
|copyOf(double[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(float[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(int[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(long[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(short[] original, int newLength)|Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length.|
|copyOf(T[] original, int newLength)|Copies the specified array, truncating or padding with nulls (if necessary) so the copy has the specified length.|
|copyOf(U[] original, int newLength, Class<? extends T[]> newType)|Copies the specified array, truncating or padding with nulls (if necessary) so the copy has the specified length.|
|copyOfRange(boolean[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(byte[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(char[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(double[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(float[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(int[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(long[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(short[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(T[] original, int from, int to)|Copies the specified range of the specified array into a new array.|
|copyOfRange(U[] original, int from, int to, Class<? extends T[]> newType)|Copies the specified range of the specified array into a new array.|

### 5. Fill Methods

The following table lists all fill related methods of Array class:

|Method Signature|Description|
|---|---|
|fill(boolean[] a, boolean val)|Assigns the specified boolean value to each element of the specified array of booleans.|
|fill(boolean[] a, int fromIndex, int toIndex, boolean val)|Assigns the specified boolean value to each element of the specified range of the specified array of booleans.|
|fill(byte[] a, byte val)|Assigns the specified byte value to each element of the specified array of bytes.|
|fill(byte[] a, int fromIndex, int toIndex, byte val)|Assigns the specified byte value to each element of the specified range of the specified array of bytes.|
|fill(char[] a, char val)|Assigns the specified char value to each element of the specified array of chars.|
|fill(char[] a, int fromIndex, int toIndex, char val)|Assigns the specified char value to each element of the specified range of the specified array of chars.|
|fill(double[] a, double val)|Assigns the specified double value to each element of the specified array of doubles.|
|fill(double[] a, int fromIndex, int toIndex, double val)|Assigns the specified double value to each element of the specified range of the specified array of doubles.|
|fill(float[] a, float val)|Assigns the specified float value to each element of the specified array of floats.|
|fill(float[] a, int fromIndex, int toIndex, float val)|Assigns the specified float value to each element of the specified range of the specified array of floats.|
|fill(int[] a, int val)|Assigns the specified int value to each element of the specified array of ints.|
|fill(int[] a, int fromIndex, int toIndex, int val)|Assigns the specified int value to each element of the specified range of the specified array of ints.|
|fill(long[] a, int fromIndex, int toIndex, long val)|Assigns the specified long value to each element of the specified range of the specified array of longs.|
|fill(long[] a, long val)|Assigns the specified long value to each element of the specified array of longs.|
|fill(short[] a, int fromIndex, int toIndex, short val)|Assigns the specified short value to each element of the specified range of the specified array of shorts.|
|fill(short[] a, short val)|Assigns the specified short value to each element of the specified array of shorts.|
|fill(Object[] a, int fromIndex, int toIndex, Object val)|Assigns the specified Object reference to each element of the specified range of the specified array of Objects.|
|fill(Object[] a, Object val)|Assigns the specified Object reference to each element of the specified array of Objects.|

### 6. Stream Methods

The following table lists all stream related methods of Array class:

|Method Signature|Description|
|---|---|
|stream(double[] array)|Returns a sequential DoubleStream with the specified array as its source.|
|stream(double[] array, int startInclusive, int endExclusive)|Returns a sequential DoubleStream with the specified range of the specified array as its source.|
|stream(int[] array)|Returns a sequential IntStream with the specified array as its source.|
|stream(int[] array, int startInclusive, int endExclusive)|Returns a sequential IntStream with the specified range of the specified array as its source.|
|stream(long[] array)|Returns a sequential LongStream with the specified array as its source.|
|stream(long[] array, int startInclusive, int endExclusive)|Returns a sequential LongStream with the specified range of the specified array as its source.|
|stream(T[] array)|Returns a sequential Stream with the specified array as its source.|
|stream(T[] array, int startInclusive, int endExclusive)|Returns a sequential Stream with the specified range of the specified array as its source.|

### 7. Conversion Methods

The following table lists all conversion related methods of Array class:

|Method Signature|Description|
|---|---|
|toString(boolean[] a)|Returns a string representation of the contents of the specified array.|
|toString(byte[] a)|Returns a string representation of the contents of the specified array.|
|toString(char[] a)|Returns a string representation of the contents of the specified array.|
|toString(double[] a)|Returns a string representation of the contents of the specified array.|
|toString(float[] a)|Returns a string representation of the contents of the specified array.|
|toString(int[] a)|Returns a string representation of the contents of the specified array.|
|toString(long[] a)|Returns a string representation of the contents of the specified array.|
|toString(short[] a)|Returns a string representation of the contents of the specified array.|
|toString(Object[] a)|Returns a string representation of the contents of the specified array.|
|asList(T... a)|Returns a fixed-size list backed by the specified array.|

### 8. Utility Methods

The following table lists all utility related methods of Array class:

|Method Signature|Description|
|---|---|
|hashCode(boolean[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(byte[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(char[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(double[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(float[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(int[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(long[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(short[] a)|Returns a hash code based on the contents of the specified array.|
|hashCode(Object[] a)|Returns a hash code based on the contents of the specified array.|
|mismatch(boolean[] a, boolean[] b)|Finds and returns the index of the first mismatch between two boolean arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(boolean[] a, int aFromIndex, int aToIndex, boolean[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two boolean arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(byte[] a, byte[] b)|Finds and returns the index of the first mismatch between two-byte arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(byte[] a, int aFromIndex, int aToIndex, byte[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two-byte arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(char[] a, char[] b)|Finds and returns the index of the first mismatch between two char arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(char[] a, int aFromIndex, int aToIndex, char[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two char arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(double[] a, double[] b)|Finds and returns the index of the first mismatch between two double arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(double[] a, int aFromIndex, int aToIndex, double[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two double arrays over the specified ranges; otherwise, returns -1 if no mismatch is found.|
|mismatch(float[] a, float[] b)|Finds and returns the index of the first mismatch between two float arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(float[] a, int aFromIndex, int aToIndex, float[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two float arrays over the specified ranges; otherwise, returns -1 if no mismatch is found.|
|mismatch(int[] a, int[] b)|Finds and returns the index of the first mismatch between two int arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(int[] a, int aFromIndex, int aToIndex, int[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two int arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(long[] a, int aFromIndex, int aToIndex, long[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two long arrays over the specified ranges; otherwise, returns -1 if no mismatch is found.|
|mismatch(long[] a, long[] b)|Finds and returns the index of the first mismatch between two long arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(short[] a, int aFromIndex, int aToIndex, short[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two short arrays over the specified ranges; otherwise, returns -1 if no mismatch is found.|
|mismatch(short[] a, short[] b)|Finds and returns the index of the first mismatch between two short arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(Object[] a, int aFromIndex, int aToIndex, Object[] b, int bFromIndex, int bToIndex)|Finds and returns the relative index of the first mismatch between two Object arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(Object[] a, Object[] b)|Finds and returns the index of the first mismatch between two Object arrays; otherwise, returns -1 if no mismatch is found.|
|mismatch(T[] a, int aFromIndex, int aToIndex, T[] b, int bFromIndex, int bToIndex, Comparator<? super T> cmp)|Finds and returns the relative index of the first mismatch between two Object arrays over the specified ranges, otherwise returns -1 if no mismatch is found.|
|mismatch(T[] a, T[] b, Comparator<? super T> cmp)|Finds and returns the index of the first mismatch between two Object arrays; otherwise, returns -1 if no mismatch is found.|

### 9. Parallel Array Methods

The following table lists all parallel array related methods of Array class:

|Method Signature|Description|
|---|---|
|parallelPrefix(double[] array, int fromIndex, int toIndex, DoubleBinaryOperator op)|Performs parallelPrefix(double[], DoubleBinaryOperator) for the given subrange of the array.|
|parallelPrefix(double[] array, DoubleBinaryOperator op)|Cumulates, in parallel, each element of the given array in place, using the supplied function.|
|parallelPrefix(int[] array, int fromIndex, int toIndex, IntBinaryOperator op)|Performs parallelPrefix(int[], IntBinaryOperator) for the given subrange of the array.|
|parallelPrefix(int[] array, IntBinaryOperator op)|Cumulates, in parallel, each element of the given array in place, using the supplied function.|
|parallelPrefix(long[] array, int fromIndex, int toIndex, LongBinaryOperator op)|Performs parallelPrefix(long[], LongBinaryOperator) for the given subrange of the array.|
|parallelPrefix(long[] array, LongBinaryOperator op)|Cumulates, in parallel, each element of the given array in place, using the supplied function.|
|parallelPrefix(T[] array, int fromIndex, int toIndex, BinaryOperator<T> op)|Performs parallelPrefix(Object[], BinaryOperator) for the given subrange of the array.|
|parallelPrefix(T[] array, BinaryOperator<T> op)|Cumulates, in parallel, each element of the given array in place, using the supplied function.|
|parallelSetAll(double[] array, IntToDoubleFunction generator)|Set all elements of the specified array, in parallel, using the provided generator function to compute each element.|
|parallelSetAll(int[] array, IntUnaryOperator generator)|Set all elements of the specified array, in parallel, using the provided generator function to compute each element.|
|parallelSetAll(long[] array, IntToLongFunction generator)|Set all elements of the specified array, in parallel, using the provided generator function to compute each element.|
|parallelSetAll(T[] array, IntFunction<? extends T> generator)|Set all elements of the specified array, in parallel, using the provided generator function to compute each element.|
|parallelSort(byte[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(byte[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(char[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(char[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(double[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(double[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(float[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(float[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(int[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(int[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(long[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(long[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(short[] a)|Sorts the specified array into ascending numerical order.|
|parallelSort(short[] a, int fromIndex, int toIndex)|Sorts the specified range of the array into ascending numerical order.|
|parallelSort(T[] a)|Sorts the specified array of objects into ascending order, according to the natural ordering of its elements.|
|parallelSort(T[] a, int fromIndex, int toIndex)|Sorts the specified range of the specified array of objects into ascending order, according to the natural ordering of its elements.|
|parallelSort(T[] a, int fromIndex, int toIndex, Comparator<? super T> cmp)|Sorts the specified range of the specified array of objects according to the order induced by the specified comparator.|
|parallelSort(T[] a, Comparator<? super T> cmp)|Sorts the specified array of objects according to the order induced by the specified comparator.|

### 10. Set Methods

The following table lists all set related methods of Array class:

|Method Signature|Description|
|---|---|
|setAll(double[] array, IntToDoubleFunction generator)|Set all elements of the specified array, using the provided generator function to compute each element.|
|setAll(int[] array, IntUnaryOperator generator)|Set all elements of the specified array, using the provided generator function to compute each element.|
|setAll(long[] array, IntToLongFunction generator)|Set all elements of the specified array, using the provided generator function to compute each element.|
|setAll(T[] array, IntFunction<? extends T> generator)|Set all elements of the specified array, using the provided generator function to compute each element.|

## Arrays Class Method Example

Let's see some commonly used methods of the Java Arrays class.

### 1. Sorting an Array by Using the sort() Method

The following code demonstrates how to sort an array in Java using the Arrays.sort() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         int[] numbers = {5, 2, 8, 1, 3};         
5.         Arrays.sort(numbers);         
6.         System.out.println("Sorted Array: " + Arrays.toString(numbers));  
7.     }  
8. }  

**Output:**

Sorted Array: [1, 2, 3, 5, 8]

When sorting in descending order, apply Arrays.sort() along with Collections.reverseOrder() treatment to Integer[] arrays.

### 2. Comparing Two Arrays by Using the equals() Method

The following code checks whether two arrays are equal in Java using the Arrays.equals() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.    public static void main(String[] args) {  
4.        int[] num1 = {6, 7, 8};  
5.        int[] num2 = {6, 7, 8};  
6.        System.out.println(Arrays.equals(num1, num2));  
7.    }  
8. }  

**Output:**

true

### 3. Searching an Array by Using the binarySearch() Method

The following code demonstrates how to search for an element in a sorted array using the Arrays.binarySearch() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         int[] numbers = {1, 3, 5, 7, 9};  
5.         int index = Arrays.binarySearch(numbers, 5);  
6.         System.out.println("Index of 5 is: " + index);  
7.     }  
8. }  

**Output:**

Index of 5 is: 2

#### Note: The array must be sorted before using the binarySearch() method; otherwise, the results will be unpredictable.

### 4. Filling an Array by Using the fill() Method

The following code demonstrates how to fill all elements of an array with a specific value using the Arrays.fill() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         int[] arr = new int[5];  
5.         Arrays.fill(arr, 10)  
6.         System.out.println("Filled Array: " + Arrays.toString(arr));  
7.     }  
8. }  

**Output:**

Filled Array: [10, 10, 10, 10, 10]

### 5. Copying an Array by Using the copyOf() Method

The following code demonstrates how to copy elements from one array to another using the Arrays.copyOf() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main{  
3.     public static void main(String[] args) {  
4.         int[] original = {1, 2, 3, 4, 5};  
5.         int[] copied = Arrays.copyOf(original, 3);  
6.         System.out.println("Copied Array: " + Arrays.toString(copied));  
7.     }  
8. }  

**Output:**

Copied Array: [1, 2, 3]

### 6. Converting an Array by Using the toString() Method

The following code demonstrates how to convert an array into a readable string format using the Arrays.toString() method.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         String[] names = {"Alice", "Bob", "Charlie"}  
5.         System.out.println("Array as String: " + Arrays.toString(names));  
6.     }  
7. }  

**Output:**

Array as String: [Alice, Bob, Charlie]

### 7. Comparing Two-Dimensional Arrays by Using the deepEquals() Method

The following code demonstrates how to compare two multidimensional arrays and display their contents using the Arrays.deepEquals() and Arrays.deepToString() methods.

#### Code

[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)[](https://www.tpointtech.com/arrays-class-in-java#)

1. import java.util.Arrays;  
2. public class Main {  
3.    public static void main(String[] args) {  
4.        int[][] numbers = {{4, 8, 0}, {9, 5, 1}, {7, 2, 6}};  
5.        int[][] numbersCopy = Arrays.copyOf(numbers, numbers.length);  
6.        System.out.println("Are the given arrays equal to each other?");  
7.        System.out.println(Arrays.deepEquals(numbers, numbersCopy));  
8.        System.out.println(Arrays.deepToString(numbersCopy));  
9.    }  
10. }  

**Output:**

Are the given arrays equal to each other?
true
[[4, 8, 0], [9, 5, 1], [7, 2, 6]]