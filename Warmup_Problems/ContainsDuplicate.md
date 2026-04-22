#### Problem 1: Contains Duplicates
- ##### Approach 1: Brute Force
    A brute force approach can be used to compare each element with all other elements in the array. If any two elements are the same, True will be returned; else if there are no duplicates, False is returned.

      def containsDuplicate(self, nums):
        for i in range(len(nums)):
          for j in range(i + 1, len(nums)):
            if nums[i] == nums[j]:
              return True
        return False
      # TC: O(n^2), SC: O(1)

- #### Approach 2: Hash Set
    Using a set data structure is very helpful, as sets only hold unique elements. We can check if the elements in the given array are peresent more than once by adding them to a set and comparing the array and set after adding elements to the set.

      def containsDuplicate(self, nums):
        # Option 1:
        duplicates = set()
        for n in nums:
          duplicates.add(n)
        return len(duplicates) != len(nums)

        # Option 2: another way to implement this
        unique_set = set()
        for n in nums:
          if n in unique_set:
            return True
          unique_set.add(n)
        return False
      # TC: O(N), SC: O(N)

- #### Approach 3: Sorting
    Another method commonly used is to sort the array first before checking for duplicates. By iterating through the array and comparing current elements to the next element, we can see if they either don't match or do, and if they do match, we have found a duplicate.

      def containsDuplicate(self, nums):
          nums.sort()
          for i in range(len(nums) - 1)
              if nums[i] == nums[i + 1]
                  return True
          return False
      # TC: O(nlogn), SC: O(logn)

The most optimal approach would be to use the Hash Set method, as it has both linear Time and Space Complexities. 

        
