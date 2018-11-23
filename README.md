### Desired outcome:
- Possess the skills necessary to carry out independent vulnerability research
against binary applications.
- Have an intimate understanding of executable formats, program control flow at
the assembly level, and other low level concepts.
- Understand classic and contemporary vulnerabilities and exploitation techniques.
- Apply both source code auditing and binary reverse engineering to the
vulnerability discovery process.
- Be capable of exploiting vulnerabilities found in real world software as defined by
MITRE’s Critical Vulnerabilities and Exposures (CVE) system
- More topics include:
 ```
    Buffer Overflows
    Heap Exploitation
    Format String Exploits
    Return Oriented Programming
    Reverse Engineering
    Networking
    Linux Kernel
```
bla bla bla ... 

I want to learn how to Pwn!! 

![](https://vignette.wikia.nocookie.net/villains/images/4/4a/Wiki-logo.jpg)

### Foundamentals:
- [Binary Exploitation: x86 Assembly Crash Course](https://www.youtube.com/watch?v=75gBFiFtAb8)
- [Assembly Primer For Hackers ](https://www.youtube.com/watch?v=K0g-twyhmQ4)
- [Binary Hacking Course](http://www.liveoverflow.com/binary_hacking/)
- [Modern Binary Exploitation](http://security.cs.rpi.edu/courses/binexp-spring2015/) + [git](https://github.com/RPISEC/MBE)
- [Binary Exploitation ELI5– Part 1](https://hackernoon.com/binary-exploitation-eli5-part-1-9bc23855a3d8)
- [OSCP Guide. Where to start, what to read, how to practice.](https://blog.acheremisov.com/2018/01/oscp-guide-where-to-start-what-to-read-how-to-practice/)
- [(PoC||GTFO or PoC or GTFO)](https://www.alchemistowl.org/pocorgtfo/)
- [Smashing the Stack for Fun and  profit - Phrack](http://phrack.org/issues/49/14.html)

***
# The Journal
### 23/11/2018
I started today with the [lecture one](http://security.cs.rpi.edu/courses/binexp-spring2015/lectures/1/01_lecture.pdf), then I moved to read [this book chapter 2](https://repo.zenk-security.com/Techniques%20d.attaques%20%20.%20%20Failles/EN-Hacking_The_Art_of_Exploitation%201.pdf) about writing a simple vulnerable program to execute a stack overflow attack and gain root access. (in reality the chapter goes up to the heap overflow too).Then searching on google how to determine which is the proper shellcode to use, I ended up [here](https://dhavalkapil.com/blogs/Shellcode-Injection/).Interestingly, in his explenation he use a flag ```To disable the rest of security functions we will be using the following flags to compile:-fno-stack-protector -z execstack ```, a quick search on google brought up this [GCC Stack Protection Mechanisms](https://security.stackexchange.com/questions/158609/how-is-the-stack-protection-enforced-in-a-binary).

[Get shellcode of the binary using objdump:](https://www.commandlinefu.com/commands/view/12151/get-shellcode-of-the-binary-using-objdump)
```Bash
for i in $(objdump -d binary -M intel |grep "^ " |cut -f2); do echo -n "\x$i"; done;echo 
```
Then,

``` Bash
./vuln $(python -c 'print "\x90"*40 + "\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x89\xe2\x53\x89\xe1\xb0\x0b\xcd\x80" + "A"*47 + "\x20\xce\xff\xff"')
```

- [gdb output hex format](http://www.delorie.com/gnu/docs/gdb/gdb_55.html)
### 22/11/2018
The biggest challenge so far is to create a real plan of action , the resources online are pkently, but most of time these resources are redundant, depracated, inaccurate. Therefore a challenge before the challenge is to make a clear path of what I need to learn.


### 20/11/2018
- [writing-exploits-for-win32-systems-from-scratch](https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2016/june/writing-exploits-for-win32-systems-from-scratch/)

### 17/11/2018
There are 2 website you(I) need to check: http://www.fuzzysecurity.com/ and https://www.corelan.be/ these are holyBible2.0 of hacking resources. But, not the only one needed. For general reference on the topic https://null-byte.wonderhowto.com/how-to/exploit-development-everything-you-need-know-0167801/ and a [link](https://github.com/topics/exploit-development) to the github by topic.


***

### Resources: 
- [Linux Exploit Development Tutorial Series](http://www.fuzzysecurity.com/tutorials.html) 
- [HoleyBeep: Explanations and exploit in python](https://sigint.sh/#/holeybeep)
- [HoleyBeep: exploit in C](https://gist.github.com/fkt/5f8f9560ef54e11ff7df8bec09dc8f9a)
- [Ethical Hacking: Exploits](https://www.lynda.com/Linux-tutorials/Ethical-Hacking-Exploits/512724-2.html)
- [Pluralsight: Exploit Development and Execution with the Metasploit Framework](https://www.pluralsight.com/courses/exploit-development-execution-metasploit-framework)
- [Pluralsight: Security for Hackers and Developers: Exploit Development ](https://www.pluralsight.com/courses/exploit-development-security-hackers-developers)
- [Metasploit Unleashed – Free Ethical Hacking Course](https://www.offensive-security.com/metasploit-unleashed/)
- [A Study in Exploit Development by Anitian](https://www.anitian.com/a-study-in-exploit-development-part-1-setup-and-proof-of-concept/)
- [Exploit Development for Beginners Youtube](https://www.youtube.com/watch?v=tVDuuz60KKc)
- [Infosec guides](https://bitvijays.github.io/#)

### Other stuffs
- [Essential linux](https://bitvijays.github.io/LFF-ESS-P0B-LinuxEssentials.html)

### Other university security teams:
 - https://rpis.ec/
 - https://www.vusec.net/
 
### Books
- https://www.amazon.com/Penetration-Testing-Hands-Introduction-Hacking/dp/1593275641
- https://www.amazon.com/Kali-Linux-Revealed-Penetration-Distribution/dp/0997615605
- https://www.amazon.com/Metasploit-Penetration-Testers-David-Kennedy/dp/159327288X
- https://www.amazon.com/Rtfm-Red-Team-Field-Manual/dp/1494295504/
- [Hacking_The_Art_of_Exploitation](https://repo.zenk-security.com/Techniques%20d.attaques%20%20.%20%20Failles/EN-Hacking_The_Art_of_Exploitation%201.pdf)
- https://www.amazon.com/Shellcoders-Handbook-Discovering-Exploiting-Security/dp/047008023X
