# How I found the differences between outputs
I tried to use the diff method, but because my implementation will give some exceptions when encounter certain inputs, while the given implementation will not, so the output from the two implementations are very different, so the diff function will not work. Thus, I instead collected all the outputs into a txt file, and then manually checked the outputs. Here are screenshots of the results.txt:
![image](https://user-images.githubusercontent.com/51312196/158932034-6dbf68dd-1b84-4d69-b936-b374d7db8fb3.png)
![image](https://user-images.githubusercontent.com/51312196/158932159-6789a143-d6b3-4874-9b59-c84de904059c.png)


# 1st test
test file [511.md](https://github.com/ucsd-cse15l-w22/markdown-parse/blob/main/test-files/511.md)
![image](https://user-images.githubusercontent.com/51312196/158481373-5b5f34ad-8424-4b7b-bab3-93eafd6ff258.png)


## The output from my markdownparse implementation
![image](https://user-images.githubusercontent.com/51312196/158481718-a76c3c2b-9bb9-4055-9f67-6b0fe8c0a58b.png)

## The output from the implementation provided in lab 9 
![image](https://user-images.githubusercontent.com/51312196/158481407-222c02bc-c220-4ff2-8751-b788b2f2fcd6.png)

## How to fix bug

Here my implementation is giving the wrong output because my code is prompting that there is an invalid input when it encounters a symbol that is not ( after the first closing bracket ]. I would change my code to check if there is another ] after the first ] and record the location of the last ] before the next (. 
![image](https://user-images.githubusercontent.com/51312196/158933430-e3a42fe5-eb3e-44e4-ac1f-f5acc23e2e90.png)
More code should be added under the highlighted portion in order to make sure there are no other ] after the one being found.


# 2nd test
test file [530.md](https://github.com/ucsd-cse15l-w22/markdown-parse/blob/main/test-files/530.md)
![image](https://user-images.githubusercontent.com/51312196/158480830-6f612d4f-94e2-414b-9a83-d1a6cfa0f4c1.png)

## The output from my markdownparse implementation
![image](https://user-images.githubusercontent.com/51312196/158481686-e3a4a626-5d69-459b-8889-472162da1493.png)

## The output from the implementation provided in lab 9 
![image](https://user-images.githubusercontent.com/51312196/158481226-77c60614-1ef6-4e43-bbfb-a4cbca4f0e61.png)

## How to fix bug
The given implementation output is wrong because .jpg should not be considered as a link, instead, it is a picture.
![image](https://user-images.githubusercontent.com/51312196/158932394-49327009-0df8-4d2d-b19a-86a8862c6153.png)
Over here, right after the highlighted part, the following code should be added in order to exclude the pictures from the links returned.
(There should be more code added in order to cover all formats that is not link. For example, .pdf, .md, .jpeg, .gif...
```
int lastDot = p.toString().lastIndexOf(".");
if(lastDot == -1 || !p.toString().substring(lastDot).equals(".jpg")) {
    return result;
}
```
