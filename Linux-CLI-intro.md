# Index

## Part 1 - LINUX AND THE FLOSS PHILOSOPHY
### 1.0 - Introduction
### 1.1 - Definition of an Operating System
### 1.2 - Unix/Linux Philosophy
### 1.3 - Open Source Principles
### 1.4 - Software Licensing
### 1.5 - The Free Software Foundation
### 1.6 - The Open Source Initiative
### 1.7 - Further reading

## Part 2 -
### 2.1 - Moving around directories
### 2.2 - Listing files
### 2.3 - Launching programs and creating aliases

# NOTICE
**THIS IS A WORK IN PROGRESS.**
Updates are done frequently and new material is added as often as possible. There are going to be spelling mistakes, editing work and other changes before all the course parts are completed. Currently the focus is on adding all the material before editing and correcting.

This notice will remain until the course is complete.

Any and all feedback is appreciated.

# 1.0 - Introduction
--------------------

There are many tutorials and introductions to the Linux/Unix command line. Some of them focus on a basic set of commands or on the concepts needed to pass a certification.

I like it when the focus is on the practical side of learning. What can be effectively be applied at work.

The selection I have made covers areas and commands that any Linux user or sysadmin will use on a daily basis. You can see them as the building blocks for more advanced knowledge.

The first part covers some theory that will allow you to understand what Linux is and the philosophy behind it. It isn't compulsory to learn about it but it will help you better understand what the design principles and why certain things are done in a certain way.

I have tried to ensure that all the chapters build on top of the previous ones. If I introduce a concept that relies on some other knowledge, this will have already been presented in a previous chapter. 

My preference is for the knowledge to be introduced in a natural way, setting the base and groundwork upon which to build from. If you are new to Linux following it in order will yield the maximum benefit.


## A note on console fonts
Consoles are configured by default with mono-space fonts and that have clear and distinctive fonts.

The reason for this is that some characters with certain fonts are difficult to distinguish.

The clearest example are 1, I, l, 0 and O.

If this document has been rendered in a way that you can't differentiate between the above characters please get an updates version or go to the course's website to get it in a different format:

https://github.com/dpoves/Linux-CLI-intro


## Getting in touch
If you want to get in touch you can reach me via the following.

**Technical Blog**
https://pov.es

**GitHub**
https://github.com/dpoves

Any feedback is appreciated. If you find any typos, feel that certain sections aren't clear enough or find any mistakes, please let me me know.

I hope you find the course useful!

# 1.1 - Definition of an Operating System
-----------------------------------------

## What is an Operating System?
An Operating System (OS) provides the basic features of a computer. It allows you to use the hardware devices, provides a user interface and its standards and a set of basic tools that makes the computer useful.

Most of those basic features will be defined by the OS' kernel.

## What is a Kernel?
The kernel of an OS if the software component that is responsible for managing several low level features. They include:

- Interfacing with hardware devices.
- Allocating memory to programs.
- Allocating CPU time to programs.
- Allowing programs to interact with each other

When you run a program it does rely on the kernel for many of its basic functions. The kernel will allocate memory and CPU time to it. If needed, it will also give access to hardware and kernel services.

You can imagine the kernel as the part that holds the computer together. Without it the computer wouldn't be able to do much. 	

Different OS will use different kernels. macOS, Windows and Linux use different kernels and they aren't interchangeable.

Each kernel uses a different internal design and software interfaces for programs to use. Programs will be built to work with one specific kernel or kernel type.

Some programs can be made so they run in different types of kernel but they will still need different binaries for each OS.

## Linux kernel
Linux uses a kernel called Linux. Strictly speaking Linux is just the kernel. The full name of the OS is GNU/Linux. We will look into what makes Linux an OS later.

You can read more on the naming in this Wikipedia article:

https://en.wikipedia.org/wiki/GNU/Linux_naming_controversy

Some of the features that you might associate with Linux, like the command line that we will be learning in here, are provided by command and programs that aren't part of the kernel.

Linus Torvalds created the Linux kernel in 1991, while he was still a student. The kernel has evolved considerably since. It runs on a wide variety of CPUs and hardware.

The easiest way to learn about Linux (as an OS) is to use it on a desktop or laptop computer

The Linux kernel, however, runs on everything from mobile phones to supercomputers.

## What else identifies an OS?
The kernel is at the core of any Operating System but it is a component most user don't manipulate directly.

Users would normally interact with other software components like:

* **Command line shells**
Many years ago users interacted with computers exclusively by typing commands in a program called a shell. The commands would allow to manipulate files, execute programs and so on. Many computer users don't use text based shells, but they are still important for intermediate and advanced users. This course is exclusively about using the terminal and such programs. Many different shells are available. The most popular is the Bash shell, also known as Bourne Again Shell, although different distributions and operating systems might use their own variants.

* **Graphical User Interfaces**
GUIs rely on menus, icons and a mouse pointer. Each OS has their own graphical interface that makes it distinct. Linux relies on the X Window System as its GUI. X defines protocol and graphics primitives so additional software like window managers and desktop environments are used to provide a complete user experience. Linux has several available interfaces that can be installed separately.

* **Utility programs**
Nearly all OS come with a set of utilities or applications like text editors, calculators, maintenance tools and so on.

* **Libraries**
Libraries are collections of programming functions that provide critical services. They are used by nearly all programs. Normally it will only be programmers that will need to work with them directly.

* **Productivity programs**
These would be programs like web browsers, word processors and similar. Most users will use computers to work with this kind of programs. This kind of programs are technically independent of the OS, but sometimes they are related to a specific one. For example, Microsoft Office on Windows. Although programs can be available for more than one OS they will vary due to the different OS and GUIs.

There are other things that will differentiate different OS. User management, disk naming conventions, init systems, etc.

## Building a Linux based Operating System
Taking into account all of the above, what does make Linux a complete OS?

These are some of the components that will make part of a full Linux Operating System (also called distro, short for distribution):

* **Linux kernel**
The kernel will be at the core of any Linux OS. The kernel is updated regularly and new versions come out roughly every 6-8 weeks.
Different distributions will be probably be using different versions.

* **Core Unix Tools**
The set of command line utilities included with the OS, the X Window System and Desktop Environment (if used) and other utilities that will come with the OS will vary between different distros, in some cases it will be just different versions, in some other cases some will be on one distro and not included on another.

* **Additional software**
Programs to run server services, productivity tools and similar will vary from one distro to another.

* **Init system**
How the OS is initialised and all the startup scripts can vary greatly. Linux uses an init system (init for initialisation) that will launch programs responsible for different functions like networking. The init system will give an OS part of its personality
Many distros have moved to _systemd_ but this has also been the source of much controversy and clashes.

* **Installer**
Depending on the distro you use the installation process and program used will vary. Some distros will use a text interface, others will use a graphical interface. Different distros might support different disk layouts and formats, they will set the first user accounts, etc.
Some installers will be a full and complete ISO image, others will provide a minimal configuration and rely on a connection to the Internet to download all the additional software.

# 1.2 - Unix/Linux Philosophy
-----------------------------

## The Unix philosophy
This is a summary from the Wikipedia's entry on Unix Philosophy (https://en.wikipedia.org/wiki/Unix_philosophy).

The Unix is a set of cultural norms and philosophical approaches to minimalist, modular software development.

Early Unix developers brought the concepts of modularity and re-usability into software engineering practice. Over time, the leading developers of Unix and associated programs established a set of cultural norms for developing software. These norms have been termed the "Unix philosophy."

It emphasises building **simple**, **short**, **clear**, **modular**, and **extensible** code that can be easily maintained and repurposed by developers other than its creators.

In essence, Unix development is:

* Write programs that do one thing and do it well.
* Write programs to work together.
* Write programs to handle text streams, because that is a universal interface.

The Unix philosophy favours composability. This is a system design principle that ensures that system components can be selected and assembled in various combinations to satisfy specific user requirements.

The essential features that make a component composable are that it be:

* **self-contained** (or **modular**)
It can be deployed independently – note that it may cooperate with other components, but dependent components are replaceable
 
* **stateless**
It treats each request as an independent transaction, unrelated to any previous request.

On composable systems it is easier to evaluate their individual parts adding to their trustworthiness.
	
You can read more about the Unix philosophy in the following link: https://catb.org/esr/writings/taoup/html/ch01s06.html

# 1.3 - Open Source Principles
------------------------------

## Types of software
Software is distributed in different forms. Each way has its own expectations on regards to payment, redistribution and user's rights.

We can divide software in some of the following categories:
    
