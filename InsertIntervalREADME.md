# leet-day80

# Insert Interval into Sorted Intervals

This C++ solution is for the "Insert Interval" problem on LeetCode. Given a sorted list of non-overlapping intervals, this code inserts a new interval into the list while maintaining the sorted order and ensuring there are no overlapping intervals.

## Usage

1. Clone this repository:

    ```bash
    git clone <repository-url>
    ```

2. Compile the C++ code:

    ```bash
    g++ insert_interval.cpp -o insert_interval
    ```

3. Run the executable:

    ```bash
    ./insert_interval
    ```

4. Modify the `insert_interval.cpp` file to use the `insert` function in your own C++ code.

## Algorithm Explanation

The code follows these steps:

1. Initialize an empty vector `result` to store the merged intervals.
2. Iterate through the given `intervals` while comparing each interval with the `newInterval`:
   a. If the current interval ends before the `newInterval` starts (i.e., `intervals[i][1] < newInterval[0]`), add it to the result vector as it doesn't overlap with the new interval.
   b. If the current interval starts after the `newInterval` ends (i.e., `intervals[i][0] > newInterval[1]`), it means you have passed the point of insertion. Add the new interval and all remaining intervals to the result vector and break from the loop.
   c. If there's an overlap between the current interval and the new interval, update the `newInterval` to be the merged interval of the two (take the minimum start and maximum end), and continue to the next interval.
3. After the loop, add the final `newInterval` to the result vector.
4. Return the `result` vector as the merged and sorted intervals.

