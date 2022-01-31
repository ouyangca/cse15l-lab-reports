# Week 4 Lab Report: Fixing bugs

## Code change #1
* code change diff
![image](https://user-images.githubusercontent.com/51312196/151722820-a42f2c83-47fb-4d8a-ac1d-4b316cd03610.png)
* failure-inducing input [test2](https://github.com/ouyangca/markdown-parse/blob/main/test2_file.md)
* symptom
![image](https://user-images.githubusercontent.com/51312196/151723340-cf61e9fc-0645-4d6a-aa1e-7e8cf8cf8387.png)
> We are assuming that a pair of brackets always come before the parenthesis
> A failure inducing input is when parenthesis come without a complete brakets proceeding them
> The symptom is the array list cannot collect the correct information since it keeps searching for brackets while the input does not provide
> By adding code that returns an empty list when parenthesis comes first, we can avoid the error
---
## Code change #2
* code change diff
![image](https://user-images.githubusercontent.com/51312196/151722479-10cd6bec-e53f-4887-a3d0-e8cdbc7c184b.png)
* failure-inducing input [test3](https://github.com/ouyangca/markdown-parse/blob/main/test3-file.md)
* symptom
![image](https://user-images.githubusercontent.com/51312196/151723356-36c12944-e7ef-4686-8d09-357b9da36ef4.png)
> We are assuming that the content within the parenthesis is a link
> A failure inducing input is when the content is not a link
> the output will contain the inputs even when it is not an actual link
> We add code to check if the content is a link (checking .html ending) and ignore the ones including jpg and pdf formats

---
## Code change #3
* code change diff
![image](https://user-images.githubusercontent.com/51312196/151722807-11c3dd33-cb45-42c1-9d5a-15806e6d51d2.png)
* failure-inducing input [test4](https://github.com/ouyangca/markdown-parse/blob/main/test4-file.md)
* symptom
![image](https://user-images.githubusercontent.com/51312196/151723376-a0568040-4d4c-4bf6-9c65-549450f04534.png)
![image](https://user-images.githubusercontent.com/51312196/151723237-ffa8a292-278e-4170-b8ad-fa630e5bd212.png)
> We were assuming that all inputs will have complete elements
> A failure inducing input is when some parenthesis or brakets is missing
> The symptom will be infinite loop to search for certain elements until the index get out of bounds
> We check for the index and stops the program before it gets out of bounds