* **Commercial software**
Individuals or companies develop commercial software with the intention of selling it for a profit. Commercial software source code is usually kept secret. Redistribution or copying of commercial software is generally illegal. Microsoft Windows and Microsoft Office are examples of commercial software.

* **Shareware software**
Shareware software is very similar to commercial software. It is also copyrighted and the developer asks for payment. The main difference is the way it is distributed. You are allowed to try the software for free for a period of time, and even copy it, as long as after a the trial period expires you buy a license and don't distribute the licensed version. Shareware was very popular in the 1990's.

* **Freeware**
Freeware is distributed without any payment expected by the author. Freeware software might be a basic version of a more fully featured program, or it can be bundled to promote another software. Freeware normally comes with no source code. Some examples of freeware are Adobe Reader, most of Windows drivers.
Please, note that freeware should not be confused with **free software**.

* **SaaS**
The advent of cloud computing has made this model more common place. The software is normally hosted on the cloud or web and accessed via a web browser and it is paid on a subscription base. In this kind of software distribution it is unlikely for you to have access to both the binary and the source code. Office365 and Google Docs are examples.  

* **Open Source Software**
Open Source Software is defined by 10 principles that are available at https://opensource.org/osd-annotated

The most important of these principles are _the right of the user to redistribute the program_, _the availability of source code_, and _the right of the user to make and distribute changed versions of the program_.

These principles mean that users can modify open source programs to suit their own needs. This can even be in ways or purposes that the original author doesn’t support.

The major difference with Free Software is that some Open Source licenses, like the BSD licence, allow redistribution of modified works under a different licence. This means that a modified version of an open source program could be redistributed as closed source.

* **Free/Libre Software**
Superficially Free/Libre software seems very similar to Open Source software.

We will look into this licence in more detail later, but the main difference with Open Source is that redistribution of modified versions of  Free/Libre Software have to distributed under the same licence. 


There are more types of software beyond these categories. Also some that might be a mix of the above that don't fit in the above categories.

The Free Software Foundation keeps a list of licences indicating which ones are Free/Libre:

https://www.gnu.org/licenses/license-list.html

The Open Source Initiative does keep a list of licences that are Open Source:

https://opensource.org/licenses


If you want to learn more about different types of Free/Libre and Open Source licences you can read this book:

https://people.debian.org/~dktrkranz/legal/Understanding%20Open%20Source%20and%20Free%20Software%20Licensing.pdf


## Characteristics of Open Source software
The argument in favour of Open Source software is that that software that is developed in an open manner is likely to be superior to software developed as closed source.

This is argument in favour (or against it depending of your point of view) are:

* **Better code**
Exposing the source code allows the community to review and improve it. This might not be necessarily true for smaller projects if they aren't actively reviewed by other programmers.

* **Flexibility**
Having access to the source code allows users to modify and customise the software. Rather than having a program nearly do what the user needs from it, it can be modified so it does exactly what the user wants. It can be argued that this benefit is only available to those with the skill, time or money to modify or able to hire someone to modify the software.

* **Lower cost**
The open source and free software definition allows the selling of software, although due to how it is distributed it tends to be available for free (as in no money paid). However, there are services associated with using FLOSS (Free/Libre Open Source Software), like support, consultancy and others that need to be taken into consideration.

* **No vendor lock-in**
Proprietary software can make it difficult for products of the competition by using closed file formats and by not playing nice with open standards or products. FLOSS products can be forked and/or modified to support additional file formats, protocols or standards.

The FLOSS community would argue that the above points are all in favour of using FLOSS, where the disadvantages are small compared to the loss of freedoms you get.

Ultimately this is a matter of opinion and you should reach your own conclusions. Note that this course is about using FLOSS so there is certainly a bias in favour of it.

# 1.4 - Software Licensing
--------------------------

## Copyright and software
Copyright law has existed for several centuries and although it was never designed to deal with software it has been and it is applied to it.

A copyright is a legally recognised right to create a copy of something. For example, if you write a book, take a photograph, make a video or write a program, in most jurisdictions you alone have the right to make copies of it. You can grant others a right to make those copies or handover the copyright to others.

Every country has different copyright laws but most countries are signatories of the Berne Convention. The convention enforces a requirement that member countries recognize copyrights held by the citizens of all other member countries. You can create your work in your home country and it will be automatically copyrighted in all the other member countries.

The main problem with copyright law is that it was written at a time computers didn't exist and they don't blend too well. Normally copyright law will forbid you to make a copy of a computer programs, but this isn't practical.

You need to make copies of your software to make it functional. For example:

* You might need to copy the software to your hard drive.
* When executed the program will have to be copied to RAM.
* There might be a copy of the program in some of the computer or hard drive caches.
* You might have backups of your hard drive that will include copies of the program.

Those copies would normally be considered fair use and be ignored. Some countries copyright law accepts that some software copies are necessary for it to be used.

## Modifying Copyright Terms Through Licences
Most software is released with a licence which is a document that modifies the rights granted by copyright law. You don't normally sign this licences, although you must be familiar with menus asking you to click a button to accept the licence terms. Before software distribution through the internet was prevalent software licences were a printed document accompanying the software.

Those licences are usually called End-User Licence Agreements (EULAs), shrink-wrap licences or click-though licences. Open Source software is distributed with the licence in the form of a file, normally called LICENSE or COPYING.

Software licences can modify copyright terms by making them more or less restrictive. Some licences tie the software to a single machine, which is a more restrictive term than standard copyright law.

The Linux kernel is distributed under the General Public Licence (GPL) which is a Free/Libre licence. The GPL grants you the right to redistribute the software both in source code and binary form. This kind of licence provides less restrictions than standard copyright law.

Usually proprietary software will be distributed with more restrictive licences and FLOSS with less restrictive ones, although this isn't always the case.

# 1.5 - The Free Software Foundation
------------------------------------

