#### Problem 2: Is Panagram

A pangram is a sentence where every letter of the English alphabet appears at least once.

- #### Approach 1: HashSet
  Using a HashSet to check whether or not a sentence is a panagram or not is the most efficient way to solve this problem. First of all, if a string does not even contain 26 characters or more, we can just claim right away that the sentence is not a panagram. We define a hashSet to store all unique characters of the string, iterating over the whole sentence using a basic for-loop. We must use strip() and lower()/upper() functions in order to skip over whitespaces and to make sure 'A' is considered 'a'. We only add a character to the set if said character is part of the alphabet, so using the isalpha() function in an if statement is necessary. Finally, if the final set length is equal to 26 (total number of alphabet letters), we return True. Otherwise, the sentence is not a panagram, so we return False.

      def checkIfPanagram(self, sentence):
        if len(sentence) < 26:
          return False
  
        letter_set = set()

        for n in sentence.strip().lower():
          if n.isalpha():
            letter_set.add(n)

        return len(letter_set) == 26
      # TC: O(n), SC: O(1)
  
