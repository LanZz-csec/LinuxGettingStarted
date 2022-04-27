<h1 align="center">Linux Getting Started Guide</h1>

[![N|dc](https://i.hizliresim.com/3vwdudh.png)](https://discord.gg/5sYSzWQJ3Z)

<details> 
 <summary><strong>Contents (İçindekiler)</strong></summary>
 <p>

* File/Folder operations
  - [ls](#ls)
  - [clear](#clear)
  - [cd](#cd)
  - [pushd/popd](#pushd)
  - [mkdir](#mkdir)
  - [touch](#touch)
  - [ln](#ln)
  - [readlink](#readlink)
  - [cat/more/less](#cat)
  - [echo](#echo)
  - [cp](#cp)
  - [rm](#rm)
  - [mv](#mv)
  - [nano/vim/nvim](#nano)
  - [du](#du)
  - [find](#find)
  - [chmod](#chmod)
  - [./](#dotslash)

<br>
</details>
# Simple Linux Commands

## File/Folder operations

### ([▲](#top)) ls <a name="ls"></a>
`ls` command allows you to see the files in the directory you are in. Example Usage:
- -l : Shows folders in list format with their details.
- -s : Shows the size of the files in bytes.
- -a : Shows all hidden files and folders
- -h : It uses byte units of measurement while showing the file size in K/M/G/T/P.
- -A : When used with the -a parameter, hides the . and .. folders from the output.

- Suggestion: If you use the `ls` command with the `-lsah` argument, you can see the write-read-execute permissions of the files, who the files belong to, the space they occupy on the disk and all the hidden files in the directory you are in at once. Example usage:
```
┌──(root💀kali)-[~]
└─# ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos

┌──(root💀kali)-[~]
└─# ls -lsah
total 128K
4.0K drwx------ 14 root root 4.0K Jul 19 19:53 .
4.0K drwxr-xr-x 19 root root 4.0K Jul 19 19:38 ..
8.0K -rw-r--r--  1 root root 5.3K Jul 19 19:38 .bashrc
4.0K drwx------  7 root root 4.0K Jul 19 19:50 .cache
4.0K drwx------  8 root root 4.0K Jul 19 19:53 .config
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Desktop
4.0K -rw-r--r--  1 root root   55 Jul 19 19:49 .dmrc
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Documents
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Downloads
 12K -rw-r--r--  1 root root  12K Jul 19 19:41 .face
   0 lrwxrwxrwx  1 root root   11 Jul 19 19:41 .face.icon -> /root/.face
4.0K drwx------  3 root root 4.0K Jul 19 19:49 .gnupg
   0 -rw-------  1 root root    0 Jul 19 19:49 .ICEauthority
4.0K drwxr-xr-x  3 root root 4.0K Jul 19 19:49 .local
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Music
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Pictures
4.0K -rw-r--r--  1 root root  148 May 25 17:54 .profile
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Public
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Templates
4.0K -rw-r-----  1 root root    4 Jul 19 19:49 .vboxclient-clipboard.pid
4.0K -rw-r-----  1 root root    4 Jul 19 19:49 .vboxclient-display-svga-x11.pid
4.0K -rw-r-----  1 root root    4 Jul 19 19:49 .vboxclient-draganddrop.pid
4.0K -rw-r-----  1 root root    4 Jul 19 19:49 .vboxclient-seamless.pid
4.0K drwxr-xr-x  2 root root 4.0K Jul 19 19:49 Videos
4.0K -rw-------  1 root root   49 Jul 19 19:49 .Xauthority
8.0K -rw-------  1 root root 8.0K Jul 19 19:53 .xsession-errors
4.0K -rw-------  1 root root   24 Jul 19 19:49 .zsh_history
 12K -rw-r--r--  1 root root  11K Jul 19 19:38 .zshrc
```
`ls` You can also see the contents of another directory by adding any directory to the end of the command.
<p>&nbsp;</p>


### ([▲](#top)) clear <a name="clear"></a>
`clear` command deletes the text on the screen. Example usage:
```
┌──(root💀kali)-[~]
└─# clear
```
<p>&nbsp;</p>



### ([▲](#top)) cd <a name="cd"></a>
`cd` command is used to change from the current directory to another directory. Example usage:
```
┌──(root💀kali)-[~]
└─# cd /home

┌──(root💀kali)-[/home]
└─#
```
- Suggestion: If you want to go to the parent directory of the directory you are in, you can use `..` instead of typing the name of the directory.
```
┌──(root💀kali)-[~]
└─# cd ..

┌──(root💀kali)-[/]
└─#
```
- Suggestion: If you are going to return to your home directory, you can directly type `cd` instead of `cd directory`.
```
┌──(root💀kali)-[/opt]
└─# cd 

┌──(root💀kali)-[~]
└─#
```
- Suggestion: You can use `cd -` if you are going to return to the previous directory.
```
┌──(root💀kali)-[/home/can/Downloads]
└─# cd /opt/

┌──(root💀kali)-[/opt]
└─# cd - 

┌──(root💀kali)-[/home/can/Downloads]
└─#  
```
<p>&nbsp;</p>



### ([▲](#top)) pushd/popd <a name="pushd"></a>
`pushd` command, like the `cd` command, is used to move from the current directory to another directory. The difference from `cd` is that it does not forget the old directory when switching to the new directory. You can go back to the old directory with the `popd` command. Example usage:
```
┌──(root💀kali)-[/home/can/Downloads]
└─# pushd /opt

┌──(root💀kali)-[/opt]
└─# popd

┌──(root💀kali)-[/home/can/Downloads]
└─#
```
<p>&nbsp;</p>



### ([▲](#top)) mkdir <a name="mkdir"></a>
`mkdir` command is used to create folders.
- -p : forces two or more subfolders to be created. Example usage:
```
┌──(root💀kali)-[~/deneme]
└─# mkdir exfile

┌──(root💀kali)-[~/deneme]
└─# ls
exfile

┌──(root💀kali)-[~/deneme]
└─# mkdir -p file2/file3

┌──(root💀kali)-[~/deneme]
└─# ls file2
file3
```
<p>&nbsp;</p>



### ([▲](#top)) touch <a name="touch"></a>
The `touch` command is used to create files in the directory you are in, unless you specify a directory. Example usage:
```
┌──(root💀kali)-[~/deneme]
└─# touch a.txt

┌──(root💀kali)-[~/deneme]
└─# ls
klasör  a.txt

┌──(root💀kali)-[~/deneme]
└─# touch /tmp/kali.txt

┌──(root💀kali)-[~/deneme]
└─# ls /tmp
kali.txt
```
<p>&nbsp;</p>



### ([▲](#top)) ln <a name="ln"></a>
The `ln` command is used to link/short a file or a folder to another location. Hard-link is made when no parameter is given (Note: folders cannot be hard-linked)
- -s : Symbolically links. This is the commonly used parameter.
- -f : Force linking.
```
┌──(root💀kali)-[~/deneme]
└─# ls
a.txt   b.txt

┌──(root💀kali)-[~/deneme]
└─# ln a.txt c.txt

┌──(root💀kali)-[~/deneme]
└─# ls
a.txt   b.txt   c.txt

┌──(root💀kali)-[~/deneme]
└─# ln -sf b.txt d.txt

┌──(root💀kali)-[~]
└─# ln -sf /root/deneme/b.txt e.txt

┌──(root💀kali)-[~/deneme]
└─# ls -al
total 8
drwxr-xr-x.  2 root root 4096 Jan 19 10:08 .
drwxr-xr-x. 10 root root 4096 Jan 19 10:07 ..
-rw-r--r--.  2 root root    0 Jan 19 10:07 a.txt
-rw-r--r--.  1 root root    0 Jan 19 10:08 b.txt
-rw-r--r--.  2 root root    0 Jan 19 10:07 c.txt                         #hardlink
lrwxrwxrwx.  1 root root    5 Jan 19 10:08 d.txt -> b.txt                #softlink
lrwxrwxrwx.  1 root root   28 Jan 19 10:08 e.txt -> /root/deneme/b.txt   #softlink
```
<p>&nbsp;</p>




### ([▲](#top)) readlink <a name="readlink"></a>
The `readlink` command shows the exact location of the linked files and how they are linked.
- Note: it does not show files linked by hardlink.
```
┌──(root💀kali)-[~/deneme]
└─# ls -al
total 8
drwxr-xr-x.  2 root root 4096 Jan 19 10:08 .
drwxr-xr-x. 10 root root 4096 Jan 19 10:07 ..
-rw-r--r--.  2 root root    0 Jan 19 10:07 a.txt
-rw-r--r--.  1 root root    0 Jan 19 10:08 b.txt
-rw-r--r--.  2 root root    0 Jan 19 10:07 c.txt         
lrwxrwxrwx.  1 root root    5 Jan 19 10:08 d.txt -> b.txt
lrwxrwxrwx.  1 root root   28 Jan 19 10:08 e.txt -> /root/deneme/b.txt

┌──(root💀kali)-[~/deneme]
└─# readlink d.txt
b.txt

┌──(root💀kali)-[~/deneme]
└─# readlink e.txt
/root/deneme/b.txt
```

<p>&nbsp;</p>




### ([▲](#top)) cat/more/less <a name="cat"></a>
The `cat`, `more` and `less` commands are usually used to read the contents of the files given to it. Example uses:
```
┌──(root💀kali)-[~/deneme]
└─# cat a.txt

┌──(root💀kali)-[~/deneme]
└─# more a.txt

┌──(root💀kali)-[~/deneme]
└─# less a.txt
a.txt (END)
```
NOTE: You have to press the q key to exit the `less` command.

- Creating a file from scratch with `cat` and adding content (you can write whatever you want instead of SEPERATOR.)
```
┌──(root💀kali)-[~/deneme]
└─# cat <<-'SEPERATOR' > a.txt
first line
second line
third line
SEPARATOR

┌──(root💀kali)-[~/deneme]
└─# cat a.txt
first line
second line
third line
```
- Adding content below existing file:
```
┌──(root💀kali)-[~/deneme]
└─# echo "123" >> a.txt

┌──(root💀kali)-[~/deneme]
└─# cat <<-'SEPERATOR' >> a.txt
first line
pressing the second screen
third line
SEPARATOR

┌──(root💀kali)-[~/deneme]
└─# cat a.txt
123
first line
second line
third line
```
<p>&nbsp;</p>



### ([▲](#top)) echo <a name="echo"></a>
`echo` command causes what you type to it to be printed on the screen. Example usage:
- -e : Activates escape sequences.
```
┌──(root💀kali)-[~/deneme]
└─# echo Merhaba
Merhaba

┌──(root💀kali)-[~/deneme]
└─# echo -e "Merhaba\nDünya\t123"
Merhaba
Dünya   123

```
Genel kullanım amaçları:
- Dosya oluşturmak
```
┌──(root💀kali)-[~/deneme]
└─# echo "" > b.txt

┌──(root💀kali)-[~/deneme]
└─# ls
klasör  a.txt  b.txt
```
NOTE: The `>` operator you see here, if there is a file, deletes everything in the file and writes the content in the output that you wrote to the `echo` to the file. If the file does not already exist, it creates a file and writes the content you write to `echo`.
```
┌──(root💀kali)-[~/deneme]
└─# cat b.txt

┌──(root💀kali)-[~/deneme]
└─#
```
- Dosyaya ekleme yapmak
```
┌──(root💀kali)-[~/deneme]
└─# echo "abc" >> c.txt

┌──(root💀kali)-[~/deneme]
└─# echo "21" >> c.txt

┌──(root💀kali)-[~/deneme]
└─# cat c.txt
abc
21

┌──(root💀kali)-[~/deneme]
└─#
```
NOTE: The `>>` operator we use here is used to append the output to the last line without deleting the contents of the file.
<p>&nbsp;</p>



### ([▲](#top)) cp <a name="cp"></a>
The `cp` command is used to copy files.
Commonly used arguments:
- -r : Copies a folder.
- -f : Force copy.
- -v : When copying a folder, it outputs which files were copied.
- -i : asks before overwriting. Example usage:
```
┌──(root💀kali)-[~/deneme]
└─# cp -r klasör ~/
```
Important informations:
- ~/ : It is your home folder, that is, it is used to specify the /root directory since we are root now.
- ./ : it is used to specify the directory we are currently in.
<p>&nbsp;</p>



### ([▲](#top)) rm <a name="rm"></a>
The `rm` command is used to delete the file at the address you provided.
Commonly used arguments:
- -r : Deletes the folder.
- -f : Forces deletion.
- -v : While deleting more than one file, after deleting each file, it informs that I deleted the following file.
- -i : Asks if you are sure to delete before each deletion. Example usage:
```
┌──(root💀kali)-[~/deneme]
└─# rm -rf klasör

┌──(root💀kali)-[~/deneme]
└─# ls
a.txt  b.txt  c.txt
```
<p>&nbsp;</p>



### ([▲](#top)) mv <a name="mv"></a>
The `mv` command is used to move files and folders.
Commonly used arguments:
- -v : When moving more than one file, after moving each file, it informs that I have moved the following file.
- -f : Forces a move.
- -i : asks before overwrite. Example usage:
```
┌──(root💀kali)-[~/deneme]
└─# mv a.txt ..

┌──(root💀kali)-[~/deneme]
└─# ls
b.txt  c.txt
```
NOTE : If you put -- in mv it will rename the file.
```
┌──(root💀kali)-[~/deneme]
└─# mv c.txt -- d.txt

┌──(root💀kali)-[~/deneme]
└─# ls
b.txt  d.txt
```
<p>&nbsp;</p>



### ([▲](#top)) nano <a name="nano"></a>
`nano` is a terminal based text editor.
- set nano filename to open or create a specific file in nano.
- Press ctrl+x to exit nano, press y to save, type the file name you want and press enter, ctrl+c to cancel, press n to close without saving.

```
┌──(root💀kali)-[~]
└─# nano x.txt
```
<p>&nbsp;</p>



### ([▲](#top)) vi/vim
`vi` is a slightly more complex version of `nano`.
- There are key combinations to save and exit. (:q = Exit | :wq = Exit with saving | :q! = Exit without saving)
- For more, see: https://linuxacademy.com/site-content/uploads/2019/05/vim-1.png
<p>&nbsp;</p>



### ([▲](#top)) nvim
We can call it the shaped slug of `vim`. You can install it as a separate package from Vim.
<p>&nbsp;</p>



### ([▲](#top)) du <a name="du"></a>
The `du` command is a command to show the size of a particular folder content or a file.
- -s : Shows only the size of the folder you want. If you don't use this parameter, the du command will scan subfolders as well.
- -h : It uses byte units of measurement while showing the file size in K/M/G/T/P.
- -S : This parameter collects only the volume of the files under that folder.
```
┌──(root💀kali)-[~]
└─# du -s .
23952124	.

┌──(root💀kali)-[~]
└─# du -sh /var/log
3.0G     /var/log

┌──(root💀kali)-[~]
└─# du -shS /var/log
6.9M     /var/log
```



### ([▲](#top)) find <a name="find"></a>
The `find` command is used to search for files.
- -type : Type of content searched ( f: File(file) | d: directory(folder) | l: symlink(symbolic link) )
- -name : The name of the searched content (when used as \*.extension, it searches for files with that extension)
- -perm : Lists files with the specified permission.
- -executable : Lists executable files, preceded by "!" If set, it will only show files that cannot be run.
- -exec : Runs the desired command with the found outputs.
- -size <number>K/M/G/T/P : Lists files with the specified size.
- -atime <number> : Lists files with specified access date.
- -ctime <number> : Lists files with specified modification date.
* NOTE: If you know only a part of the file name (for example, if the file is named flag-1-of-3.txt, you only know that the filename has "flag" in it);
   The -name part should be `-name "flag*"`. Example usage:
```
┌──(root💀kali)-[~]
└─# find /home -name "*.txt" -type f
...
/home/can/a.txt
/home/can/b.txt
...

┌──(root💀kali)-[~]
└─# find /home -type f -perm 0644 
...
/home/can/.cache/thumbnails/large/983e8399cacb80336e937666d0fda42e.png
...

┌──(root💀kali)-[~]
└─# find /home -size +1G -exec du -sh {} \;
6.2G	/home/can/.local/share/Steam/steamapps/common/Euro Truck Simulator 2/base.scs
2.0G	/home/can/.local/share/Steam/steamapps/common/Euro Truck Simulator 2/dlc_lunar_new_year.scs

┌──(root💀kali)-[~]
└─# find / -type f -perm /u=s 2>/dev/null
```
The above command is generally used to perform "privilege escalation". You can see how in the CTF article at the end of the page.
<p>&nbsp;</p>



### ([▲](#top)) chmod <a name="chmod"></a>
The `chmod` command is used to set the permissions of files.
- +x : Allows the file to be run.
- -x : Removes executable permission from file.
NOTE: You can find more information on how to use `chmod` by typing `chmod cheat sheet` into google. Or you can check out the calculator [at](https://chmodcommand.com/) or check out [this photo](https://miro.medium.com/max/800/1*McJxuQAO-fLpz-7S4Cr4pA.gif) to see exactly what numbers do in `chmod`. Example usage:
```
┌──(root💀kali)-[~]
└─# chmod 777 a.sh

┌──(root💀kali)-[~]
└─# chmod -x a.sh
```
<p>&nbsp;</p>


### ([▲](#top)) ./ <a name="dotslash"></a>
With `./` you can run a file with executing authority in the directory you are in. The execution authority appears as "x" in the output of `ls -lsah`. Example usage:
```
┌──(root💀kali)-[~]
└─# ./a.sh
##########################
# Join the Community     #
# .gg/5sYSzWQJ3Z         #
##########################

┌──(root💀kali)-[~]
└─#
```
<p>&nbsp;</p>