<div align="center">
  <h1> Strings, Array and List</h1>
<sub>Author:
<a href="https://www.linkedin.com/in/chidi-jude" target="_blank">Chidi Jude</a><br>
</sub>

</div>

[Week 3 >>](../Week%203%20Hash%20Tables/Hash%20Tables.md)

![NitHub](../images/Nithub_image.jpeg)

- [📘 Week 2 Strings, Arrays and List](#-week-2)
    - [Assignment Submissions](#submissions)
        - [String Compressions](#string-compression)
   

    
# 📘 Week 2
## Assignment Submissions

###   String Compression
```cs
public class Solution {
    public int Compress(char[] chars) {
        StringBuilder s = new StringBuilder();
        int count = 0;
        string holder = "";

        for (var i = 0; i < chars.Length; i++){
            var item = chars[i];
            if (item.ToString() == holder){
                count += 1;
            }
            else{
                s.Append(holder);
                if (count/10 > 0){
                    s.Append((count/10).ToString());
                    s.Append((count % 10).ToString());
                }
                if (count > 1 && count < 10){
                    s.Append((count % 10).ToString());
                }                
                count = 1;           
            }
            holder = item.ToString();
        }
         s.Append(holder);
        if (count/10 > 0){
            s.Append((count/10).ToString());
            s.Append((count % 10).ToString());
        }
        if (count > 1 && count < 10){
            s.Append((count % 10).ToString());
        }   
        for (var i = 0; i < s.ToString().Length; i++){
            chars[i] = s[i];
        }       
        return s.ToString().Length;
    }
}
```
![String Ccompression Submission](../images/String%20Compression.png)
