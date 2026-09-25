

[[MOC - IBM Data Engineering]] #Linux #Shell


What is Unix?

A family of operating systems:
- Oracle Solaris
- FreeBSD
- HP-UX
- IVM AIX
- Apple macOS

What is Linux?

Family of Unix-like OSs: usually specific distribution
- Originally developed as an effort to create a free, open-source Unix OS 

Features
- Free and open source
- Secure
- Multi-user
- Multitasking
- Portability

Beginnings:

| 1980 | GNU Developed               |
| ---- | --------------------------- |
| 1991 | Linux Kernel                |
| 1992 | Linux OS born via GNU+Linux |
| 1996 | Tux                         |

Linux use cases today
- Android
- Supercomputers
- Data centers and cloud services
- PCs
[[Introduction to Linux Commands and Shell Scripting]][[IBM Data Engineering]]
--------------------------
What is Linux distribution?
- A specifi flavor of Linux OS
- Also referred to as Distro
- Linux kernel is the core component
- There are hundres of Linux distros 

Linux distro differences
- System utilities
- GUI
- Shell commands
- Support types: Community vs enterprise
- Long-term support (LTS) vs rolling release

**Debian First release in 1993, 0.01 - First stable release in 1996 1.1**
**Ubuntu first release in 2004 - 4.10**
**Red Hat Linux: Stable, reliable, managed by Red Hat **
**Fedora is known as a stable operating system**
**SUSE Linux Enterprise (SLE): fo server and desktop**
**Arch Linux Do-it-yourself approach 

Overview of Linux Architecture

![[Pasted image 20260905234221.png|641]]


### Overview of Linux Architecture


UI 

![[Pasted image 20260906171646.png|527]]

![[Pasted image 20260906171709.png|525]]

![[Pasted image 20260906171740.png|521]]

![[Pasted image 20260906171828.png|525]]

![[Pasted image 20260906171928.png|532]]

Linux Shell

Mainly used to: 
- Move and copy files
- Write to and read from files 
- Extract and filter data 
- Search for data

Shells: 
- Bash 
- Zsh

![[Pasted image 20260906201759.png|561]]


![[Pasted image 20260906201916.png|554]]

LINUX FILESYSTEM
/
├── home
│   ├── project
│   └── theia
├── bin
├── etc
├── usr
├── var
└── tmp

pwd        # muestra dónde estoy
ls         # lista contenido del directorio actual
ls /home   # lista contenido de /home
ls /       # lista directorios desde la raíz

`/` = raíz del sistema  
`/home/project` = ruta absoluta  
Directorio = carpeta  
Subdirectorio = carpeta dentro de otra carpeta
### 1. Tab Completion

Sirve para **autocompletar comandos, archivos y directorios** usando `Tab`.

Ejemplo:

```
cd P
```

Si `Pictures` es la única carpeta que empieza con `P`, al presionar `Tab` queda:

```
cd Pictures/
```

Si hay varias opciones con el mismo inicio, por ejemplo:

```
Documents
Downloads
```

Entonces:

```
cd Do
```

no puede autocompletar todavía.

Pero con:

```
cd Doc
```

- `Tab`

queda:

```
cd Documents/
```

También sirve para rutas largas:

```
cd Documents/python-examples/
```

![[Pasted image 20260907003233.png]]

---
### Module 2

What is a shell? 
- User interface for running commands 
- INteractive language
- Scripting language

A sea of shells
- Default shell is usually Bash
- Many other shells, including sh, ksh, tcsh, zch, and fish
- This course uses bash

$ printenv SHELL
$ bash in SN | outside SN you can use >

Shell command applications
- Getting information
- Navigating and working with files and directories 
- printing file and string contents
- Compression and archiving
- Performing network operations
- Monitoring performance and status
- Running batch jobs

![[Pasted image 20260910223211.png]]

![[Pasted image 20260910223225.png]]

![[Pasted image 20260910223254.png]]

![[Pasted image 20260910223329.png]]

![[Pasted image 20260910223403.png]]

![[Pasted image 20260910223427.png]]



Informationla Commands
- Display user information 
- whoami
- id: id -u | id -u -n
- uname | uname -s -r (Nname of OS)
- df (disk free) : df -h ~
- ps (process status): ps -e
- top (tables of processes) : top -n 3
- echo (print string or variable): $ echo "hello" | $ echo $PATH
- date: displays date and time: $  date | date "+%j day of %Y"
- Man (manual): $ man id 

---
### Viewing File Content

