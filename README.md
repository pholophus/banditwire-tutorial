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

LEVEL 6 ---> LEVEL 7
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The target of this level is to learn to find a file based on its owner and group. 

Find file by group
------------------
The syntax is:
find directory-location -group {group-name} -name {file-name}

Where,
directory-location : Locate the file in this directory path.
-group {group-name} : Find the file belongs to group-name.
-name {file-name} : The file name or a search pattern

Find file owned by user
-----------------------
The syntax is:
find directory-location -user {username} -name {file-name}

Where,
directory-location : Locate files or directories in this directory location.
-user { user-name } : Find the file belongs to user.
-name {file-name} : File name or pattern.

So the full command for this level is:
find / -group bandit6 -user bandit7 -size 33c

Password : HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

LEVEL 7 ---> LEVEL 8
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal for this level is to learn search a keyword in a file. The command that can be use for this is the GREP command.

Grep is an acronym that stands for Global Regular Expression Print.
The grep command consists of three parts in its most basic form. The first part starts with grep, followed by the pattern that you are searching for. After the string comes the file name that the grep searches through.

grep "millionth" data.txt

Result: 
-------
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV

LEVEL 8 ---> LEVEL 9
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal of the level is to search for a keyword where it only occurs once.

To search for the keyword, we can use the command UNIQ, the UNIQ command filters out repeated lines in a file. But it can only detect adjacent duplicate lines. Also to only print out uniq lines, we will use the option -u. And the keywords in the file is not in order. So we need to sort the file first before we can use the uniq command. The command to sort the data  inside the file is SORT. SORT command is used to sort a file, arranging the records in a particular order. By default, the sort command sorts file assuming the contents are ASCII. Using options in sort command, it can also be used to sort numerically.

cat data.txt | sort | uniq -u

Result:
-------
password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

LEVEL 9 ---> LEVEL 10
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Strings : Print the strings of printable characters in files.
strings data.txt
Password : truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

LEVEL 10 ---> LEVEL 11
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal of this level is to learn encode and decode a file. To encode or decode standard input/output or any file content, Linux uses base64 encoding and decoding system.

Syntax:
base64 [OPTION] [INFILE] [OUTFILE]

To decode, we are going o use 

-d or –decode

base64 -d data.txt

Result
------
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

LEVEL 11 ---> LEVEL 12
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal of this level is to learn to shift/replace characters according to a number. And for this question, we need to shift the characters by 13.

The tr command in UNIX is a command line utility for translating or deleting characters. t supports a range of transformations including uppercase to lowercase, squeezing repeating characters, deleting specific characters and basic find and replace.

To shift/replace the characters by thirteen, we will write the first set as [a-z], this will be the input, the second set we will write as [n-za-m], this will be the output. TR command will convert the letter a with n, b with o and so on. 

echo "5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh" | tr '[a-z][A-Z]' '[n-za-m][N-ZA-M]'
5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

LEVEL 12 ---> LEVEL 13
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The target of this level is to learn about file compression. The question says that the file is a hexdump of a file that has been repeatedly compressed. So firstly we will need to use command 'xxd' to reverse hexdump. After that, we will be given unreadable characters, because the question says the file was compressed repeatedly, so to know what kind of compression it is, we will use the 'file' command to get the details of the file.

For this question, there are 3 types of compression,

First: bzip2
------------
data2: bzip2 compressed data, block size = 900k
bzip2 -d data.bz2

Second: tar
-----------
data5.bin: POSIX tar archive (GNU)
tar -xvf data5.tar

Third: gzip
-----------
gzip -d data4.gz
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix

Result:
-------
Password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

LEVEL 13 ---> 14
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal for this level is to learn how to connect using private SSH key.

First we need to save the private SSH key in a pem file. A PEM file is a Base64-encoded certificate file used to authenticate a secure website. It may contain a private key, certificate authority (CA) server certificate, or other various certificates that make up the trust chain. PEM files typically imported from a Unix-based Apache Web server and compatible with OpenSSL applications.

Later to connect, we will type

ssh -i "name of pem file".pem bandit14@ bandit.labs.overthewire.org -p 2220

LEVEL 14 ---> 15 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The goal of this level is to send info through a connection. To do this, we will use the command nc. ncat or nc is networking utility with functionality similar to cat command but for network. It  is a general purpose CLI tool for reading, writing, redirecting data across a network. It is  designed to be a reliable back-end tool that can be used with scripts or other programs.

echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc 127.0.0.1 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr

LEVEL 15 ---> LEVEL 16
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | openssl s_client -connect 127.0.0.1:30001 -ign_eof
cluFn7wTiGryunymYOu4RcffSxQluehd

LEVEL 16 ---> LEVEL 17
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
nmap -sV -p 31000-32000 127.0.0.1  -v
 echo "cluFn7wTiGryunymYOu4RcffSxQluehd" | openssl s_client -connect 127.0.0.1:31790 -ign_eof
 
 LEVEL 17 ---> LEVEL 18
 -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
 ssh -i pem-file.pem bandit17@bandit.labs.overthewire.org -p 2220

