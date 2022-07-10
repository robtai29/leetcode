class Solution {
public String sortString(String s) {
int[] letters = new int[26];

        StringBuilder sb = new StringBuilder();
        for (char ch : s.toCharArray()){
            letters[ch - 'a']++;
        }

        while (sb.length() < s.length()){
            for (int i = 0; i < 26; i++){
                if (letters[i]-- > 0){
                    sb.append((char)('a' + i));
                }
            }

            for (int i = 25; i >= 0; i--){
                if (letters[i]-- > 0){
                    sb.append((char)('a' + i));
                }
            }

        }
        return sb.toString();
    }

}
