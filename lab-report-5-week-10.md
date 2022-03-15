# 1st test
test file [511.md](https://github.com/ucsd-cse15l-w22/markdown-parse/blob/main/test-files/511.md)
![image](https://user-images.githubusercontent.com/51312196/158481373-5b5f34ad-8424-4b7b-bab3-93eafd6ff258.png)


## The output from my markdownparse implementation
![image](https://user-images.githubusercontent.com/51312196/158481718-a76c3c2b-9bb9-4055-9f67-6b0fe8c0a58b.png)

## The output from the implementation provided in lab 9 
![image](https://user-images.githubusercontent.com/51312196/158481407-222c02bc-c220-4ff2-8751-b788b2f2fcd6.png)

Here my implementation is giving the wrong output because my code is prompting that there is an invalid input when it encounters a symbol that is not ( after the first closing bracket ]. I would change my code to check if there is another ] after the first ] and record the location of the last ] before the next (. 

# 2nd test
test file [530.md](https://github.com/ucsd-cse15l-w22/markdown-parse/blob/main/test-files/530.md)
![image](https://user-images.githubusercontent.com/51312196/158480830-6f612d4f-94e2-414b-9a83-d1a6cfa0f4c1.png)

## The output from my markdownparse implementation
![image](https://user-images.githubusercontent.com/51312196/158481686-e3a4a626-5d69-459b-8889-472162da1493.png)

## The output from the implementation provided in lab 9 
![image](https://user-images.githubusercontent.com/51312196/158481226-77c60614-1ef6-4e43-bbfb-a4cbca4f0e61.png)

The given implementation output is wrong because .jpg should not be considered as a link, instead, it is a picture.
