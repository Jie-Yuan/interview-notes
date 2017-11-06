# Sorting

Name      |Worst      |Best       |Avg        |Aux   |Stable  |Adaptive
----------|-----------|-----------|-----------|------|--------|---------
Bubble    |`O(n**2)`  |`O(n)`     |`O(n**2)`  |`O(1)`|X       |X
Selection |`O(n**2)`  |`O(n**2)`  |`O(n**2)`  |`O(1)`|        |
Insertion |`O(n**2)`  |`O(n)`     |`O(n**2)`  |`O(1)`|X       |X
Shell     |`O(n**2)`  |`O(nlogn)` |gap variant|`O(1)`|        |X
Heap      |`O(nlogn)` |`O(n)`     |`O(nlogn)` |`O(1)`|        |
Merge     |`O(nlogn)` |`O(nlogn)` |`O(nlogn)` |`O(n)`|X       |
Quick     |`O(n**2)`  |`O(nlogn)` |`O(nlogn)` |`O(n)`|        |
Tim       |`O(nlogn)` |`O(n)`     |`O(nlogn)` |`O(n)`|X       |X
Counting  |`O(n+k)`   |`O(n+k)`   |`O(n+k)`   |`O(k)`|X       |
Radix     |`O(d(n+k))`|`O(d(n+k))`|`O(d(n+k))`|`O(k)`|X       |

When choosing a sorting algo, think about how the different [data cases][1]
effect the behavior of each sorting algo

What is comparison based sort lower bound = `O(nlogn)`

## Bubble:
* elements are bubbled, **via swaps**, into the sorted section
* each pass places a maximums

## Selection:
* maximums are placed, **via 1 swap**, into the sorted section

## Insertion:
* elements are inserted, **via shifts**, into the sorted section
* low overhead
* complexity is `O(n + f(n))` where `f(n)` is the number of inversions.
`f(n) = O(n)` when the list is partially sorted, therefore, if we know the
data is **always partially sorted**, insertion is the best sort hands down
(`O(n)` time and `0(1)` aux space)

## Shell:
* gap sequence defined, insertion sorts which partially sorts list before
final insertion sort with `gap = 1`
* allows the direct exchange of items that are far apart
* any decreasing sequence that ends in 1 will work as a gap sequence

## Heap:
* `build-heap`(not obvious) and then `pop` until the heap is empty

## Merge:
* divide via recursion then conquer via merges
* `bottom-up` vs `top-down`: tail-call optimization
* space complexity can be verified using sum of powers of 2 + tracing algo
* stable as long as we **favor left-half values** when merging

## Quick:
* divide via partitioning around pivot then conquer with recursion
* lists with **few unique elements** aka many duplicates = 3 way partition

## Tim:
* hybrid of insertion & merge sort
* takes advantage of miniruns

## Counting:
* count, prefix sum, place and then +1(not -1)

## Radix:
* apply a stable sort(ex:counting), across digits, from least to most
significant fig


[1]: https://www.toptal.com/developers/sorting-algorithms/
