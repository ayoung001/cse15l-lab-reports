# **LAB REPORT 3: "It Works on my Machine"**

Setting up the `ssh` command in ieng6 more efficiently. 

## **Step 1: ~/.ssh/config**

We locate our file named `/.ssh/config` to create a username for our ieng6 accounts when logging in. 

To find where `~/.ssh/config` is located, we locate it through our file explorer by typing: `/Users/(computerusername)\~\.ssh\config/` as seen in this image: 

![figure 1](3figure1.png) 

or by typing the command `code ~/.ssh/config` in command prompt: 

![figure 2](3figure2.png) 

From here, we can use VSCode to modify the file `config` to type in the following: 

```
Host ieng6
    Host ieng6
    HostName ieng6.ucsd.edu
    User cs15lwi22ahn 
```

![figure 3](3figure3.png)

We can now use the command `ssh ieng6` to use the key to log you in with the username specified from the public key. 