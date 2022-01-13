# **LAB REPORT 1**

## **STEP 1: Installing Visual Studio Code (VSCode)** 

Follow the link to the VSCode website: [https://code.visualstudio.com/](https://code.visualstudio.com/) to download the version that matches your operating system. After the installation has finished, click on the the icon to open a page similar to this: ![figure 1](https://i2.paste.pics/82abf8ec8a47be4742c9b0dfa192b7a1.png)

## **STEP 2: Remotely Connecting**

Begin by looking up your course respective ieng6 account using this [link](https://sdacs.ucsd.edu/~icc/index.php). The account should look something like this: `cs15lwi22xyz@ieng6.ucsd.edu` (with `xyz` replaced with your account's letters.) You will need to reset your password in order to activate and access your account.  

In VSCode, open a terminal by locating it at the menu option and clicking "New Terminal."   

![figure 2](https://i2.paste.pics/9ba2b11ebc8c6c33eff7d30d57993a0d.png) 

In the terminal, run the following command: `ssh cs15lwi22xyz@ieng6.ucsd.edu` to prompt the following message: 
```ssh cs15lwi22xyz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

Do not be afraid if you see this message. It is expected to pop up when connecting to servers for the first time. Type `yes`, press enter and then type in your password. After logging in successfully, the following messages should be received: 

![figure 3](https://i2.paste.pics/f3663c2ba2cc5af699b5cd169b557a17.png). 

Congragulations, you have successfully connected your computer's terminal (client) to a remote computer! (server).

## **STEP 3: Trying Some Commands**

Below is a compiled list of useful commands to try in your terminal: 

**file commands**
* `ls` - directory listing
* `ls -al` - formatted listing with hidden files
* `cd dir` - changes directory to *dir*
* `cd` changes directory to home
* `pwd` - shows current directory 
* `mkdir dir` - creates a directory *dir*
* `exit` or crtl + D - logs out of the remote server

**commands to observe**
* `ls cat /home/linux/ieng6/cs15lwi22/public/hello.txt` 
* `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~`

Some examples of running these commands are: 

![figure 4](https://i2.paste.pics/8c3a33f1d29a63fd0bbb55f6a9d5b98e.png)

![figure 5](https://i2.paste.pics/60660f831aa8dee2df8b87f53a944407.png)

## ** STEP 4: Moving Files over SSH with scp

The command `scp`, which is always run from the client, copies files from your computer to a remote computer.

We begin by creating a file called `WhereAmI.java` which has the following contents: 
```
class WhereAmI 
{
  public static void main(String[] args) 
  {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

Run the following command in the file's directory:  

`$ scp WhereAmI.java cs15lwi22xyz@ieng6.ucsd.edu:~/` 



1. Installing VScode
Remotely Connecting
Trying Some Commands
Moving Files with scp
Setting an SSH Key
Optimizing Remote Running
