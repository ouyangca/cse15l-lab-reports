# Tutorial: Logging into your 15L account on ieng6 

---
## Installing VScode
First of all, let's install [VSCode](https://code.visualstudio.com/) onto your personal computer.
*Click on the link to download.*
When VSCode has been installed correctly, run it and you should see a page like this.
![image](https://user-images.githubusercontent.com/51312196/149611968-e323279e-99f4-4122-b791-1838f9bc2a85.png)

---
## Remotely Connecting
Now we can start connecting to the server!
We will need to find your account name first -> [Find Account](https://sdacs.ucsd.edu/~icc/index.php)

Now replace the brackets and the words inside it with your account name
```
$ ssh cs15lwi22{insert your account here}@ieng6.ucsd.edu
```

Enter the above line into your VSCode terminal, and it should prompt you for a password.
Press enter after you entered your password, and you should see something like this when you have successfully connected:
![image](https://user-images.githubusercontent.com/51312196/149612197-9b1968e7-de6e-4ca1-b0e8-d975b59f66ad.png)


---
## Trying Some Commands
*Note: enter `exit` or use `Ctrl_D` in terminal to disconnect from the server*
Try the following commands on the server (and on your local computer) and see what happens:

`cd`
`ls`
`pwd` 
`mkdir`
`cp`

More commands:
```
cd ~
cd
ls -lat
ls -a
ls <directory> where <directory> is /home/linux/ieng6/cs15lwi22/cs15lwi22abc, where the abc is one of the other group members’ username
cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/
cat /home/linux/ieng6/cs15lwi22/public/hello.txt
```
![image](https://user-images.githubusercontent.com/51312196/149612484-fdb9ab3d-feb7-4148-b42f-b1b6d0ada0fb.png)

---
## Moving Files with scp
Create a file on your local computer named **WhereAmI.java** with the following content:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
Using VSCode, logout of the server and go to your local directory that contains the file **WhereAmI.java**.
Run the following command:
`scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/`

Now run the file using `javac` and `java` on the server and see what happens.
![image](https://user-images.githubusercontent.com/51312196/149612525-b4874bd3-5b3f-4d49-bd17-1725eb4e3f81.png)

---
## Setting an SSH Key

![image](https://user-images.githubusercontent.com/51312196/149612551-f667fc46-1555-4889-8ec2-7e735768353b.png)
![image](https://user-images.githubusercontent.com/51312196/149612559-259012b0-90d6-475a-99ca-8837a7a2deb1.png)


---
## Optimizing Remote Running
Try the following code and see what happens
```
$ ssh cs15lwi22@ieng6.ucsd.edu "ls"
```
```
$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```

> Note: 
> Everything within "" will run as a single execution
> use ; to include multiple commands on the same line
> use `↑` and `↓` to select pervious commands in the terminal


