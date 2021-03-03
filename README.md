# banditwire-tutorial

---LEVEL 0---
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of this level is to learn on how to use SSH. The host that will be connected is bandit.labs.overthewire.org on port 2220 with the username bandit0 and password bandit0.

The command line to connect to bandit.labs.overthewire.org with username bandit 0 is

ssh bandit0@bandit.labs.overthewire.org -p2220

Later enter the password bandit0. After successfully login, it will appear as below

![lvl 0 - result](https://user-images.githubusercontent.com/41103533/109589985-2abeb300-7b46-11eb-83d3-b31ce3187bf4.PNG)


LEVEL 0 ---> LEVEL 1
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of level 0 ---> level 1 is to search a file named readme is the bandit0 directory. Then we need to read the file to retrieve the password to login into bandit1.

Firstly we will try to list out all the files in the current directory, to do that just type ls. The file readme will appear. Then to read the content of file readme, type cat readme.

Below are the steps:

![step 1 (ls and cat)](https://user-images.githubusercontent.com/41103533/109590510-0fa07300-7b47-11eb-9760-7b6ed939821f.PNG)

From the readme file, we know that the password is boJ9jbbUNNfktd78OOpsqOltutMc3MY1, so we can use this to login as bandit1.


LEVEL 1 ---> LEVEL 2
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of level 1 ---> level 2 is to learn read dash files. Sometimes you maybe have to handle files with a dash (-) as first character from Linux command line. It can be difficult, because the script thinks the marks after the dash are parameters.

So to read dash files, we will need to attach the directory. To know the current directory, we can use 'pwd'. Below is an example:

![step 1](https://user-images.githubusercontent.com/41103533/109592790-d10cb780-7b4a-11eb-9036-8581e6b9a8c8.PNG)

As you can see at the above image, when we type cat /home/bandit1/- then only we are able to read the content of the file.

LEVEL 2 ---> LEVEL 3
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of level 2 ---> level 3 is to read file which its name has spaces. To read file name that has spaces, insert the character '\' at each space. Below shows how to do it.

![method 1](https://user-images.githubusercontent.com/41103533/109596246-d0771f80-7b50-11eb-935e-2738384b9570.PNG)

LEVEL 3 ---> LEVEL 4
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of level 3 ---> level 4 is to find hidden files in a directory. To list out all files in a directory, can use the command ls -a. Below shows how to do it.

![method 1](https://user-images.githubusercontent.com/41103533/109596518-61e69180-7b51-11eb-9001-70eef0f50c1a.PNG)

pIwrPrtPN36QITSp3EQaw936yaFoFgAB

LEVEL 4 ---> LEVEL 5
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goal of level 4 is to learn check the type of files in a director and to know which file is human readable file. To know if a file is human readable, it uses ASCII text.

To know the details of a file, we can use the command file, it determine the file type. Becasue in the directory there are about 10 files, rather than searching each one, we can use the * which will automatically search all files based on its number.

![method 1](https://user-images.githubusercontent.com/41103533/109768656-25d82d00-7c34-11eb-9425-7c9d007b05a5.PNG)


From the image above, we know that the only file with ASCII type is file 7, so we will read file 07 and retrieve the password. 

Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

LEVEL 5 ---> LEVEL 6
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The goals of level 5 is to learn to find a file based on several things such as size etc. The question ask to search a file where has all of the following properties:

human-readable
1033 bytes in size
not executable

For this, we can use the file command, first to search file by file size, the file size is 1033 in bytes, so we type file . -size 1033c, the suffix c represents byte, the other available suffixes to our disposal are:
b - 512-byte blocks (this is the default if no suffix is used)
c - bytes
w - two-byte words
k - Kilobytes
M - Megabytes
G - Gigabytes

The next condition is that the file must not be executable, so we just type ! -executable.

Lastly is the human readable, humans read in unicode ASCII, so we will find file type with ASCII.

Below is the code

![method 1](https://user-images.githubusercontent.com/41103533/109790311-398f8d80-7c4c-11eb-8f1c-2abae51ef26f.PNG)


Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

Password : HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs


