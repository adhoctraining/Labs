 I pass CEH Practical Exam (18/20)
Post Exam Study Write Up

I took the exam today and scored 18/20. Below, I share my experience.

Personal context

I am an engineer and have worked with numerous virtual machines, around 80 or more. At the time, I completed the Pentester Jr path on TryHackMe, but stopped practicing for about 10 months. However, in the last month I resumed my studies. My work experience has been mainly in multinational corporations, with roles in cloud, telecom, audit and internal control.

Preparation

There are multiple guides available on GitHub and other platforms. For my preparation, I mainly studied EC-Council's eCourseware. The labs section at the end of the eCourseware was key. For the last month, I tried to do one virtual machine per day (although I didn't meet this goal every day, it worked overall). I practice with my machine on Kali Linux, with Zsh / Oh my Zsh and some of their plugins what I consider easier and visually appealing. In the exam, however, it is only Parrot OS, which has no command hints, plugins or shortcuts so you should consider it when practicing.

Exam experience

Exam rules

The exam is open book and allowed to be consulted on the internet, although many sites are blocked (such as HackTricks, Facebook, Reddit, etc.). I prepared my own command sheet and shared it on Google Drive. Only one monitor is allowed and you can't have your cell phone. You can go to the restroom but you must give notice, you have 15 minutes break and you can move around as long as you are in view of the camera.

Personal experience

The platform crashed in the morning and my user was locked out, which made me a bit nervous. I recommend checking credentials before starting the exam.

Examination procedure

I started with a good pace. The key is enumeration and having your notes organized. I identified the challenges that might take the most time, such as vulnerability scans and brute force attacks. It's important to find a personal balance between reading the questions and not getting overwhelmed. For me, I found it helpful to read them 5 by 5 to identify tasks that would take a long time.

Practicing constantly will give you confidence. I encountered a brute force attack that, despite using the maximum amount of threads, took me over 40 minutes.

I can say that maybe it was luck, but there were many challenges that involved brute force, or maybe I did not identify other attack vectors. In the first four hours, I had already completed 70% of the exam. However, in the last two hours I felt overwhelmed and noticed my weaknesses, especially in static analysis. I ended up reading the eCourse, although to my mind there are parts that are not well documented and rely on experimentation with the tools to see what results they yield.

I used the eCourse to identify which tool could solve each challenge and then practiced with the tool. Honestly, my lack of study or confidence that certain issues would not show up hurt me. Unfortunately, those topics did show up on the exam and facing something I had never practiced didn't turn out well.

The lesson is clear: you can't rely on luck and it is critical to prepare in every way possible before facing the exam.

Tools that I consider important

Below, I share the tools and techniques that I used or found useful during the exam. They are not all of them, but they are the ones I remember:

    DVWA: Damn Vulnerable Web Application to practice web vulnerabilities.

    WordPress/WPScan

    Smbclient: Useful tool to interact with SMB services.

    Privilege escalation on Windows and Linux: Essential techniques for gaining privileged access on both operating systems.

    SQLMap/BurpSuite:

    Hydra

    Nmap: is the exam base

    OpenVAS: Vulnerability scanning tool, although time-consuming.

    Password cracking:

        aircrack-ng: For wireless networks.

        Hashcat/John the Ripper/rainbow tables: For cracking password hashes.

    Static analysis : This was my weakest area, as I didn't study it enough.

        IDA Pro

        snow

        OpenStego:

    VeraCrypt

    Wireshark:

        Filters

        Common protocols MQTT http post / gest

        Identification of DoS attacks.

        Packet statistics analysis.

    Identification of common service ports

        MySQL: 3306

        MSSQL: 1433

        RDP: 3389

        VNC: 5900

        Web: 80 (HTTP), 8080, 443, 8443

        LDAP: 389

        SMB: 445

    There are basic techniques that you usually use on a ctf

        Reverse Shell

        Web Shell

        Share Files SCP / HTTP servers in Python

        Netcat / nc -lvnp (PORT)

        Identifying hashes

        File search with find / Practicing on platforms like OverTheWire can improve your Linux skills.

    Tools that you do not practice and neglect

        Phonesploit

        RATs (Remote Access Trojans): There are multiple tools and techniques, and it is important to be familiar with them.

        ELF files: Analysis of executable files on Linux. The Die tool is useful for this.

        Snow: Tool for steganography in text files. Identifies files with many blank spaces.

        Hex files: Interpretation and analysis of files in hexadecimal format.

        OpenStego: Allows to hide files without password. Not knowing this made me lose a lot of time.

Recommendations

    Read the questions carefully: The questions may contain a lot of irrelevant information. Concentrate on what is specifically asked of you.

        Example: “You are a security researcher blah blah blah blah ... you have found a compromised system that blah blah blah ... the system has many services among them MySQL blah blah blah blah .... What is the IP of the MySQL server on the network 10.10.10.10.10?"

            Just want the IP of a server with MYSQ

    Stay focused on the key question to avoid distractions: Beware of rabbit holes: there are many traps and false flags that are worthless. Stay focused and don't get sidetracked.

        Example: The flag is located in the root of the windows3000 server in a file iamwindows3000.txt, but as you escalate privileges you find flag.txt files that don't bring any important information.

    Organize your notes effectively, as you will be working with multiple networks and hosts, some of them very similar. Organization is crucial to identify where you have already scanned, listed and what you have found. This skill develops with experience, i.e., by practicing and refining your own method of organization. In addition, reviewing the notes of others can be useful to learn different approaches and improve your own organization system.

    Analyze and prioritize challenges strategically. One approach that worked for me was to read five questions at a time to identify potentially time-consuming procedures. I recommend addressing the answers in the following order:

        Vulnerability scanning tools.

        Brute force attacks

        Enumeration scripts

        Privilege escalation scripts

        Other procedures

Machines / CTF that I would recommend

Next I am going to share a series of virtual machines that I consider that can help you, I am not sponsored by tryhackme (hopefully they can haha) but I consider that it is the best between what it offers and what you have to pay (I also like hackthebox but I am more used to tryhackme).

There is probably not a definitive list of recommendations, so I would appreciate if anyone who considers that any machine has been helpful to them to add it in the comments. In particular, I recommend doing the official labs to familiarize yourself with the platform and exam scenario. From my perspective, EC-Council sometimes uses very specific tools that are not common in CTFs.

    Wordpress:https://tryhackme.com/r/room/wordpresscve202129447

    DVWA https://tryhackme.com/r/room/dvwa or https://github.com/digininja/DVWA

    Hydra https://tryhackme.com/r/room/hydra

    SQL injection https://tryhackme.com/r/room/sqlinjectionlm

    SQLMap https://tryhackme.com/r/room/sqlmap

    OpenVas https://tryhackme.com/r/room/openvas

    https://tryhackme.com/r/room/expose

    Burpsuite https://tryhackme.com/module/learn-burp-suite or https://portswigger.net/