- cat (catenate) - Print entire file contents
- more - Print file contents page-by-page
- head - print first 10 lines 
- head - print firs N lines of file: head -n 3 numbers.txt
- tail - print the last 10 lines
- tal -n 3 
- wc (word count) - count characters, words, lines : wc pets.txt | wc -l pets.txt (don't count newlines) | wc -w pets-txt (to view only word count) | wc -c to view only byte count
### Useful commands for Wrangling text files 

- sort - sort lines in a file | sort -r oets.txt (reverse order)
- uniq ("unique") - Filter out repeated lines 
- grep ("global regular expression print") - Returns lines in a file matching pattern. grep -i makes it case insensitive: gre cg people.txt | grep -i ch people.txt
- cut - extracts a section form each line. cut -c 2-9 people.txt | cut -d ' ' -f2 people.txt
- paste - merge lines from different files: paste firs.txt last.txt yob.txt | paste -d "," firs.txt last.txt yob.txt 

![[Pasted image 20260916004637.png]]

---
### Networking

- A computer network is a set of computers that are able to communicate with each other and share resources. A network resource is any object, such as a file or document, which can be identified by the network. A network node is any device that participates in a network.
    
- A host is a computer that can function as a server or a client on a network. A server is a host computer that is able to accept a connection from a client host and fulfill certain resource requests made by the client.
    
- A network packet is a formatted chunk of data that can be transmitted over a network. The ping command works by sending special 'echo request' packets to a host and waiting for a response from the host.
    
- An IP address is a code used to uniquely identify any host on a network. A URL identifies a web resource and enables access to that resource.

**Network Commands**

- hostaname - prints hostname | hostname -s | hostname -i
- ip a - display system network interfaces | ip addr show eth0
- ping - send ICMP packets to URL and print response
- curl (Client URL) - Transfer data to and from URL | curl www.google.com -o google.txt
- wget (Web get) - Downloads files form a IRL; more focused than curl, supports recursive file downloads


----
### File Archiving and Compression Commands

**Archiving** is storing the information and preserve it. A collection of data files and directories stores as a single file. Makes the collection more portable and serve as a backup in case of loss or corruption
**Compression** reduce the file size by reducing information redundancy. Preserves storage, space, speeds up data transfer, and reduces bandwidth load. 

- tar (tape archiver) 

```
Archive and extract files: tar -cf notes.tar notes
Compress: tar -czf notes.tar.gz notes
list items: tar -tf notes.tar
extract: tar -xf notes.tar notes
Decompress/extracat: tar -xzf notes.tar.gz notes
ls -R to see the directories 
```

Zip

Zip compress files and directories to an archive

 ```
 zip:  zip -r notes.zip notes | ls to check
 unzip: unzip notes.zip | ls -R
 ```
 

-----
[[Linux Commands]]

man -k

- NAME - The name of the command or feature and a brief description of what it does.
    
- SYNOPSIS - A summary of the command syntax, including any options and arguments that can be used.
    
- DESCRIPTION - A more detailed description of the command, including its function and behavior.
    
- OPTIONS - All the available options and arguments that can be used with the command.
    
- EXAMPLES - Some examples of how to use the command.
    
- SEE ALSO - Related commands and documentation that may be helpful.

---
### File and directory navigation commands


ls (list) - list files and directories
pwd - print working directory
cd - change directory | cd .. change to parent directory | cd ~ for home folder
find - find files in directory
mkdir - Make directory | mkdir test
rm - remove file or directory - rm file1 | rm -r folder | rmdir 
touch - create empty files | touch a.txt  | date -r notes (check creation date)
cp - copy a file or directory | cp notes.txt Documents
mv - move file or directory | mv my_script.sh Scripts
chmod - Change file permissions  | chmod +x my_script.sh

![[Pasted image 20260913002022.png]]


# Security - Managing File Permissions and Ownership

## File Ownership and Permissions — Summary

Linux is a **multi-user operating system**, so file permissions are important to protect private or confidential information from other users.

### Ownership levels

Linux uses three ownership categories:

- **User (u):** the owner of the file, usually the person who created it.
- **Group (g):** a group of users who may share access.
- **Other (o):** everyone else with access to the system.

The file owner can decide who is allowed to read, modify, or execute the file.

### Permission types

Linux uses three main permissions:

- **r — read:** view the contents of a file.
- **w — write:** modify the file.
- **x — execute:** run the file as a program or script.

You can view permissions with:

```
ls -l
```

For example:

```
-rw-r--r--
```

This is divided into three groups:

```
rw-   r--   r--
user  group other
```

This means:

- The **user** can read and write.
- The **group** can only read.
- **Others** can only read.
- Nobody can execute the file.

The first character describes the object type:

```
- = regular file
d = directory
```

### Directory permissions

Permissions have slightly different meanings for directories:

|Permission|Meaning|
|---|---|
|`r`|List the directory contents|
|`w`|Add or remove files/directories|
|`x`|Enter the directory with `cd`|

For example, having `x` permission on a directory allows a user to access it.

### Changing permissions with `chmod`

The `chmod` command changes file or directory permissions.

For example:

```
chmod go-r my_new_file
```

means:

- `g` = group
- `o` = others
- `-` = remove permission
- `r` = read permission

So this command removes **read access from the group and other users**, making the file more private.

You can check the result again with:

```
ls -l
```

### Executable files and scripts

For a shell script to be executable, it generally needs:

1. **Execute permission (`x`)**
2. A **shebang** on the first line, which tells Linux which interpreter should run the script.

Example:

```
#!/bin/bash
```

A Bash script is simply a text file containing commands that the Bash shell can interpret.

### Key commands

```
ls -l
```

View permissions.

```
chmod
```

Change permissions.

```
chmod go-r filename
```

Remove read permission from group and others.

### Quick memory trick

```
r = read
w = write
x = execute

u = user
g = group
o = other
```

So something like:

```
chmod u+x script.sh
```

means **give the user execute permission** on `script.sh`.

```
Hello GPT
```