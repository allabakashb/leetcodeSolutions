```java

class WordDictionary {
    
    class Trie {
        boolean wordEnd = false;
        Trie[] words = null;
    }
    
    Trie dictionary;

    /** Initialize your data structure here. */
    public WordDictionary() {
        
        dictionary = new Trie();
    }
    
    /** Adds a word into the data structure. */
    public void addWord(String word) {
        
        addWord(word.toCharArray(), dictionary, 0);
    }
    
    private void addWord(char[] word, Trie dict, int index) {
        
        if (index < word.length) {
            
            int charIndex = index(word[index]);
            
            if (dict.words == null) {
                
                dict.words = new Trie[26];
            }
            
            Trie newDict = dict.words[charIndex];
        
            if (newDict == null) {

                newDict = new Trie();
                dict.words[charIndex] = newDict;
            }
            
            if (index == word.length-1) {
                
                newDict.wordEnd = true;
            } else {
                
                addWord(word, newDict, index+1);
            }
        }
    }
    
    private int index(char c) {
        
        return c - 'a';
    }
    
    /** Returns if the word is in the data structure. A word could contain the dot character '.' to represent any one letter. */
    public boolean search(String word) {
                
        return search(word.toCharArray(), dictionary, 0);
    }
            
    private boolean search(char[] word, Trie dict, int index) {
        
        if (dict == null || dict.words == null) return false;
        
        boolean exists = false;
        if (word[index] == '.') {
            
            for (Trie wd: dict.words) {
                
                if (wd != null) {
                    
                    if (index == word.length-1) {
                        
                        if (wd.wordEnd)
                        return wd.wordEnd;
                    } else {
                        
                        if (search(word, wd, index+1)) {

                            return true;
                        }
                    }
                }
            }
            
        } else {
            
            int charIndex = index(word[index]);
            
            Trie wd = dict.words[charIndex];
            
            if (wd != null) {
                
                if (index == word.length-1) {
                        
                    if (wd.wordEnd)
                    return wd.wordEnd;
                } else {
                    
                    exists = search(word, wd, index+1);
                }
            }
        }
        
        return exists;
    }
}

/**
 * Your WordDictionary object will be instantiated and called as such:
 * WordDictionary obj = new WordDictionary();
 * obj.addWord(word);
 * boolean param_2 = obj.search(word);
 */
 
 
 /*
 
  Time Complexity - 
  addWord - O(N) - N - length of the string
  search - O(N) -  N - length of the string
   
   Space Complexity - O(N*K) - N - number of nodes and K - max length of a string
 
 */
 
 ```
