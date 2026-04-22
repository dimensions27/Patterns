# Patterns
Notes for myself that contain patterns for coding problems and situations

This is simply going to be a note taking repository so I can further my knowledge on the common and uncommon patterns we see throughout many coding problems, along with in depth example. There will be coding blocks along with descriptions to what approaches are deemed best, along with time complexities and space complexities of each approach. 

There are around ~30 patterns I will be jotting down, feel free to poke around. There will be different files based on patterns and problems associated with them, all in one repository.

#### Problem 1: Contains Duplicates
- ##### Approach 1: Brute Force
    A brute force approach can be used to compare each element with all other elements in the array. If any two elements are the same, True will be returned; else if there are no duplicates, False is returned.

      def containsDuplicate(self, nums):
        for i in range(len(nums)):
          for j in range(i + 1, len(nums)):
            if nums[i] == nums[j]:
              return True
        return False # TC: O(n^2), SC: O(1)

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

        



