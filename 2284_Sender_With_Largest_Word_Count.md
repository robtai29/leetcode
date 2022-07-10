/******************\*\*******************\*\*******************\*\*******************
7.9.22
https://leetcode.com/problems/sender-with-largest-word-count/
******************\*\*******************\*\*\*******************\*\*******************/

class Solution {
public String largestWordCount(String[] messages, String[] senders) {
HashMap<String, Integer> map = new HashMap<>();

        for (int i = 0; i < messages.length; i++){
            int count = countWords(messages[i]);
            map.put(senders[i], map.getOrDefault(senders[i], 0) + count);
        }

        return Collections.max(map.keySet(), (a, b) -> map.get(a).compareTo(map.get(b)) == 0 ? a.compareTo(b) : map.get(a).compareTo(map.get(b)));

    }

    private int countWords(String msg){
        if (msg.length() == 0 || msg == null){
            return 0;
        }
        int count = 1;
        for (char ch : msg.toCharArray()){
            if (ch == ' '){
                count++;
            }
        }
        return count;
    }

}
