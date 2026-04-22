#### Problem 3: Reverse Vowels in a String

We need to reverse only all the vowels in any given string and return it, keeping the positions of consonants and other characters intact. There are two methods (more but we will focus on two) and they involve using either a stack, or using the two-pointer technique.

- #### Approach 1: Two-pointer Approach
  We first create a static string that contains all lowercase and uppercase vowels, which is used to check whether a character in the input string is a vowel. Our first pointer is at index 0, and our last pointer is at the last index of the string. Converting the input string to a character array makes it easier for us to manipulate individual characters. The while loop we enter when the first pointer index is left to the last pointer index allows us to check if we just found a consonant, skip it, otherwise we are going to swap them at the specified indices. Finally, we are going to to join all the characters in the array into a string.

      def reverseVowels(self, s):
        vowels = "aeiouAEIOU"
        first, last = 0, len(s) - 1
        array = list(s)
        while first < last:
          while first < last and vowels.find(array[first]) == -1:
            first += 1
          while first < last and vowels.find(array[last]) == -1:
            last -= 1

          array[first], array[last] = array[last], array[first]

          first += 1
          first -= 1

        return "".join(array)
      # TC: O(n), SC: O(n)

- #### Approach 2: Stack + Set Method
  My personal favorite approach is creating a set of vowels with all the vowels both uppercase and lowercase, and a stack in which we will append our found vowels from the inputted string. With a simple for loop, we check to see if a character from the inputted string is in our vowel set, and if it is, we append it onto the discovered_vowels list. After adding all the found vowels into our list, we create a new list called new_string. We make a new for-loop to iterate through the inputted string again, and if we find a consonant (otherwise a character not found in our vowel set), we append the character into the new_string list. If we do find a vowel, we append the last character from our discovered_vowel list using pop(), which takes the last thing inputted, and removes it from the respective list and adds it into our new_string list. Finally, we join the characters into a string.

      def reverseVowels(self, s):
        vowels = set("aeiouAEIOU")
        discovered_vowels = []
    
        for char in s:
          if char in vowels:
            discovered_vowels.append(char)

        new_string = []
        for char in s:
          if char not in vowels:
            new_string.append(char)
          else:
            new_string.append(discovered_vowels.pop())

        return ''.join(new_string)
      # TC: O(n), SC: O(n)

    
