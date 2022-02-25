# Lab Report 3
* A [link](https://github.com/qzou1215/markdown-parse-new.git) to my markdown-parse repository
* A [link](https://github.com/aajc/markdown-parse.git) to the repository I reviewed
## Test for Snippet 1 (Implementation Reviewed)
* What markdown-parse should produce
![Snippet1Preview](Snippet1Preview.png)
* Test code
![PTest1](PTest1.png)
* Test output
![POutput1](POutput1.png)
## Test for Snippet 2 (Implementation Reviewed)
* What markdown-parse should produce
![Snippet2Preview](Snippet2Preview.png)
* Test code
![PTest2](PTest2.png)
* Test output
![POutput2](POutput2.png)
## Test for Snippet 3 (Implementation Reviewed)
* What markdown-parse should produce
![Snippet3Preview](Snippet3Preview.png)
* Test code
![PTest3](PTest3.png)
* Test output
![POutput3](POutput3.png)
## Test for Snippet 1 (My Implementation)
* What markdown-parse should produce
![Snippet1Preview](Snippet1Preview.png)
* Test code
![PTest1](PTest1.png)
* Test output
![MOutput1](MOutput1.png)
## Test for Snippet 2 (My Implementation)
* What markdown-parse should produce
![Snippet2Preview](Snippet2Preview.png)
* Test code
![PTest2](PTest2.png)
* Test output
![MOutput2](MOutput2.png)
## Test for Snippet 3 (My Implementation)
* What markdown-parse should produce
![Snippet3Preview](Snippet3Preview.png)
* Test code
![PTest3](PTest3.png)
* Test output
![MOutput3](MOutput3.png)
## Answers to questions
* I think there is a small code change that will make my program work for snippet 1 and all related cases that use inline code with backticks.
I can write a helper method that determines a valid link. In this case, if open bracket or open parenthesis occur between a pair of backticks, the method will determine this is an invalid link, so markdown-parse will not return the link.
* I think there is a small code change that will make my program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets.
I can change the code of markdown-parse to make `closeParen` the index of the last close parenthesis, so markdown-parse will return the entire link in the parathesis. In this case, the program will reutrn `a.com(())` rather than `a.com((`.
* I think there is a small code change that will make my program work for snippet 3 and all related cases that have newlines in brackets and parentheses.
I can write a helper method that returns a new string with the same content as Snippet 3, but it makes each link in the same line, so the output will not include new lines. For the link without close parenthesis, I can write a helper method that decides if a link has close parenthesis. If it doesn't, the program will consider it as an invalid link and will not return it.

