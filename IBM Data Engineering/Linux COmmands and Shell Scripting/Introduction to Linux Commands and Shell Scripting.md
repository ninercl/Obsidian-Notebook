
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

----
[[Creating and Editing Text Files]]

Popular text editors:
- Command-line text editors: GNU nano, vi, VIM
- GUI-based text editors: gedit
- Command-line or GUI: emacs

Features of gedit:
A general-purpose editor, easy to use with a clean, simple GUI:
- Integrate file browser
- Undo and redo
- Search and replace
- Extensibility

Features of GNU nano:
A command-line text editor provides:
- Undo and redo
- Search and replace
- Syntax highlighting
- Indenting groups of lines 
- Line numbers 
- Line-by-line scrolling
- Multiple buffers

File editing with vim
VIm is a traditional and very powerful command-line

to star vim: vim
to specify a file to edit, type: vim filename 

*Two basic modes*

- Insert and command mode. Press i to enter Insert mode. PRess ESC to exit insert mode and switch to command mode. 
- Enter :sav exapample.etx to create a file and write the buffer to the file 
- Enter :w to write the buffer to the file
- Enter :1 to quit vim session
- Enter :q! to quit without saving


----
Packages

![[Pasted image 20260910004706.png]]

Deb And RPM Packages

- Packages for Linux OS
- Distinct file types for different Linux Oss
- .deb files: For Debain-based distributions such as Debian, Ububtu, and Mint.
- .rpm files: for Red Hat-Based distributions such as CentOS/RHEL, Fedora, and OpenSUSE
- RPM ands for Red Hat Package Manager

deb and RPM formas are equivalent
- deb and RPM formas are equivalent
- If a package is only available in one format, you can use alien to convert it.

- sudo apt upgrade to update 
- yum to update rpm 
- pip for python

