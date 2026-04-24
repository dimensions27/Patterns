#### Problem 4: Is Palindrome

- #### Approach 1: List Reversal
  The first approach I went for was to initialize an empty list named new_s, then created a for-loop that stripped and made all characters lowercase in the inputted string. From there, I checked to see if the character in iteration was either an alphabetical character or number. If true, we append the character into new_s, otherwise we increment by 1 and check the next character until there are no more left. From there, we return whether or not the value of the normal new_s and reversed new_s are equal using splicing.

      def isPalindrome(self, s):
        new_s = []
        for c in s.strip().lower():
          if c.isalnum():
            new_s.append(c)

        return new_s[::] == new_s[::-1]
      # TC: O(n), SC: O(n)

- #### Approach 2: Two-Pointer Technique
  The most common approach (and most taught) is using two pointers (start and last), that go right and left, set at the start of the string. Then you enter a while loop that stays until the pointers cross each other. Inside the loop, the first inner loop moves start forward while skipping any characters that are not letters or digits, until it points to a valid character or crosses last. The second inner while loop moves last pointer following the same rules. After finding valid characters at either start or last, it converts the characters into lowercase and checks if they are the same. If the while loop terminates without finding unequal pairs, the function returns true, otherwise false is returned.

      def isPalindrome(self, s):
        i, j = 0, len(s) - 1

        while i < j:
          while i < j and not s[i].isalnum():
            i += 1
          while i < j and not s[j].isalnum():
            j -= 1
          if s[i].lower() != s[j].lower():
            return False
          i += 1
          j -= 1

        return True
      # TC: O(n), SC: O(1)

  
      