## The Free Software Foundation
The Free Software Foundation (FSF) is of great importance in the FLOSS community. It was founded in October 1985 by Richard Stallman to support the free software movement and the GNU (GNU's Not Unix) project.

The GNU project aims to provide computer users freedom and control in their use of their computers and computing devices by collaboratively developing and publishing free software under their GPL licence.

The GPL licence is the manifestation of FSF's philosophy.

## Understanding the FSF Philosophy
The FSF advocates Free Software. Free as in freedom (not as in beer). Free Software defined by the FSF states what you are allowed to do with the software.

Free software is different from freeware. Freeware is software that's free of charge (gratis), but not free as in freedom (free/libre).

The FSF defines four specific software freedoms:

  0. The freedom to run the program as you wish, for any purpose. 

  1. The freedom to study how the program works, and change it so it does your computing as you wish. Access to the source code is a precondition for this. 

  2. The freedom to redistribute copies so you can help your neighbour. 

  3. The freedom to distribute copies of your modified versions to others.

More information is available in:

https://www.gnu.org/philosophy/free-sw.html.en

These freedoms are similar to the OSI principles but there are some important differences in interpretation.

By FSF standards all software in the world would be free following the above four freedoms. Some Linux distributions are completely free but some distributions include proprietary software. For example some vendors don't publish the source code for their drivers. In some cases, a part of the distro is proprietary to limit redistribution without charging.

Free Software isn't necessarily free of charge and the four freedoms don't limit the possibility of selling it for a fee, but free software's price tends to be zero. The problem with proprietary software isn't about the cost, but how it restricts its redistribution.

The takeaway about software freedom is that it empowers users, not just developers or companies. If you can modify a program that nearly does what you need it to do, to exactly do what you want it gives it an enormous advantage over a proprietary version.

By then distributing your modified version you can help others that had the same problem. The application of the FSF philosophy has a benefit for the wider community.

The FSF licences have sometimes been called copyleft. This is a wordplay with copyright. Where copyright restricts the usage rights, copyleft widens them. Copyleft provides provisions meant to guarantee the freedom of users to copy software, rather than restrict it.

## The General Public Licence (GPL)
The legal expression of the principles of the FSF are written in the GPL. Two versions of the GPL are the most common, versions 2 and 3.

Both versions apply the four freedoms. They also make explicit an implication of those four freedoms by stating that any derivative work has to be released under the same GPL licence.

This is meant to stop a company or individual from appropriating a program released as free software. For example, many companies contribute to the Linux kernel by providing patches or bug fixes. No company could redistribute their modified versions without also sharing the source code. Whatever patches or bug fixes they have applied would be shared if they were to redistribute their kernel version.

Please note that it is perfectly fine to make modifications to free software and not share it as long as it is not distributed. Google and Amazon have their own versions of Linux that they use internally and that aren't distributed.

Also it is important to note that in a Linux distro there will be a collection of different programs, each one with their own individual licence. Some programs will be GPL, version 2 or 3, others might have an Open Source licence and others might have a proprietary one. No one licence takes priority over the others and applies to each individual program. 

GPL version 2 (or GPLv2 for short) was released in 1991. GPLv3 was released in 2007 with the intention of closing what the FSF viewed as loopholes in the GPLv2. GPLv3 contains clauses intended to combat use of hardware restrictions that limit the four freedoms and to address issues related to software patents.

The most clear example of what the GPLv3 tried to address were hardware limitations that Tivo applied so no kernel versions that the ones they create themselves can be installed on their hardware. Android is another example of this situation. GPLv3 tries to limit this.

Some programs have upgraded their licence to GPLv3 while others have remained on GPLv2. The most noticeable is the Linux kernel that is released under GPLv2. This is quite important as it allows the Linux kernel to be used by devices that are otherwise fairly closed. Many of such devices use restrictive boot processes to prevent unauthorized kernels from booting.

## The Lesser General Public Licence
The Lesser GPL or LGPL is a variant of the GPL licence.

Developers have to use libraries regularly. Libraries are collections of code that are shared with other programs. For example, in Linux (and other Operating Systems) libraries provide common features like creating menus or displaying windows. All GUI applications use these features and developers use them so they don't need to rewrite code for shared features. It has also the advantage of reducing the size of programs.

The LGPL is often applied to libraries because the GPL wording would require that all programs that were to use a GPL library to be released also as GPL.

The LGPL allows programs that use a library to be released under a different licence, even a commercial one.

## The GNU Free Documentation Licence (GFDL)
The GFDL is meant to be used for documentation rather than software.

The GPL was written with software in mind so its wording doesn't fit static documents. The GFDL fills this need.

Many projects of the Wikimedia Foundation, including Wikipedia use the GFDL in conjunction with Creative Commons.

## Further reading
There are other types of licences like Creative Commons that aren't discussed here. You can read more in the following links.

**Understanding Open Source and Free Software Licensing** by Andrew M. St. Laurent 
https://people.debian.org/~dktrkranz/legal/Understanding%20Open%20Source%20and%20Free%20Software%20Licensing.pdf

**Free as in Freedom** by Sam Williams, _O'Reilly Media, Inc._, March 2002, ISBN 9780596002879
http://gutenberg.org/ebooks/5768

# 1.6 - The Open Source Initiative
----------------------------------

The Open Source Initiative (OSI) was founded by Bruce Perens and Eric S. Raymond in 1998. It was created as an umbrella organisation for open source software.

Although the idea behind is similar to the FSF it is different in some important parts. More software qualifies as open source than free software. Remember that some open source licences allow redistribution of modified versions as proprietary.

The OSI, like the FSF, keeps a list of licences that they consider Open Source. Some of the licences are both compatible with Free/Libre and Open Source Software, but some licences that are Open Source aren't Free/Libre Software.

**Free/Libre compatible and incompatible licences**
https://www.gnu.org/licenses/license-list.html

**OSI approved licences**
https://opensource.org/licenses/alphabetical


## The Open Source Philosophy
During the 1980s and 1990s the free software movement gain support in some circles, specially academia and hobbyists. Making inroads in business was proving more difficult.

Some businesses adopted open source software, but this was slow and minimal. Businesses distrusted software that was offered for free and worried about future liability.

Mainly the adoption was spearheaded by administrators that had small budgets and started installing Linux, Samba, Apache and other free software in order to save money compared with the commercial alternatives available at the time.

The FSF's advocacy is based on the moral imperative that all software should be free. This is appealing to some people, but businesses, specially the ones that make money off selling software would disagree. They would reject using free software as it clashed with their world-view.

This was one of the reasons why the OSI creators designed their organisation as a way to advocate free software. They coined the term Open Source and softened some of the FSF's imperatives. OSI aims to promote Open Source Software in the business world.

In the OSI's words:
>
	Open source enables a development method for software that harnesses the power of distributed peer review and transparency of process. The promise of open source is higher quality, better reliability, greater flexibility, lower cost, and an end to predatory vendor lock-in.

	https://opensource.org/about

As stated before, the main difference between the FSF and the OSI is the requirement by the GPL that derived works are also distributed under the GPL.

The OSI has certified many licences as Open Source but not all of them have this kind of restriction and therefore don't qualify as Free/Libre Software.

There is software that has been released with an Open Source licence and has been then moved into closed source products. macOS is one example of this.

The OSI doesn't oppose this as long as the licence originally used allows it. The FSF on the other side forbids this explicitly.

Ultimately, the OSI saw as a benefit that businesses adopted Open Source Software above said businesses adopting a FLOSS philosophy, taking a more pragmatic approach. 

Generally speaking free software is also open source software, but some FSF approved licences aren't recognised as Open Source by the OSI. Similarly, many Open Source licences don't qualify as Free/Libre Software.

Nowadays there is some tension between free software purists and the open source community although they share similar goals.

You have seen me use the FLOSS (Free/Libre Open Source Software) acronym before and this as umbrella definition that covers both types of software. You might see also the FOSS (Free Open Source Software) acronym, although this is being superseded by FLOSS.


## The Definition of Open Source Software
The open source definition is available in https://opensource.org/docs/osd

It is made of 10 principles originally derived from the Debian Free Software Guidelines. These 10 principles are summarised here: 

1. **Free redistribution**
The licence must permit redistribution, including redistribution as part of a larger work.

2. **Source code**
The program must include source code and permit redistribution of both source code and (if applicable) binary code.

3. **Derive works**
The licence must permit others to modify the software and to distribute such modifications under the same licence as the original. Note that the open source definition permits but does not require that the licence redistribution is made under the same original licence.

4. **Integrity of the author's source code**
The licence may restrict redistribution of modified source code, but only if patch files may be distributed along with the original source code. The licence may require that derived works change the software’s name or version number.

5. **No discrimination against persons or groups**
The licence must not discriminate against any person or group of people.

6. **No discrimination against fields of endeavour**
The licence must not forbid use of the program in any field, such as in business or by genetics researchers.

7. **Distribution of licence**
The licence must apply to anybody who receives the program without needing a separate agreement.

8. **Licence must not be specific to a product**
The licence must not require that the program be used or distributed as part of a larger program — that is, you may extract a single program from a larger collection and redistribute it alone.

9. **Licence must not restrict other software** The licence must not impose restrictions on other software that’s distributed along with the licenced software.

10. **Technology neutrality**
The licence must not be restricted based on specific technologies or interfaces.


The first three of these principles are the most important. At least to understand the point of open source technology.

The 10 principles have a resemblance to the FSF's four freedoms. There are, as it has been repeatedly pointed out, differences, specially in terms of licensing requirements for derived works.

# 1.7 - Further reading
-----------------------

## Kernel

* _Ward, Brian_. **How Linux Works, 2nd edition**, No Starch Press, 2015. **Chapter 1**

* _Negus, Christopher_. **Linux Bible, 9th edition**, Wiley, 2015. **Chapter 1**

* _Nemeth, Evi; Snyder, Garth; Hein, Trent R.; Whaley, Ben; Mackin, Dan;  Garnett, James; Branca,Fabrizio; Mouat, Adrian_. **Unix and Linux System Administration Handbook, 5th edition**,  Pearson Addison-Wesley, 2018. **Chapter 11**


## Unix/Linux, Free/Libre Open Source Software

* Williams, Sam. **Free as in Freedom: Richard Stallman's Crusade for Free Software**, O'Reilly, 2002.

* _Negus, Christopher_. **Linux Bible, 9th edition**, Wiley, 2015. **Chapter 9**

* _Blum, Richard; Bresnahan, Christine_. **Linux Command Line and Shell Scripting Bible, 3rd edition**, Wiley, 2015. **Chapter 1**

* _Nemeth, Evi; Snyder, Garth; Hein, Trent R.; Whaley, Ben; Mackin, Dan;  Garnett, James; Branca,Fabrizio; Mouat, Adrian_. **Unix and Linux System Administration Handbook, 5th edition**,  Pearson Addison-Wesley, 2018. **A Brief History of System Administration, pages 1166-1175**

# 2.0 - 
--------------------


# 2.1.0 - Moving around directories
-----------------------------------

## Console prompt
When you first open your terminal you will be greeted with a prompt similar to this:

```shell
david@tuxedo:~$ 
```
This will vary from one Linux distribution to another and you shouldn't worry too much if it looks different to your console, at least for now.

The first part **david@tuxedo** shows the current user and the machine name. It is just a way of saying that this console is currently logged with user _david_ at a machine called _tuxedo_.

The **~** is an alias for the current user's home folder. If you change folders this part of the prompt will be updated if your console is configured in that way.

The **:** is a separator between the machine name and the current directory you are in.

The **$** is the the command prompt for the Bash shell. All the commands that you type will be after this **$**.

I will be showing the **$** in my examples for convention but you don't have to type it when you enter your commands. Console output in the examples won't have the **$** prompt.

I will not show the user or machine name and current directory before the **$** prompt in the rest of the course unless relevant.

## Current Directory
The first command you will type is **pwd**. It stands for _print working directory_ or in another words, display the directory I currently am in.

```shell
$ pwd
/home/david
```
After typing **pwd** the console replies with _/home/david/_ as the folder I am currently in. In Linux user folders are generally stored in _/home/_.

Your username will match the one you created when you installed the OS. In the examples below I will be using a _username_ called _david_.

You can change folders with the **cd** which stands for _change directory_.

```shell
$ cd Desktop
```
The **cd** command followed by the folder you want to change will take you to that directory. Check the current directory with **pwd**:

```shell
$ pwd
/home/david/Desktop
```

## The root directory
We saw earlier that **~** is the current user's home folder. The **/** represents the _root folder_. In Unix and Linux all folders and devices start in the root folder. We will look at the Linux folder structure in more detail later on.

You can use **/** as a way to directly reach the root folder:

```shell
$ cd /
$ pwd
/
```

You might have noticed already, but Linux and nearly any other Unix derived OS is case sensitive. If you have files or directories called _Linux_, _linux_ and _linuX_ they will all be treated as different files.

You can use a command like **cd ~** to go back to your home folder, but Unix is about efficiency. If you just type **cd** on its own it will bring you to your home folder:

```shell
$ pwd
/
$ cd
$ pwd
/home/david/
```

## Types of paths
There are two kinds of paths used when working with directories:

* Relative paths
* Absolute paths

A _relative path_ is a path relative to your current location. For example, the above **cd Desktop** command moved you to a directory called **Desktop** from the current directory you were in.

An _absolute path_ is the full path to any given directory. For example:

```shell
$ cd /home/david/Desktop
$ pwd
/home/david/Desktop
```

Full paths aren't ambiguous and will always bring you to the folder you want to be. They will always start with the root directory **/**.

Note that the **/** is also used to separate directories and subdirectories, like in _/home/david/Desktop_. In this case meaning _root directory_, _home_ directory, _david_ subdirectory, _Desktop_ subdirectory. 


## Other directory reference characters
There are other interesting shortcuts that you will have to use often.

If you want to move back one directory you will use **..**. The two dots are a reference for the directory directly above the current one. The **.** or single dot is a reference for the current directory you are in. You will never need to use it with **cd**, as **cd .** would just leave you in the same directory you currently are. The **.** will become very useful in the future when working with other commands.

```shell
$ pwd
/home/david
$ cd ..
$ pwd
/home
```
You can also use **cd ..** to change to a directory parallel to the one you are in one go:

```shell
$ cd
$ cd Desktop
$ pwd
/home/david/Desktop
$ cd ../Downloads
$ pwd
/home/david/Downloads
```

Or go down several levels in one go:

```shell
$ cd
$ cd Desktop
$ pwd
/home/david/Desktop
$ cd ../..
$ pwd
/home
```

You can use **cd -** to back to the directory you were previously:

```shell
$ cd
$ pwd
/home/david
$ cd Desktop
$ pwd
/home/david/Desktop
$ cd -
/home/david
```

## Using wildcards
**cd** also allows you to use wildcards to change directories if you don't know its full name.

For example:

```shell
$ pwd
/home/david
$ cd /home/david/De*
$ pwd
/home/david/Desktop
```

As long as there isn't more than one directory that matches the string, it will change to the matching directory.

Otherwise you will get an error:

```shell
$ cd
$ cd /home/david/D*
bash: cd: too many arguments
```

## Home folders
We already saw that **~** is a reference for the current user's home directory.

You can change to the home directory of a given user by using the **~username** reference:

```shell
$ cd
$ pwd
/home/david
$ cd ~peter
$ pwd
/home/peter
$ cd ~david
$ pwd
/home/david
```

We already mentioned that normally all user directories are in _/home_. The only exception is the _root account_ or superuser. The _root account_ home directory is in **/root**.

Note that the _root directory_ (**/**) isn't the same as the _root account_ home directory (**/root**).

# 2.1.1 - Moving around directories key points
-----------------------------------

## Commands
```shell
pwd		Print Working Directory
cd 		Change Directory
```

## Concepts
```
Absolute paths
Relative paths
```

## Folder references
```
.	Current directory
..	Directory above current one
~	Current user home directory
/	Root directory
```

## Shortcuts
```
cd				Move to your home directory 

cd ~username	Move to home dir of 'username'

cd -			Move back to the dir you were previously 

cd /home/d*		Move to the folder starting with d in /home
```

# Further reading

* _Robbins, Arnold_. **Bash Pocket Reference**, O'Reilly, 2010. **Pages 1-8**

* _Ward, Brian_. **How Linux Works, 2nd edition**, No Starch Press, 2015. **Chapter 2**

* _Negus, Christopher_. **Linux Bible, 9th edition**, Wiley, 2015. **Chapters 3 and 4**

* _Blum, Richard; Bresnahan, Christine_. **Linux Command Line and Shell Scripting Bible, 3rd edition**, Wiley, 2015. **Chapters 3, 5 and 23**

# 2.1.2 - Moving around directories (EXERCISES)
-----------------------------------------------

## Exercises

1. Get to the **root folder** with one command.
2. Can you think of a quick way of going to your **home folder**?
3. Go to **/usr/bin** and switch to **/usr/lib** with one command.
4. Move to **/proc/tty** and display the current directory path.
5. Move back to your **home folder** with one command.
6. Move to the **previous folder you were in** using a directory reference rather than the full path.
7. How do you move to the **home directory** of a user named john?
8. Give an example of relative path and another of an absolute path.
9. How do you move up one directory?

# 2.2.0 - Listing files
-----------------------

Before we start looking at more commands a brief note on their syntax.

All commands in Unix and Linux follow a similar pattern:

```
command [options] [arguments]
```

Not all commands need options or arguments, others might require them both, but in general the above pattern holds true for a majority of them.


## ls
**ls** stands for _list_. It will list the contents of a folder.

```shell
$ cd
$ ls
Desktop     Documents   Images  Pictures    snap
Templates   Downloads   Music   Public      Videos
```

**ls** can be used to list files in a different directory to the one you are if you use that directory as an argument:

```shell
$ cd
$ ls /sbin
[..]
```

## The zero or more characters wildcard *
Some commands accept the use of wildcards. We are going to see some examples with **ls**, but there are more commands, specially the ones that are used to manipulate files and directories that accept them.

```shell
$ ls *
Desktop:
 trash.desktop
Documents:
Downloads:
[...]
```

In Linux the * stands for everything, in reality it stands for matching any number of characters, but for this example you can assume that it means everything. 

You might be familiar with **`*.*`** in DOS/Windows to list all files. Linux and Unix don't need files to have an extension  so **`ls *`** is enough.

**`ls *.*`** would list files in the current directory that contain a dot.

```shell
$ ls
Desktop     Documents   Images  Pictures    snap
Templates   Downloads   Music   Public      Videos

$ ls *
Desktop:
 trash.desktop
Documents:
Downloads:
[...]

$ ls *.*
ls: cannot access '*.*': No such file or directory
```

Note the difference in output between using `*.*` and *.  When `*.*` is used **ls** doesn't find any files containing a dot in the name and shows an error message.

The * wildcard is very versatile, as it stands for any number of characters (including zero) you can create strings like:

To list all files starting with the string foo:

```shell
$ ls foo*
```

Or all files ending with foo:

```shell
$ ls *foo
```

Strictly speaking, for the above examples if there was to be a file just called "foo" the above two commands would find this file it would match both criteria. The idea in any case is that you will be likely be using * to search for files with partial matches like above.

You can also list files that contain the string foo using * on both ends:

```shell
$ ls `*foo*`
```

One last very useful example is to use * for a whole directory. For example, if I wanted to list the files in the Downloads directory of all the users in my system I would be doing something like:

```shell
$ ls /home/david/Desktop
$ ls /home/alice/Desktop
$ ls /home/bob/Desktop
[...]
```

Doing it this way would be very time consuming. You can use * to just list all in one go:

```shell
$ ls /home/*/Desktop
[...]
```

Just note that the above will show a permissions error as standard users can't access other users' directories, but an administrator would be able to issue a command like that. 


## The single character wildcard ?
Where the * represented any number of characters, the **?** represents a single character.

This can be very interesting because you can issue commands that will list files with a specific number of characters:

```shell
$ ls ?oo
```

The above will list all files that are exactly 3 characters in length and of which the last two characters are oo.

You can use the **?** several times or just on its own.

List all files that are four characters long and that start with s in /bin:

```shell
$ ls /bin/s???
/bin/sddm  /bin/shuf  /bin/snap  /bin/stat  /bin/sudo  /bin/sync
/bin/sftp  /bin/size  /bin/sort  /bin/stty  /bin/svlc
```

Or just list all files that are three characters long in /sbin:

```shell
$ ls /sbin/???
/sbin/lpc  /sbin/rmt  /sbin/ufw  /sbin/zed  /sbin/zic
/sbin/raw  /sbin/tor  /sbin/zdb  /sbin/zfs
```

You can also mix different wildcards together:

```shell
 $ ls /bin/?g*
/bin/egrep          /bin/ngettext  /bin/sg      /bin/xgc
/bin/fgconsole      /bin/pgrep     /bin/tgz     /bin/zgrep
/bin/fgrep          /bin/qgltf     /bin/wget
/bin/kglobalaccel5  /bin/rgrep     /bin/xgamma
```
The above example will list all the files which its second character is g.

If you wanted to search for files that end with a specific character you can use * on its own. For example, all the files that finish in z in /bin:

```shell
$ ls /bin/*z
/bin/7z  /bin/lz  /bin/tgz  /bin/unxz  /bin/uz  /bin/xz
```

But you will need to use ? if you want to find all the files whose name have a z in the second to last character:

```shell
$ ls /bin/*z?
/bin/7za               /bin/python3-pasteurize
/bin/7zr               /bin/size
/bin/futurize          /bin/systemd-analyze
/bin/lz4               /bin/unlz4
/bin/pasteurize        /bin/x86_64-linux-gnu-size
/bin/python3-futurize
```

Obviously these examples might come across as weird but the point isn't about memorising everything. At this stage, if you are just starting with Linux, you just need to be aware that these kind of searches and selections are possible.

You can always come back and look things up if you get stuck (even experienced users do it!).

With time and practice these commands will become more natural so don't worry too much about learning everything in one go. 


## The range wildcard []
The last wildcard I will show you is the range. This one is similar to **?** but it will allow you to select a range of valid values.

For example, if you want to list all the files that start with a, b or c in /bin:

```shell
$ ls /bin/[abc]*
[...]
```

Remember that Linux is case-sensitive, so the above example would only work with files that start with a lowercase a, b or c.

Also, each range **[]** stands for a single character. You are just defining what are the range of characters you want to match.

The syntax for a range can be done in several ways. Some, but not all of them, are interchangeable:

```
[abc]   Characters a, b or c

[a,b,c] Characters a, b or c

[a-c]   Characters a to c

[a-b,d] Characters a to b and d
```

Ranges can also be used as an exclusion:

```
[!abc]   Any characters except a, b or c

[!a,b,c] Any characters except a, b or c

[!a-c]   Any characters not in range a to c

[!a-b,d] Any characters except a to b and d
```

When you mix all of the above you can generate very powerful and specific search strings.

For example, let's search for all files which its second character is a vowel and last character is a number in /bin:

```shell
$ ls /bin/?[aeiou]*[0-9]
/bin/base32          /bin/kiconfinder5  /bin/pinentry-gnome3
/bin/base64          /bin/kioclient5    /bin/pinentry-x11
/bin/bunzip2         /bin/linux32       /bin/ping4
/bin/diff3           /bin/linux64       /bin/ping6
/bin/foo2hbpl2       /bin/meinproc5     /bin/qaptworker3
/bin/keditfiletype5  /bin/perl5.30.0    /bin/uic3
```

Or all the files that start with an a and the second character isn't a vowel and fourth character is in the range p to z in /bin:

```shell
$ ls /bin/a[!aeiou]?[p-z]*
/bin/addpart    /bin/appres        /bin/apturl-gtk
/bin/addr2line  /bin/appstreamcli  /bin/aseqdump
/bin/amixer     /bin/apturl        /bin/aseqnet
```

## This is what Unix is about
All of this is a fine example of the Unix philosophy at work. A program will do one thing and one thing only, and it will do it really well.

**ls** is responsible to list files, a job that it does remarkably well. 

The command has many different arguments divided in three areas:

* **F**ormatting
* **S**orting
* **I**nformation displayed

Just see a selection of available arguments:

**Formatting**

Command | Type | Description
--------|------|------------
ls | I | list files
ls -l | FI | long listing format (will also sort alphabetically)
ls -la | FI | long listing format and all files (including hidden)
ls -lA |FI | don't list . and ..
ls -l –author | I | show the author of each file
ls -lsk | I | use kibibytes as the size unit
ls -1 | F | list one file per line
ls -d | I | list directories, not their content
ls -e | I | show ACLs (macOS)
ls -@ | I | display extended attribute keys (macOS)
ls -f | F | don't sort (enable -aU, disable -ls –color)
\ls | F | don't sort
ls -n| I | list numeric user and group IDs
ls -i | I | display the index number for each file
ls -m | F | display list of files in a line separated by commas
ls -tl | SI| sort by modification time, newest first
ls -u | S | sort by access time, newest first
ls -ult | FI | show and sort by access time
ls -ul | SI | show access time and sort by name
ls -U | S | do not sort, list entries in directory order
ls -X | S | sort alphabetically by entry extension
ls -c | S | sort by ctime, newest first
ls -clt | SI | show and sort by last modification date (ctime)
ls -cl |SI | show ctime and sort by name
ls --color=auto | F |
ls -C | F | list entries in a column
ls -x | F |list in lines instead of columns
ls -r | S |reverse order when sorting
ls -S | S | sort by file size, largest first
ls -Q | F |enclose names in double quotes
ls --full-time | I | display date with full detail
ls -g | I | long format showing group ownership but no file owner
ls -o | I | long format showing file owner but no group ownership
ls -lh | I | human readable file sizes in base 2
ls -l –si | I | human readable file sizes in base 10
ls --hide=PATTERN | F | do not display PATTERN in results
ls -lk | I | display size in kibibytes
ls -p | F | append the / symbol to the end of directories
ls -R | I | list contents of subdirectories recursively
ls -s | I | show the allocated size of each file in blocks
ls -F | I | append indicator (*	executable file, / directory, @	symbolic link /extended attributes, = socket, %	 white-out, | FIFO white-out,> doors (I believe Solaris only)

That is an very long list and it isn't complete but it illustrates the point that Unix is about specialised tools working together.

Right now it is only one command, but soon enough you will learn how to make commands interact with each other. That is the real power of the CLI. Each command is like a LEGO piece. On its own it can't do complicated builds, but the more pieces you have the more elaborate and elegant they can be.

The above list isn't meant to be memorised. You only need to know that **ls** has many arguments that can help you list files you need, in a specific order, with a given format and the information of your choice.

# 2.2.0 - Listing files key points
----------------------------------

## Commands
```shell
ls		List files
```

## Concepts
```
command [options] [arguments]
```

## Wildcards
```
*	Zero or more characters
?	One character
[]	Range of characters
```

## Ranges
```
[abc]   Characters a, b or c

[a,b,c] Characters a, b or c

[a-c]   Characters a to c

[a-b,d] Characters a to b and d

[!abc]   Any characters except a, b or c

[!a,b,c] Any characters except a, b or c

[!a-c]   Any characters not in range a to c

[!a-b,d] Any characters except a to b and d
```

## Unix philosophy
Individual specialised tools or programs that can easily interact between them to solve more complicated problems.


# Further reading
* _Robbins, Arnold_. **Bash Pocket Reference**, O'Reilly, 2010. **Pages 1-8**

* _Ward, Brian_. **How Linux Works, 2nd edition**, No Starch Press, 2015. **Chapter 2**

* _Negus, Christopher_. **Linux Bible, 9th edition**, Wiley, 2015. **Chapter 4**

* _Blum, Richard; Bresnahan, Christine_. **Linux Command Line and Shell Scripting Bible, 3rd edition**, Wiley, 2015. **Chapter 3 and 5**

* FreeBSD man page for ls in Debian 8.1.0 https://www.freebsd.org/cgi/man.cgi?query=ls&apropos=0&sektion=0&manpath=Debian+8.1.0&arch=default&format=html

# 2.2.2 - Listing files (EXERCISES)
-----------------------------------

## Exercises
1. List the contents of the folder above the one you are currently in without leaving it.
2. List all the files in the Downloads folder for all users with a single command.
3. List all the files in /usr/bin by reverse last modification date.
4. List all the files in /sbin based on their extension
5. List the permissions for the files in /sbin and /usr/bin that start with the letter a.
6. List all the files in /bin which second letter is an 'a' in a single column.
7. List the contents of /bin and /sbin with a single command.
8. List all the files in /bin that are exactly 5 characters long.
9. List all the files in /sbin which the second character is a vowel.
10. Using **cd** and **ls** navigate around your systems folders and familiarise yourself with the commands.

# 2.3.0 - Launching programs and creating aliases
-------------------------------------------------

## clear
Sometimes the output on the screen might make things too garbled or difficult to read. Specially if you are listing many different files.

You can easily clear the screen contents with the **clear** command.

```shell
$ clear
```

We will be seeing later on some keyboard shortcuts but you can achieve the same result with the keyboard combination of **Ctrl-L**. 

## Using the [TAB] key
The Bash shell has an autocompletion feature that is triggered with the tab key.

When you are typing a command, file or directory name, you can press the TAB key to autocomplete.

For example, type **l** and immediately after press TAB:

```shell
$ l[TAB]
Display all 126 possibilities? (y or n)
```

There are 126 commands that start with the letter l. The more characters you type the lower the options will and also the way those options are displayed:

```shell
$ ls[TAB]
ls           lsblk        lshw         lslocks      lsmod        lspci        lsusb        
lsar         lsb_release  lsinitramfs  lslogins     lsns         lspcmcia     
lsattr       lscpu        lsipc        lsmem        lsof         lspgpot
```

After you press the TAB the shell still expects you to press ENTER before accepting the commands. You can always delete and try again.

TAB will also autocomplete file and directory names. Experiment with it because it will save you a lot of typing.


## echo
In the first example, when you pressed the TAB key to autocomplete it showed that there were 126 matches. This is a huge list of commands. Those are all commands that are in your PATH variable. This works exactly the same as in DOS/Windows, when you type a command the directories that are in your PATH variable are searched and if that command is found, it is executed.

You can use the **echo** command to display messages, but also to show the value of system variables. System variables are traditionally uppercase.

```shell
$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

The result of the command shows all of the directories where commands and programs are searched for execution.

The other usage for **echo** is to display messages:

```shell
$ echo Hello
Hello
```

This doesn't look very useful at the moment, but if you develop shell scripts later on, you might want to display a message upon completion or when a certain action is taking place.


## Launching programs
We saw before that the $PATH variable indicates which directories are searched when you type a command.

Linux/Unix won't execute a program in the local folder like DOS/Windows does. Unless the directory is in the $PATH variable you need to explicitly indicate you want to execute a program.

This is done for security reasons. An attacker could create a program in a directory with the same name as a commonly invoked program and trick an administrator into executing it without realising that it is a local and malicious program.

If you want to execute a program and you want to explicitly indicate that it is a local one you will need to add **./** in the front.

Remember the directory reference characters from section 2.1? We used **..** for the directory above the current one and we mentioned **.** for the current directory.

This is what the dot in **./** indicates, the local directory. The forward slash **/** is to separate the directory from the file name, as you do with any path name that contains at least one directory and file.

So, to execute a a program in the local directory you will add the **./** in front:

```shell
$ cd /bin
$ ./lsusb
[...]
```

**./lsusb** will execute the program called _lsusb_ in the local folder (/bin)which lists your USB devices. This command will be seen in more detail later on, right now it is only used as an example on how to execute a program in your current directory.

If you also recall we spoke about relative and absolute paths. The **./** invocation is a relative path. You can use an absolute path to execute a program without having to change directories or if you want to execute a specific version, in case that more than one version is installed.

```shell
$ cd
$ /bin/lsusb
[...]
```

The above example executes the same program but without being in the same directory by using the absolute path.


## file
The command **file** will allow you to know what a file type is.

We have mentioned that in Unix/Linux file extensions aren't necessary. They are still used but not always. That means that many files don't have a file extension.

You can use **file** to get information about what type of file a given one is:

```shell
$ file /bin/lsusb
/bin/lsusb: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=3a9a52954527a4faa60a90b2388a9964c85e7bba, for GNU/Linux 3.2.0, stripped

$ file /etc/fstab 
/etc/fstab: ASCII text
```

In the above example one file is 64 bit executable and the other is a text file.


## Aliases
The last command we will learn in this section is **alias**.

**alias** allows you to create an alias for one or more commands. Without arguments it will display the existing aliases.

```shell
$ alias
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
```
 Your output might differ depending on the Linux distro you are using. This example shows the aliases on my system.

 We will create a new alias to list all files in human readable format:

 ```shell
 $ alias .='ls -lh'
 ```

Now when I type **.** it will execute the alias I have just created:

```shell
$ . /bin/lsusb 
-rwxr-xr-x 1 root root 243K Oct  1  2019 /bin/lsusb
```

You can edit an existing alias by just re-issuing:

```shell
 $ alias .='ls -gh'
 $ . /bin/lsusb 
-rwxr-xr-x 1 root 243K Oct  1  2019 /bin/lsusb
 ```

 Aliases are only valid for the current session unless they are stored. We won't be looking at this yet.

 If you want to remove an alias you can use **unalias**:

 ```shell
$ alias
alias .='ls -gh'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
$ unalias .
$ alias
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
```

In my output **ls** is an alias of the command of the same name. You can do this and it won't clash. Aliases will be executed ahead of the command if the names match. This can be useful if you want to force certain arguments on a command by default.

> alias ls='ls --color=auto'

If you want **ls** to be the command rather than the alias you can **unalias** it, but sometimes you just want the unaliased command temporarily.

You can achieve this by executing the command with a \ in front. This will tell the console that the command should be executed unaliased.

```shell
$ \ls
Desktop  Documents  Downloads  Images  Music  Pictures  Public  Templates  Videos
```

The only difference in this instance is that the unaliased **ls** won't colourise the output.

# 2.3.1 - Launching programs and creating aliases key points
------------------------------------------------------------

## Commands
```shell
clear       Clear the terminal screen
echo        Display messages or variable values
file        Display file type
alias       Set or edit an alias
unalias     Delete an alias
```

## Concepts
```
[TAB]               autocomplete
./executable        Launch local executable
/path/executable    Launch executable
\aliasname          Execute unaliased version of command
```

# Further reading
* _Robbins, Arnold_. **Bash Pocket Reference**, O'Reilly, 2010. **Pages 58 and 17**

* _Ward, Brian_. **How Linux Works, 2nd edition**, No Starch Press, 2015. **Chapter 2**

* _Blum, Richard; Bresnahan, Christine_. **Linux Command Line and Shell Scripting Bible, 3rd edition**, Wiley, 2015. **Chapters 3 and 5**

# 2.3.2 - Launching programs and creating aliases (EXERCISES)
-------------------------------------------------------------

## Exercises

1. Clear the screen of your terminal.
2. Display the value of your $PATH.
3. Using the autocomplete feature check how many commands start with an s in your system.
4. What type if file is _/etc/resolv.conf_?
5. What type of file is _/usr/bin_?
6. Check the exercises from the previous section and create some aliases for some of the ls commands you created.
7. Create an alias to list the current folder by just using . and one that goes back up one directory by typing ..
8. Check what happens when you manually unalias the aliases you have created.
9. How can you check that you have removed an alias?

# 2.4.0 - Getting help
----------------------

## man

We have seen that Linux comes with a lot of commands built in. It isn't realistic to expect anyone to remember all of the commands and all of their individual options.

Linux and Unix systems come with a set of reference manuals, and usually if a new command is installed it will at the time of installation add its own manuals to the system.

**man** stands for _manual_ and it is a program that acts as an interface for those system reference manuals.

**man** requires an argument, the name of the command you want information of.

For example, let's get some information about the **ls** command.

```shell
$ man ls
LS(1)                                                      User Commands                                                      LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...
```

You can use the arrow keys and scroll buttons (or space bar) to explore the manual entry for **ls**.

Have a look around and once you are finished press **q** to **q**uit.

We need to look two aspects of **man**. First, how we call the program, as in how we query help for specific commands. Second, how we navigate through the interface. 

Let's look at the first part. The syntax is the same as the first example:

```
man command_name
```


**man -f _page_**
(whatis)

**man -k *search_term***
(apropos)






man
	command [-x] {on|off} filename …

	-Anything between square brackets [] is optional.
	-Anything followed by an ellipsis … can be repeated
	-Curly braces {} mean that you should select one of the items separated by |

1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions, e.g. /etc/passwd
       6   Games
	   7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]


info
	?	Displays help information
	N	Moves to the next node
	P	Moves back to the previous node
	U	Moves up in the hierarchy
	L	Display the last info page read
	T	Top page for the topic
	Q	Quit

apropos (man -k)

whatis

A complete set of online man pages for different variants of Unix and Linux can be found at the FreeBSD documentation project: freebsd.org/cgi/man.cgi

man intro

man man

# Bibliography
--------------

## Technical
* _Robbins, Arnold_. **Bash Pocket Reference**, O'Reilly, 2010.

* _Ward, Brian_. **How Linux Works, 2nd edition**, No Starch Press, 2015.

* _Negus, Christopher_. **Linux Bible, 9th edition**, Wiley, 2015.

* _Blum, Richard; Bresnahan, Christine_. **Linux Command Line and Shell Scripting Bible, 3rd edition**, Wiley, 2015.

* _Nemeth, Evi; Snyder, Garth; Hein, Trent R.; Whaley, Ben; Mackin, Dan;  Garnett, James; Branca,Fabrizio; Mouat, Adrian_. **Unix and Linux System Administration Handbook, 5th edition**,  Pearson Addison-Wesley, 2018.

## Online Technical References

**FreeBSD collection of Unix and Linux manpages**
https://www.freebsd.org/cgi/man.cgi

_Hertzog, Raphaël; Mas, Roland Mas_. **The Debian Administrator's Handbook Buster from Discovery to Mastery**, 2003-2020  
https://debian-handbook.info/browse/stable/

**Product Documentation for Red Hat Enterprise Linux 8**
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/

## Other
* Williams, Sam. **Free as in Freedom: Richard Stallman's Crusade for Free Software**, O'Reilly, 2002.
--------------

# LICENSE
---------

Introduction to the Linux CLI by David Poves is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.


## You are free to:

> **Share** — copy and redistribute the material in any medium or format
> **Adapt** — remix, transform, and build upon the material

The licensor cannot revoke these freedoms as long as you follow the license terms.

## Under the following terms:

> **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.

> **NonCommercial** — You may not use the material for commercial purposes.

> **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

**No additional restrictions** — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

## Notices:

You do not have to comply with the license for elements of the material in the public domain or where your use is permitted by an applicable exception or limitation.

No warranties are given. The license may not give you all of the permissions necessary for your intended use. For example, other rights such as publicity, privacy, or moral rights may limit how you use the material.

------------
## creative commons

# Attribution-NonCommercial-ShareAlike 4.0 International

Creative Commons Corporation (“Creative Commons”) is not a law firm and does not provide legal services or legal advice. Distribution of Creative Commons public licenses does not create a lawyer-client or other relationship. Creative Commons makes its licenses and related information available on an “as-is” basis. Creative Commons gives no warranties regarding its licenses, any material licensed under their terms and conditions, or any related information. Creative Commons disclaims all liability for damages resulting from their use to the fullest extent possible.

### Using Creative Commons Public Licenses

Creative Commons public licenses provide a standard set of terms and conditions that creators and other rights holders may use to share original works of authorship and other material subject to copyright and certain other rights specified in the public license below. The following considerations are for informational purposes only, are not exhaustive, and do not form part of our licenses.

* __Considerations for licensors:__ Our public licenses are intended for use by those authorized to give the public permission to use material in ways otherwise restricted by copyright and certain other rights. Our licenses are irrevocable. Licensors should read and understand the terms and conditions of the license they choose before applying it. Licensors should also secure all rights necessary before applying our licenses so that the public can reuse the material as expected. Licensors should clearly mark any material not subject to the license. This includes other CC-licensed material, or material used under an exception or limitation to copyright. [More considerations for licensors](http://wiki.creativecommons.org/Considerations_for_licensors_and_licensees#Considerations_for_licensors).

* __Considerations for the public:__ By using one of our public licenses, a licensor grants the public permission to use the licensed material under specified terms and conditions. If the licensor’s permission is not necessary for any reason–for example, because of any applicable exception or limitation to copyright–then that use is not regulated by the license. Our licenses grant only permissions under copyright and certain other rights that a licensor has authority to grant. Use of the licensed material may still be restricted for other reasons, including because others have copyright or other rights in the material. A licensor may make special requests, such as asking that all changes be marked or described. Although not required by our licenses, you are encouraged to respect those requests where reasonable. [More considerations for the public](http://wiki.creativecommons.org/Considerations_for_licensors_and_licensees#Considerations_for_licensees).

## Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License

By exercising the Licensed Rights (defined below), You accept and agree to be bound by the terms and conditions of this Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License ("Public License"). To the extent this Public License may be interpreted as a contract, You are granted the Licensed Rights in consideration of Your acceptance of these terms and conditions, and the Licensor grants You such rights in consideration of benefits the Licensor receives from making the Licensed Material available under these terms and conditions.

### Section 1 – Definitions.

a. __Adapted Material__ means material subject to Copyright and Similar Rights that is derived from or based upon the Licensed Material and in which the Licensed Material is translated, altered, arranged, transformed, or otherwise modified in a manner requiring permission under the Copyright and Similar Rights held by the Licensor. For purposes of this Public License, where the Licensed Material is a musical work, performance, or sound recording, Adapted Material is always produced where the Licensed Material is synched in timed relation with a moving image.

b. __Adapter's License__ means the license You apply to Your Copyright and Similar Rights in Your contributions to Adapted Material in accordance with the terms and conditions of this Public License.

c. __BY-NC-SA Compatible License__ means a license listed at [creativecommons.org/compatiblelicenses](http://creativecommons.org/compatiblelicenses), approved by Creative Commons as essentially the equivalent of this Public License.

d. __Copyright and Similar Rights__ means copyright and/or similar rights closely related to copyright including, without limitation, performance, broadcast, sound recording, and Sui Generis Database Rights, without regard to how the rights are labeled or categorized. For purposes of this Public License, the rights specified in Section 2(b)(1)-(2) are not Copyright and Similar Rights.

e. __Effective Technological Measures__ means those measures that, in the absence of proper authority, may not be circumvented under laws fulfilling obligations under Article 11 of the WIPO Copyright Treaty adopted on December 20, 1996, and/or similar international agreements.

f. __Exceptions and Limitations__ means fair use, fair dealing, and/or any other exception or limitation to Copyright and Similar Rights that applies to Your use of the Licensed Material.

g. __License Elements__ means the license attributes listed in the name of a Creative Commons Public License. The License Elements of this Public License are Attribution, NonCommercial, and ShareAlike.

h. __Licensed Material__ means the artistic or literary work, database, or other material to which the Licensor applied this Public License.

i. __Licensed Rights__ means the rights granted to You subject to the terms and conditions of this Public License, which are limited to all Copyright and Similar Rights that apply to Your use of the Licensed Material and that the Licensor has authority to license.

j. __Licensor__ means the individual(s) or entity(ies) granting rights under this Public License.

k. __NonCommercial__ means not primarily intended for or directed towards commercial advantage or monetary compensation. For purposes of this Public License, the exchange of the Licensed Material for other material subject to Copyright and Similar Rights by digital file-sharing or similar means is NonCommercial provided there is no payment of monetary compensation in connection with the exchange.

l. __Share__ means to provide material to the public by any means or process that requires permission under the Licensed Rights, such as reproduction, public display, public performance, distribution, dissemination, communication, or importation, and to make material available to the public including in ways that members of the public may access the material from a place and at a time individually chosen by them.

m. __Sui Generis Database Rights__ means rights other than copyright resulting from Directive 96/9/EC of the European Parliament and of the Council of 11 March 1996 on the legal protection of databases, as amended and/or succeeded, as well as other essentially equivalent rights anywhere in the world.

n. __You__ means the individual or entity exercising the Licensed Rights under this Public License. Your has a corresponding meaning.

### Section 2 – Scope.

a. ___License grant.___

   1. Subject to the terms and conditions of this Public License, the Licensor hereby grants You a worldwide, royalty-free, non-sublicensable, non-exclusive, irrevocable license to exercise the Licensed Rights in the Licensed Material to:

        A. reproduce and Share the Licensed Material, in whole or in part, for NonCommercial purposes only; and

        B. produce, reproduce, and Share Adapted Material for NonCommercial purposes only.

   2. __Exceptions and Limitations.__ For the avoidance of doubt, where Exceptions and Limitations apply to Your use, this Public License does not apply, and You do not need to comply with its terms and conditions.

   3. __Term.__ The term of this Public License is specified in Section 6(a).

   4. __Media and formats; technical modifications allowed.__ The Licensor authorizes You to exercise the Licensed Rights in all media and formats whether now known or hereafter created, and to make technical modifications necessary to do so. The Licensor waives and/or agrees not to assert any right or authority to forbid You from making technical modifications necessary to exercise the Licensed Rights, including technical modifications necessary to circumvent Effective Technological Measures. For purposes of this Public License, simply making modifications authorized by this Section 2(a)(4) never produces Adapted Material.

   5. __Downstream recipients.__

        A. __Offer from the Licensor – Licensed Material.__ Every recipient of the Licensed Material automatically receives an offer from the Licensor to exercise the Licensed Rights under the terms and conditions of this Public License.

        B. __Additional offer from the Licensor – Adapted Material.__ Every recipient of Adapted Material from You automatically receives an offer from the Licensor to exercise the Licensed Rights in the Adapted Material under the conditions of the Adapter’s License You apply.

        C. __No downstream restrictions.__ You may not offer or impose any additional or different terms or conditions on, or apply any Effective Technological Measures to, the Licensed Material if doing so restricts exercise of the Licensed Rights by any recipient of the Licensed Material.

   6. __No endorsement.__ Nothing in this Public License constitutes or may be construed as permission to assert or imply that You are, or that Your use of the Licensed Material is, connected with, or sponsored, endorsed, or granted official status by, the Licensor or others designated to receive attribution as provided in Section 3(a)(1)(A)(i).

b. ___Other rights.___

   1. Moral rights, such as the right of integrity, are not licensed under this Public License, nor are publicity, privacy, and/or other similar personality rights; however, to the extent possible, the Licensor waives and/or agrees not to assert any such rights held by the Licensor to the limited extent necessary to allow You to exercise the Licensed Rights, but not otherwise.

   2. Patent and trademark rights are not licensed under this Public License.

   3. To the extent possible, the Licensor waives any right to collect royalties from You for the exercise of the Licensed Rights, whether directly or through a collecting society under any voluntary or waivable statutory or compulsory licensing scheme. In all other cases the Licensor expressly reserves any right to collect such royalties, including when the Licensed Material is used other than for NonCommercial purposes.

### Section 3 – License Conditions.

Your exercise of the Licensed Rights is expressly made subject to the following conditions.

a. ___Attribution.___

   1. If You Share the Licensed Material (including in modified form), You must:

       A. retain the following if it is supplied by the Licensor with the Licensed Material:

         i. identification of the creator(s) of the Licensed Material and any others designated to receive attribution, in any reasonable manner requested by the Licensor (including by pseudonym if designated);

         ii. a copyright notice;

         iii. a notice that refers to this Public License;

         iv. a notice that refers to the disclaimer of warranties;

         v. a URI or hyperlink to the Licensed Material to the extent reasonably practicable;

       B. indicate if You modified the Licensed Material and retain an indication of any previous modifications; and

       C. indicate the Licensed Material is licensed under this Public License, and include the text of, or the URI or hyperlink to, this Public License.

   2. You may satisfy the conditions in Section 3(a)(1) in any reasonable manner based on the medium, means, and context in which You Share the Licensed Material. For example, it may be reasonable to satisfy the conditions by providing a URI or hyperlink to a resource that includes the required information.

   3. If requested by the Licensor, You must remove any of the information required by Section 3(a)(1)(A) to the extent reasonably practicable.

b. ___ShareAlike.___

In addition to the conditions in Section 3(a), if You Share Adapted Material You produce, the following conditions also apply.

1. The Adapter’s License You apply must be a Creative Commons license with the same License Elements, this version or later, or a BY-NC-SA Compatible License.

2. You must include the text of, or the URI or hyperlink to, the Adapter's License You apply. You may satisfy this condition in any reasonable manner based on the medium, means, and context in which You Share Adapted Material.

3. You may not offer or impose any additional or different terms or conditions on, or apply any Effective Technological Measures to, Adapted Material that restrict exercise of the rights granted under the Adapter's License You apply.

### Section 4 – Sui Generis Database Rights.

Where the Licensed Rights include Sui Generis Database Rights that apply to Your use of the Licensed Material:

a. for the avoidance of doubt, Section 2(a)(1) grants You the right to extract, reuse, reproduce, and Share all or a substantial portion of the contents of the database for NonCommercial purposes only;

b. if You include all or a substantial portion of the database contents in a database in which You have Sui Generis Database Rights, then the database in which You have Sui Generis Database Rights (but not its individual contents) is Adapted Material, including for purposes of Section 3(b); and

c. You must comply with the conditions in Section 3(a) if You Share all or a substantial portion of the contents of the database.

For the avoidance of doubt, this Section 4 supplements and does not replace Your obligations under this Public License where the Licensed Rights include other Copyright and Similar Rights.

### Section 5 – Disclaimer of Warranties and Limitation of Liability.

a. __Unless otherwise separately undertaken by the Licensor, to the extent possible, the Licensor offers the Licensed Material as-is and as-available, and makes no representations or warranties of any kind concerning the Licensed Material, whether express, implied, statutory, or other. This includes, without limitation, warranties of title, merchantability, fitness for a particular purpose, non-infringement, absence of latent or other defects, accuracy, or the presence or absence of errors, whether or not known or discoverable. Where disclaimers of warranties are not allowed in full or in part, this disclaimer may not apply to You.__

b. __To the extent possible, in no event will the Licensor be liable to You on any legal theory (including, without limitation, negligence) or otherwise for any direct, special, indirect, incidental, consequential, punitive, exemplary, or other losses, costs, expenses, or damages arising out of this Public License or use of the Licensed Material, even if the Licensor has been advised of the possibility of such losses, costs, expenses, or damages. Where a limitation of liability is not allowed in full or in part, this limitation may not apply to You.__

c. The disclaimer of warranties and limitation of liability provided above shall be interpreted in a manner that, to the extent possible, most closely approximates an absolute disclaimer and waiver of all liability.

### Section 6 – Term and Termination.

a. This Public License applies for the term of the Copyright and Similar Rights licensed here. However, if You fail to comply with this Public License, then Your rights under this Public License terminate automatically.

b. Where Your right to use the Licensed Material has terminated under Section 6(a), it reinstates:

   1. automatically as of the date the violation is cured, provided it is cured within 30 days of Your discovery of the violation; or

   2. upon express reinstatement by the Licensor.

   For the avoidance of doubt, this Section 6(b) does not affect any right the Licensor may have to seek remedies for Your violations of this Public License.

c. For the avoidance of doubt, the Licensor may also offer the Licensed Material under separate terms or conditions or stop distributing the Licensed Material at any time; however, doing so will not terminate this Public License.

d. Sections 1, 5, 6, 7, and 8 survive termination of this Public License.

### Section 7 – Other Terms and Conditions.

a. The Licensor shall not be bound by any additional or different terms or conditions communicated by You unless expressly agreed.

b. Any arrangements, understandings, or agreements regarding the Licensed Material not stated herein are separate from and independent of the terms and conditions of this Public License.

### Section 8 – Interpretation.

a. For the avoidance of doubt, this Public License does not, and shall not be interpreted to, reduce, limit, restrict, or impose conditions on any use of the Licensed Material that could lawfully be made without permission under this Public License.

b. To the extent possible, if any provision of this Public License is deemed unenforceable, it shall be automatically reformed to the minimum extent necessary to make it enforceable. If the provision cannot be reformed, it shall be severed from this Public License without affecting the enforceability of the remaining terms and conditions.

c. No term or condition of this Public License will be waived and no failure to comply consented to unless expressly agreed to by the Licensor.

d. Nothing in this Public License constitutes or may be interpreted as a limitation upon, or waiver of, any privileges and immunities that apply to the Licensor or You, including from the legal processes of any jurisdiction or authority.

> Creative Commons is not a party to its public licenses. Notwithstanding, Creative Commons may elect to apply one of its public licenses to material it publishes and in those instances will be considered the “Licensor.” Except for the limited purpose of indicating that material is shared under a Creative Commons public license or as otherwise permitted by the Creative Commons policies published at [creativecommons.org/policies](http://creativecommons.org/policies), Creative Commons does not authorize the use of the trademark “Creative Commons” or any other trademark or logo of Creative Commons without its prior written consent including, without limitation, in connection with any unauthorized modifications to any of its public licenses or any other arrangements, understandings, or agreements concerning use of licensed material. For the avoidance of doubt, this paragraph does not form part of the public licenses.
>
> Creative Commons may be contacted at creativecommons.org