## Everything about chmod command in Linux

### What does it do?
```
chmod command is used to change permissions of a given file according to a certain mode which might be a set of octal characters or a set of alphabetical characters.
In Unix and Unix-like operating systems, chmod is the command and system call used to change the access permissions and the special mode flags (the setuid, setgid, and sticky flags) of file system objects (files and directories). Collectively these were originally called its modes,[1] and the name chmod was chosen as an abbreviation of change mode.
```

### Command Syntax
User refers to the owner of the file, as a reminder that the symbolic form of the command uses "u".

Usually implemented options include:
* -R Recursive, i.e. include objects in subdirectories.
* -v verbose, show objects changed (unchanged objects are not shown).

To view the file mode, the ls or stat commands may be used:
```
$ ls -l findPhoneNumbers.sh
-rwxr-xr--  1 dgerman  staff  823 Dec 16 15:03 findPhoneNumbers.sh
$ stat -c %a findPhoneNumbers.sh
754
```

The r, w, and x specify the read, write, and execute access (the first character of the ls display denotes the object type; a hyphen represents a plain file). The script findPhoneNumbers.sh can be read, written to, and executed by the user dgerman; read and executed by members of the staff group; and only read by any other users.

The main parts of the chmod permissions:
```
For example: rwxr-x---
```

Each group of three characters define permissions for each class:

* the three leftmost characters, rwx, define permissions for the User class (i.e. the file owner).
* the middle three characters, r-x, define permissions for the Group class (i.e. the group owning the file)
* the rightmost three characters, ---, define permissions for the Others class. In this example, users who are not the owner of the file and who are not members of the Group (and, thus, are in the Others class) have no permission to access the file.

### Numerical permissions

The chmod numerical format accepts up to four digits. The three rightmost digits define permissions for the file user, the group, and others. The optional leading digit, when 4 digits are given, specifies the special setuid, setgid, and sticky flags. Each digit of the three rightmost digits represents a binary value, which controls the "read", "write" and "execute" permissions respectively. A value of 1 means a class is allowed that action, while a 0 means it is disallowed.

| # | Sum | rwx | Permission |
| :-: | :-: | :-: | :-: |
| 7 | 4(r) + 2(w) + 1(x) | rwx | read, write and execute |
| 6 | 4(r) + 2(w) | rw- | read and write |
| 5 | 4(r)        + 1(x) | r-x | read and execute |
| 4 | 4(r) | r-- | read only |
| 3 |        2(w) + 1(x) | -wx | write and execute |
| 2 |        2(w)	 | -w- | write only |
| 1 |               1(x) | --x | execute only |
| 0 |  0 | --- | none |

For example, 754 would allow:

* "read" (4), "write" (2), and "execute" (1) for the User class; i.e., 7 (4 + 2 + 1).
* "read" (4) and "execute" (1) for the Group class; i.e., 5 (4 + 1).
* Only "read" (4) for the Others class.

A numerical code permits execution if and only if it is odd (i.e. 1, 3, 5, or 7). A numerical code permits "read" if and only if it is greater than or equal to 4 (i.e. 4, 5, 6, or 7). A numerical code permits "write" if and only if it is 2, 3, 6, or 7


### Numeric example
Change permissions to permit members of the programmers group to update a file:
```
$ ls -l sharedFile
-rw-r--r--  1 jsmith programmers 57 Jul  3 10:13  sharedFile
$ chmod 664 sharedFile
$ ls -l sharedFile
-rw-rw-r--  1 jsmith programmers 57 Jul  3 10:13  sharedFile
```

Since the setuid, setgid and sticky bits are not specified, this is equivalent to:
```
$ chmod 0664 sharedFile
```

### Symbolic modes

Classes of users are used to distinguish to whom the permissions apply. If no classes are specified "all" is implied. The classes are represented by one or more of the following letters:

| Reference |	Class |	Description |
| :-: | :-: | :-: | 
| u |	user |	file owner |
| g |	group	| members of the file's group |
| o |	others |	users who are neither the file's owner nor members of the file's group |
| a |	all |	all three of the above, same as ugo |
| (empty) |	default |	same as "all", except that bits in the umask will be unchanged |

The chmod program uses an operator to specify how the modes of a file should be adjusted. The following operators are accepted:

| Operator |	Description |
| :-: | :-: | 
| + |	adds the specified modes to the specified classes |
| - |	removes the specified modes from the specified classes |
| = |	the modes specified are to be made the exact modes for the specified classes |

The modes indicate which permissions are to be granted or removed from the specified classes. There are three basic modes which correspond to the basic permissions:

