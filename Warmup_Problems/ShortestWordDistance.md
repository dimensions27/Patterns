#### Problem 6: Shortest Word Distance

- #### Approach 1: Two Pointer Approach
  To find the shortest distane between two words, we can iterate through the list of words and use two pointers to track the positions of these words. When a word is found, we update the position of the word and calculate the distance from the other word. If both position1 and position2 have been updated, that means both words have been found in the list. In this case, update the shortestDistance with the absolute difference of the positions of word1 and word2, and if there are mutliple instances of the same word in the list, we combat this by finding the minimum between the current and newly calculated distance.

      import math
  
      def shortestDistance(self, words, word1, word2):
        shortestDistance = len(words)
        postion1, position2 = -1, -1
        for i, word in enumerate(words):
          if word == word1:
            position1 = i
          elif word == word2:
            postion2 = i
          if position1 != -1 and position2 != -1:
            shortestDistance = min(shortestDistance, abs(position1 - position2))

          return shortestDistance

      # TC: O(n), SC: O(1)
          
