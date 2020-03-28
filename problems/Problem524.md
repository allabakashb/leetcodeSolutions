```java

class Solution {
    public String findLongestWord(String strRef, List<String> dictionary) {
        
    String longestWord = "";
		char[] refArray = strRef.toCharArray();
		for (String word: dictionary) {

			if (word.length() <= refArray.length 
             && word.length() >= longestWord.length() 
             && isValidSubSeq(refArray, word, longestWord)) {
				        longestWord = word;
            }
        }

		    return longestWord;
    }
    
   private boolean isValidSubSeq(final char[] refArray, final String word,
      final String longestWord) {

    final int len1 = refArray.length, len2 = word.length(),
        len3 = longestWord.length();

    int i = 0, j = 0, k = 0;

    boolean isValidResult = len3 > 0;

    while (i < len1 && j < len2) {

      if (refArray[i] == word.charAt(j)) {

        if (isValidResult && len3 >= len2) {

          if (word.charAt(j) > longestWord.charAt(k)) {

            return false;
          } else if (word.charAt(j) < longestWord.charAt(k)) {

            isValidResult = false;
          }
        }

        ++k;
        ++j;
      }
      ++i;
    }

    return j == len2 && j >= len3;
  }
}

/*

    Time Complexity = O(n * m)
    Space Complexity = O(m)
    
    m - Length of String Reference
    n - Size of the dictionary

*/
```
