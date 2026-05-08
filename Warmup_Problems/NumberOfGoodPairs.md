#### Problem 7: Number of Good Pairs

- #### Approach 1: HashMap Method
  We can use a HashMap to store the frequency of each number in the array **nums**. For each number in the arrary, we can incrememnt the count of the number in the hashmap. When we find a new occurrence of a number, we have found a new pair. Evert new occurence of a number can be paired with each previous occurence of the same number, so if a number has already appeared, say 3 times, we will have 2 new pairs. This is why we add the number of occurences, p, minus 1 to pairCount, which keeps track of the total number of good pairs.

      def numGoodPairs(self, nums):
        pairCount = 0
        count = {}
        for n in nums:
          if n in count:
            pairCount += count[n]
            count[n] += 1
          else:
            count[n] = 1
        return pairCount
      # TC: O(n), SC: O(n)

- #### Approach 2: HashMap using get()

      def numGoodPairs(self, nums):
        pairCount = 0
        map = {}
        for n in nums:
          map[n] = map.get(n,0) + 1
          pairCount += map[n] - 1
        return pairCount
      # TC: O(n), SC: O(n)
      
- #### Approach 2: HashMap (Built-in Counter Python)

      def numGoodPairs(self, nums):
        count = Counter(nums)
        res = 0
        for n, c in count.items():
          res += c * (c - 1 ) // 2
        return res
      # TC: O(n), SC: O(n)

- #### Approach 4: Two-pointer Approach

      def numGoodPairs(self, nums):
        pairCount = 0
        l, j = 0, len(nums) - 1
        for i in range(len(nums)):
          for j in range(i +1, len(nums)):
            if nums[i] == nums[j] and i < j:
              pairCount += 1
            
        return pairCount
      # TC: O(n^2), SC: O(1)
