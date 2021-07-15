# Arrays - Notes

## Introduction

- homogenous data
- contiguous memory locations
- cache friendliness
- O(1) access

## Types of Arrays

1. **Fixed size arrays** ⇒ don't allow more items than current capacity
2. **Dynamic size arrays** ⇒ automatically resize

### Fixed Size Arrays

**Note:**

- **In C/C++ fixed size arrays are allocated memory in two ways:**

1. stack segment allocation

```cpp
int arr[100];
int arr[n];
int arr[] = {1,2,3,4,5};
```

2. heap segment allocation

```cpp
int *arr = new int[n];
```

- **In java, arrays are always allocated in heap**

```java
int arr[] = new int[n];
```

### Dynamic Size Arrays

- resize automatically
- in C++ it's called vector
- In Java it's called ArrayList
- Python dynamic by default

![Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled.png](Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled.png)

## Array Operations

### Searching in Array

Unsorted Array ⇒ takes O(n)

Sorted Array ⇒ takes O(log n) [binary search]

### Inserting in Array

```cpp
int insert(int arr[], int x, int cap, int pos){
   if(n == cap) return n;

   int idx = pos-1;
   for(int i=n-2;i>=idx;i--)
       arr[i+1]=arr[i];
   arr[idx] = x;
   return n+1;
}
```

### Deleting in array

```cpp
int delete(int arr[], int n, int x){
	int i;
	for(i=0;i<n;i++){
			if(arr[i] == x) break;
	}
	if(i == n) return n;
	for(int j=i;j<n-1;j++)
			arr[j] = arr[j+1];

	return n-1;
}
```

### Finding Largest element

```cpp
int getLargest(int arr[], int n){
	//set result as 0 initially
	int res = 0;
	for(int i=0;i<n;i++){
		//if current element is greater than what is pointed
		//by result, point res at that element
		if(arr[i] > arr[res]){
			res = i;
		}
	}
	//return index of largest element
	return res;
}
```

### Finding second largest element

**Trivial solution - 2 pass**

```cpp
int secondLargest(int arr[], int n){
	//first we get the largest number
	int largest = getLargest(arr,n);
	int res = -1;
	for(int i=0;i<n;i++){
		//if current element is not largest
		if(arr[i] != arr[largest]){
			//initial case
			if(res == -1) res = i;
			//case where current is greater than element pointed
			//by res
			else if(arr[res] < arr[i]) res = i;
		}
	}	
	return res;
}
```

**Efficient Solution - single pass**

```cpp
ALGORITHM CASES:
	//NEXT ELEMENT GREATER THAN LARGEST SO FAR
	//MAKE EARLIER AS SECOND LARGEST, MAKE CURRENT AS LARGEST
	1. ARR[I] > ARR[LARGEST]: RES = LARGEST, LARGEST = I
	//IF NEW ELEMENT COMES IN WHICH IS EQUAL TO LARGEST, 
	//DOES NOT CHANGE ANYTHING
	2. ARR[I] == ARR[LARGEST]: IGNORE!
	//WHEN CURRENT ELEMENT IS SMALLER THAN LARGEST
	3. A[I] < A[LARGEST]
		//NEVER SEEN SECOND LARGEST
		3.1. RES == -1: RES = I
		//THERE WAS SECOND LARGEST, NEW ELEMENT IS SMALLER
		3.2. A[I] < A[RES]: IGNORE!
		//THERE WAS SECOND LARGEST, BUT NEW ELEMENT IS LARGER
		3.3. A[I] > A[RES]: RES = I
	
```

```cpp
int secondLargest(int arr[], int n){
	int res = -1, largest = 0;
	for(int i=0; i<n; i++){
		if(arr[i] > arr[largest]){
			res = largest;
			largest = i;
		} else if(arr[i] < arr[largest]){
				if(res == -1 || arr[i] > arr[res]){
					res = i; 
				}
		}
	}
	return res;
}
```

### Move 0s to the end of the array

**Trivial solution:** Intuition for the trivial solution is that whenever we see a 0, we save it's position. We then check numbers ahead of it, as soon as we see a non-zero element we swap it with the saved element.

**Efficient Solution:** Intuition for the efficient solution is that you can store the position of next 0 by maintaining count of non zero elements before it. That is, if you have fixed a0..ai-1 it's easy to process ai in single pass

![Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%201.png](Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%201.png)

```cpp
void moveZeros(int arr[], int n){
	int count = 0;
	for(int i=0;i<n;i++){
		if(arr[i]!=0){
			swap(arr[i],arr[count]);
			count++;
		}
	}
}
```

### Reversing an Array

```cpp
void reverse(int arr[], int n){
	int low=0,high=n-1;
	while(low < high){
		int temp = arr[low];
		arr[low] = arr[high];
		arr[high] = temp;
		low++;
		high--;
	}
}
```

### Left Rotation by 1

```cpp
void rotateCounterClockwise(int arr[], int n){
	int start = arr[0];
	for(int i=1;i<n;i++)
		arr[i-1] = arr[i];
	arr[n-1] = start;
}
```

## Algorithms

### Kadane's algorithm

**Condition:** Given an array, find the maximum subarray sum.

**Brute Force Approach**

For each index, check all the possible subarrays to find the maximum sum.

![Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%202.png](Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%202.png)

**Kadane's Approach**

Kadane's approach works in linear time. It says that to find the maximum sum, you don't really need to look at all possible subarrays. You can find the max sum till an index i such that it is the max of current index element taken alone or current element combined with the max sum upto that index.

![Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%203.png](Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%203.png)

```cpp
int maxSubarraySum(int arr[], int n){
       int mCurr = arr[0], mGlob = arr[0];
       for(int i=1;i<n;i++){
           mCurr = max(arr[i],arr[i]+mCurr);
           if(mCurr>mGlob) mGlob = mCurr;
       }
       
       return mGlob;
    }
```

[Kadane's Algorithm to Maximum Sum Subarray Problem](https://youtu.be/86CQq3pKSUw)

Good video by CS Dojo

### Sort an Array of 0s, 1s and 2s

![Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%204.png](Arrays%20-%20Notes%2020406adf4176492ebe22a082617b5aa3/Untitled%204.png)

[BRO3886/450dsa](https://github.com/BRO3886/450dsa/blob/main/Sort%20an%20array%20of%200s%2C%201s%20and%202s%20-%20GFG/sort-an-array-of-0s-1s-and-2s.cpp)
