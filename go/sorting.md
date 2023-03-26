# Sorting

Sorting integers in Go is quite straightforward because you only need to call `sort.Slice`. However, there are some cases where you are prohibited to call a helper (e.g. **the interview**).

As a mitigation, we are going to learn a simple (yet slow) sorting algorithm. Bubble sort.

## sort.Slice

First, let's take a look into the mentioned `sort.Slice` (see [https://pkg.go.dev/sort#Slice](https://pkg.go.dev/sort#Slice)).

```go
// Slice sorts the slice x given the provided less function.
func Slice(x any, less func(i, j int) bool)
```

Sorting in ascending manner.

```go
nums := []int{1, 3, 2, 4} // 1, 3, 2, 4
sort.Slice(nums, func(i, j int) bool {
    return nums[i] < nums[j]
}) // sorted to 1, 2, 3, 4
```

To sort in descending manner, simply we just need to change from `nums[i] < nums[j]` to `nums[i] > nums[j].`

```
nums := []int{1, 3, 2, 4} // 1, 3, 2, 4
sort.Slice(nums, func(i, j int) bool {
    return nums[i] > nums[j]
}) // sorted to 4, 3, 2, 1
```

Simple right? Now, let's assume that the interviewer prohibits us from using `sort.Slice` and we decide to use the bubble sort algorithm.

## Bubble Sort

Bubble sort swaps the adjacent elements if they are in the wrong order. Most of the time, bubble sort will produce an O(n^2) time complexity.

Example of bubble sort implementation in Go.

```go
func BubbleSort(array[] int)[]int {
   for i:=0; i< len(array)-1; i++ {
      for j:=0; j < len(array)-i-1; j++ {
         if (array[j] > array[j+1]) {
            array[j], array[j+1] = array[j+1], array[j] // Swap if in wrong order
         }
      }
   }
   return array
}
```

As we can see, the `BubbleSort` function iterates through the `i` and `j` completely. This is why we often have O(n^2) time complexity.
