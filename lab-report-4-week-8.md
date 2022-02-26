# Lab Report 4 (Week 8)
---
## Links to markdown-parse repositories
* **My own repository: [Jessie's repository](https://github.com/ouyangca/markdown-parse)**
* **The one I reviewed: [Sean's repository](https://github.com/5ean-github/markdown-parse)**
---
## Snippet 1
* **Expected output using [CommonMark demo](https://spec.commonmark.org/dingus/)**
![image](https://user-images.githubusercontent.com/51312196/155672226-dbc5c11a-1cc1-4f3d-8236-0f94d0226207.png)
Expected output in terminal:

![image](https://user-images.githubusercontent.com/51312196/155676639-f7be66c7-d3e1-4e3d-9ed0-5852e435a3b9.png)

* **Code in MarkdownParseTest.java**
![image](https://user-images.githubusercontent.com/51312196/155817791-1f8c82f2-e51a-425c-a840-b743566406df.png)

* **My implementation**
![image](https://user-images.githubusercontent.com/51312196/155818011-02db0e90-3575-4599-bdd7-b48ad20dab22.png)

1)  test parseSnippet1 did not pass because we included url.com in the list of links, but it is not supposed to be scanned as a link. I am guessing the purpose of the ` is omit the [ after it. My code does not account the appearance of ` will omit the symbol after it.

* **Sean's implementation**

![image](https://user-images.githubusercontent.com/51312196/155860996-3f945ba8-b0c5-4bf5-9fd8-07f52ec33491.png)

---
## Snippet 2
* **Expected output using [CommonMark demo](https://spec.commonmark.org/dingus/)**
![image](https://user-images.githubusercontent.com/51312196/155677987-ed6d038b-fa1a-441c-bfce-23b1e61b13a9.png)
Expected output in terminal:

![image](https://user-images.githubusercontent.com/51312196/155677903-df650216-13b5-41a4-a0d5-7922d9eff2e9.png)

* **Code in MarkdownParseTest.java**
![image](https://user-images.githubusercontent.com/51312196/155817806-61fb051b-8c72-40b3-8a25-6bc2ba29ce7b.png)

* **My implementation**
![image](https://user-images.githubusercontent.com/51312196/155818011-02db0e90-3575-4599-bdd7-b48ad20dab22.png)

1)  test parseSnippet2 did not pass because instead of "a.com(())", we have "a.com((". The cause of this is my code automatically scans for the next closing parenthesis after detecting the first opening parenthesis. Thus, anything after the first closing parenthesis will not be included in the link string. 


* **Sean's implementation**

![image](https://user-images.githubusercontent.com/51312196/155861001-81e8c039-6008-4981-9412-7fe7a86673eb.png)

---
## Snippet 3
* **Expected output using [CommonMark demo](https://spec.commonmark.org/dingus/)**
![image](https://user-images.githubusercontent.com/51312196/155678515-a1b4bf48-a7c2-4739-bb56-1c62d8aaf817.png)
Expected output in terminal:

![image](https://user-images.githubusercontent.com/51312196/155678670-f2f23ba3-a84d-4c8a-89ef-c6802af9c628.png)

* **Code in MarkdownParseTest.java**
![image](https://user-images.githubusercontent.com/51312196/155817838-2445d995-5882-419e-b7af-da7b7c5a26ea.png)

* **My implementation**

![image](https://user-images.githubusercontent.com/51312196/155818011-02db0e90-3575-4599-bdd7-b48ad20dab22.png)

1)  test parseSnippet3 did not pass because we detected invalid input and null is returned. My code basically will categorize any md file that does not end with a closing parenthesis as invalid input. 
* **Sean's implementation**

![image](https://user-images.githubusercontent.com/51312196/155861011-5df9c9a2-4b10-40cb-8afc-49e072f055e2.png)

---
## Fixing code
* **Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.**

Yes. I only need to add two lines of code - every time we find a open braket or a closed bracket , check of the character right before it, if it is a backtick, then ignore the braket and continue to search for the next bracket after that.
* **Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.**

It would be a more involved change, because my code right now is searching each symbol in order. For example, after we locate the first opening bracket, the code will continue to search for a closing bracket while ignoring all the other symbols, such as parenthesis or another opening bracket. I would have to add code to take into the account of escaped brakets, and that would take 1-2 lines, and then I have to add code to make sure that there is no more opening brackets after the first opening bracket we found, or else we need to update the index. I then have to make sure the parenthesis we found are the outer most parenthesis.


* **Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.**

It would be a more involved change. First, I have to make sure when there are line breaks between the brackets, we ignore the entire thing before the line break. Then, when a link does not have a closing parenthesis, we need to change the code to not keep searching for a closing parenthesis, but would detect the next opening bracket instead. Lastly, we have to take into account that the md file will not always have a closing parenthesis as the last character. 
