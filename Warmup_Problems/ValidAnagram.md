#### Problem 5: Valid Anagram

- #### Approach 1: Hash Map
  We can solve this problem by calculating the frequency of appearance per character in both strings. If the frequency of each character is the same in both the given strings, the strings are anagrams of each other. Using a hash map to store the frequency of each character is a standard way to approach this. For each character in the string, the frequency of that character in the first string is incremented and the frequency of that character in the second string is decremented. After iterating over all valid characters, we check to see if the frequency of all characters is 0. A base case to have is to check the length of the string, since if they are not the same length, we can return false right away.

      def isAnagram(self, s, t):
        if len(s) != len(t):
          return False

        frequency_map = {}

        for i in range(len(s)):
          if s[i] in freq_map:
            frequency_map[s[i]] += 1
          else:
            frequency_map[s[i]] = 1

          if t[i] in frequency_map:
            frequency_map[t[i]] -= 1
          else:
            frequency_map[t[i]] = -1

        for char in frequency_map:
          if frequency_map[char] != 0:
            return False

        return True

      # TC: O(n), SC: O(1)
