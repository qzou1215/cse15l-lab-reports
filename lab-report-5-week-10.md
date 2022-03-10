# Lab Report 5
# Find tests with different results
In order to find tests with different results between my implementation of markdown-parse and the provided implementation,
* I use command `bash script.sh > results.txt` to save the outputs of my markdown-parse into `results.txt` file.
* Then I use the same command to save the outputs of the provided markdown-parse into `results.txt` file in another repository.
* Then I use program `diff` to show the differences between the two `results.txt` files in different repositories.
The command and outputs are as the following:
![diff1](diff1.png)
![diff2](diff2.png)
![diff3](diff3.png)
# Test One
Based on the outputs above, one test with different results is in `580.md` (line 1070).
* The actual output for my markdown-parse is `[]`, while the actual output for the provided markdown-parse is `[/url]`.
![580diff](580diff.png)
* Based on the preview, the expected output should be `[]`, so my implementation is correct, and the provided one is not.
![580output](580output.png)
* The problem with the provided implementation is that it does not consider the situation when there is nothing between `[]`, which leads to the situation when the link between `()` cannot be displayed.
The following part of code does not consider this situation. It does not check if there is content between `[]` and directly adds the link between `()` to `toReturn` and return it, causing the output to be `[/url]`.
![580bug](580bug.png)
# Test Two
Based on the outputs above, another test with different results is in `516.md` (line 928).
* The actual output for my markdown-parse is `[]`, while the actual output for the provided markdown-parse is `[moon.jpg]`.
![516diff](516diff.png)
* Based on the preview, the expected output should be `[/uri]`, so both implementations are wrong.
![516output](516output.png)
* The problem with the provided implementation is that it does not consider the situation when there is `()` between `[]`. In this situation, content between `()` is not the correct link. Rather, content between the `()` after the `[]` should be the link.
The following part of code does not consider this situation. The variable `openParen` refers to the index of `(` that first appears in the file. This makes the method `findCloseParen` make the `)` that first appears to be `closeParen`.
Thus, content between the `()` between the `[]` will be added to `toReturn`, causing the output to be `[moon.jpg]`.
![516bug](516bug.png)