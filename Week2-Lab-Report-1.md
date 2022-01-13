# **LAB REPORT 1**

Welcome to a tutorial regarding remote access anad the filesystem. 

## **STEP 1: Installing Visual Studio Code (VSCode) and OpenSSH (situational)**

If you are on a Windows device, then you must install a progam called [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). Otherwise, skip this first step.

To start, follow the link to the VSCode website: [https://code.visualstudio.com/](https://code.visualstudio.com/) to download the version that matches your operating system. After the installation has finished, click on the the icon to open a page similar to this: ![figure 1](https://i2.paste.pics/82abf8ec8a47be4742c9b0dfa192b7a1.png)

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

Don't be afraid if you see this message. It is expected to pop up when connecting to servers for the first time. Type `yes`, press enter, and type in your password (don't be alarmed if the grey bar does not move). After logging in successfully, the following messages should be received: 

![figure 3](https://i2.paste.pics/f3663c2ba2cc5af699b5cd169b557a17.png). 

Congragulations, you have successfully connected your computer's terminal (client) to a remote computer! (server).

## **STEP 3: Trying Some Commands**

Below is a compiled list of useful commands to try in your terminal: 

**some file commands**
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

## **STEP 4: Moving Files over SSH with scp**

The command `scp`, which is always run from the client, copies files from your computer to a remote computer.

---
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

Run the following command in the file's directory:  `$ scp WhereAmI.java cs15lwi22xyz@ieng6.ucsd.edu:~/` and then `javac` and `java`

The following image should be similar to what your terminal displays: ![figure 6](https://i2.paste.pics/0858ce15ad25d4afa7d43ce0cce75f4c.png)

## **STEP 5: Setting an SSH Key**

In this step, we will use `ssh` keys to use the file pair *public key* and *private key* using a program called `ssh-keygen` in place of entering our password to verify the authenticity of the host. 

---
***What* is SSH?**

SSH or Secure Shell is a service that that allows you to modify their remote servers from the internet. It's primary execution involves remotely logging in and command-line execution. 

**Setting up SSH Keys**
1. On the client, type the command `ssh-keygen`.
2. Enter a file to save the key (or simply press Enter). 
3. Enter a passphrase (or simply press Enter). Enter the passphrase again.
4. If on Windows, follow these [extra steps](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation). Specify the full path of the keys as shown above. Make a `.ssh` folder using the command `mkdir ssh` and log out.

The whole process should look something like this: ![figure 7](https://i2.paste.pics/0f360667de4b65df5b9d619c78f5f97e.png)

If on Windows the additional steps: ![figure 8](https://i2.paste.pics/3d86953de24f3d5e6241b92cc1052756.png)

**Copying the *public* key to the `ssh` directory**

The public key is the file with the `.pub` extension. Use the `scp` command to copy the `id_rsa.pub` to the authorized keys_keys folder. 

As instructed from above: ![figure 9](https://i2.paste.pics/8eaf02ebcd7e82b577b516d0d7750435.png)

## **STEP 6: Optimizing Remote Running**

As you become more familiar with remote running, efficiency becomes the next step 
1. Installing VScode
Remotely Connecting
Trying Some Commands
Moving Files with scp
Setting an SSH Key
Optimizing Remote Running
