
**Problem Number: 826
Relevant Tags: [[02 - DS - O - HashMap]]
<h1> Problem Description </h1>

You have `n` jobs and `m` workers. You are given three arrays: `difficulty`, `profit`, and `worker` where:

- `difficulty[i]` and `profit[i]` are the difficulty and the profit of the `ith` job, and
- `worker[j]` is the ability of `jth` worker (i.e., the `jth` worker can only complete a job with difficulty at most `worker[j]`).

Every worker can be assigned **at most one job**, but one job can be **completed multiple times**.

- For example, if three workers attempt the same job that pays `$1`, then the total profit will be `$3`. If a worker cannot complete any job, their profit is `$0`.

Return the maximum profit we can achieve after assigning the workers to the jobs.

**Example 1:**

**Input:** difficulty = [2,4,6,8,10], profit = [10,20,30,40,50], worker = [4,5,6,7]
**Output:** 100
**Explanation:** Workers are assigned jobs of difficulty [4,4,6,6] and they get a profit of [20,20,30,30] separately.

**Example 2:**

**Input:** difficulty = [85,47,57], profit = [24,66,99], worker = [40,25,25]
**Output:** 0

**Constraints:**

- `n == difficulty.length`
- `n == profit.length`
- `m == worker.length`
- `1 <= n, m <= 104`
- `1 <= difficulty[i], profit[i], worker[i] <= 105`
-----
Simple brute force solution, but there seems to be a more elegant solution that involves sorting the worker array - intuition says to just sort all three arrays to try and avoid TLE.

Actually, thinking about this - not too sure what sorting does, but you can create a hashmap where you map difficulty to profit.
Maybe then you sort it after creating the hashmap? Sort difficulty. 
Then you will have -
hashmap of difficulty mapped to profit
sorted array of easiest to hardest jobs
sorted array of worker capabilities

then iterate through the list of workers and initialize a maxprofit variable
(bruteforce brainrot)
check each value in the hashmap by iterating through the sorted array of difficulties, if difficulty[i] is more than worker[i] you can increment i by 1 (effectively continuing) because the worker will not be able to work on anything more difficult

<h1> Solution </h1>
