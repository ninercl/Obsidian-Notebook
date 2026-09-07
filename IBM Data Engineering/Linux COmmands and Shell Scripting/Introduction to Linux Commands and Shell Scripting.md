
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