| Mode |	Name |	Description |
| :-: | :-: | :-: |
| r |	read |	read a file or list a directory's contents |
| w |	write |	write to a file or directory |
| x |	execute |	execute a file or recurse a directory tree |
| X |	special execute |	which is not a permission in itself but rather can be used instead of x. It applies execute permissions to directories regardless of their current permissions and applies execute permissions to a file which already has at least one execute permission bit already set (either User, Group or Others). It is only really useful when used with + and usually in combination with the -R flag for giving Group or Others access to a big directory tree without setting execute permission on normal files (such as text files), which would normally happen if you just used chmod -R a+rx ., whereas with X you can do chmod -R a+rX . instead |
| s |	setuid/gid |   |
| t |	sticky |   |


| Symbolic Notation |	Numeric Notation	| English |
| :-: | :-: | :-: | 
| ---------- |	0000 |	no permissions |
| -rwx------ |	0700 |	read, write, & execute only for owner |
| -rwxrwx--- |	0770 |	read, write, & execute for owner and group |
| -rwxrwxrwx |	0777 |	read, write, & execute for owner, group and others |
| ---x--x--x |	0111 |	execute |
| --w--w--w- |	0222 |	write |
| --wx-wx-wx |	0333 |	write & execute |
| -r--r--r-- |	0444 |	read |
| -r-xr-xr-x |	0555 |	read & execute |
| -rw-rw-rw- |	0666 |	read & write |
| -rwxr----- |	0740 |	owner can read, write, & execute; group can only read; others have no permissions |

### Permissions explained
Each file on your system has a certain set of permissions associated with it. There are three types of permissions that can be associated with a file: </br>
Read permissions denoted by 'r' </br>
Write permission denoted by 'w' </br>
Execute permissions denoted by 'x' </br>

You can check the permissions of a given file by using the following command:
```
ls -l <filename>
```

The string rwxr-xr-x represents the permissions of this file. It can further be divided in to three parts containing three characters each and we get the three components of file permissions in linux:

<b> Owner permissions(rwx) - </b> Permissions for the user who created the file. rwx means that this user can read, write and execute this file. </br>
<b> Group permissions(r-x) - </b> Permissions for other users in the file's group. r-x means that the user can read and execute the file but cannot write to it. </br>
<b> Other user permissions(r-x) - </b> Permissions for users who do not belong to the above categories. In this case these are the same as the group permissions. </br>

### Permission modes 

There are two types of modes that can be given as input to the chmod command:

#### Set of octal characters
Consider the owner permissions in the example. They are represented by rwx. Now consider r=4, w=2, x=1. Therefore rwx = 4 + 2 + 1 = 7. Therefore the octal character 7 represents that the user has the permissions to read write and execute the file.  

Let us take another example. The group permissions in the this case is r-x. As we already know r=4 and x=1. We denote the empty slot by 0. Octal representation for r-x = 4 + 0 + 1 = 5. Therefore the octal character 5 represents that the user has permissions to read and execute the file but it cannot write to the file.

Similarly the other users' permissions evaluate to 5 in our case. Therefore the complete permissions of this file can be represented by the octal number 755.

To change the permissions of a file using the octal number mode we run:
```
chmod <octal number> <filename>
```

Now we want to change the permissions for this file to say, rw--r-xr--.

Owner permissions(rw-) = 4 + 2 + 0 = 6

Group permissions(r-x) = 4 + 0 + 1 = 5

Other user's permissions(r--) = 4 + 0 + 0 = 4

Now, for changing the file permissions we run:
```
chmod 654 chmod.txt
```

### Values of r,w and x.
In the above sections we assumed values r=4, w=2 and x=1. Now let us discuss how these are derived. The three character permission string(rwx, r-x or r--) is nothing but a three bit binary string. Now by convention the first bit specifies read permission, second bit specifies the write permission and the third bit specifies the execute permission. If that bit is one, the user has that permission. Now we denote read by 'r' and if read is allowed there is a 1 on the first bit, which evaluates to 4 if the other bits are 0. Similarly the values for 'w' and 'x' can be calculated.

### Set of alphabetical characters
We would add three more characters to this list. First one is 'a' which represents a union of all the users that is owner, group users and others. The second character is '+' which is specified to add a permission to a user, and the third character is '-' which is specified to revoke a permission from the user.

Now for changing file permission we run:
```
chmod <user type(u/g/o/a)><add/revoke(+/-)><permission type(r/w/x)>
```

To change the owner permissions of a file to read and write, we run:
```
chmod u+rw chmod.txt
```

To give a write permission to everyone, we run:
```
chmod a+w chmod.txt
```

To remove the write permission for others, we run:
```
chmod o-w chmod.txt
```

To change the permissions of a directory, we run:
```
chmod <permission> <directory name>
```

To change the permissions of a directory with its files and sub-directories recursively, we run:
```
chmod -R <permission> <directory name>
```


