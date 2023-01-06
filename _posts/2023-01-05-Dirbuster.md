---
# Dirbuster

### 2023-01-05
---
## Guides




# **Using Dirbuster**

### _Dirbuster is a web application security tool that is used to brute-force directories and files in web applications By brute-forcing directories and files, Dirbuster helps web application security professionals identify vulnerabilities in web applications that can be exploited by hackers._

_For the purpose of brute-forcing directory and file names on web and application servers, DirBuster is a multi-threaded Java program. Nowadays, it's fairly uncommon for what seems to be a web server in its initial, unmodified condition to really include additional pages and apps. This is something that DirBuster looks for. DirBuster is a program that looks for inaccessible files and directories on a website server. Web designers may sometimes "orphan" a page, meaning they will leave it up but not connect to it. DirBuster's function is to uncover such security holes. DirBuster looks for these orphaned files and directories in order to protect the website from potential security risks._

_DirBuster may improve application security by locating data on the web server or inside the application that is unnecessary (or shouldn't even be public) or by making it clear that omitting a link to a page is not the same as preventing access to that page. This tutorial will teach you how to do a brute force scan on a website to unearth (potentially hidden) folders and files._

  
* Start DirBuster.  
DirBuster has two possible methods of being launched: First, click the "dirbuster" symbol.  
Simply put "DirBuster" into Kali Linux's search bar, and the software will show up in the results:  
If you double-click the shortcut, the program will launch. The first stop is the terminal.  
You may also launch DirBuster from the command line by typing:  
dirbuster

* And then you may launch DirBuster:In the case of port 80, you should be presented with a user interface that lists files and folders.

  
* Determine the destination URL and thread count.  
Obviously, you'll have to provide the web address (URL) or IP address of the location from which you'd want to gather information; however, the URL you use must also include the scan port. For the most part, the World Wide Web (www) operates on port 80. For incoming connections from web browsers, web servers expose port 80. Like how a computer believes a web server is always running and listening on port 80 when given an IP address, a web browser will always presume a web server is running and listening on a distant address. Adding a "double point" and the number of the port at the end of the URL, is all that's needed to specify port 80 in the URL.

* It is entirely dependent on your computer's hardware to determine how many threads will be employed to carry out the brute force. Because our machine isn't very powerful and we need to multitask, we'll be restricting the DirBuster scan to 20 threads in this case.

  
_You'll need to choose from a list of potential folders and files._

  
* To do a brute-force scan, DirBuster requires a list of terms. However, you need not worry about creating your own list or searching for one on the Internet since DirBuster already has a couple of significant and helpful lists that may be utilized for your assault. To begin a brute-force scan, just click the Browser button and go to the wordlist file you want to use (often found in /usr/share/dirbuster/wordlists).Directory List 2.3, Medium.txt, will be used in this example.

  
* If you discover that the dictionaries that come with DirBuster aren't enough, you may always obtain more online (in this repository, you will find some useful lists too).4. Begin a full-on, manual search.

* Simply clicking the Start button on the user interface will start the website scan. At this point, DirBuster will search the provided URL for potentially hidden files and folders, providing another entry point for an attacker. uncovering a hidden control panel).

  
_The scan may be made faster by adjusting the number of threads used in accordance with your computer's capabilities. There were originally just 20 threads, but we increased it to 30. Optionally, the report should be generated._

  
* After the scan is complete or you pause the application, the Report button will become active. A report window is provided for exporting the scanned urls of the identified directories and files into several formats, such as plain text, XML, or CSV. Just enter your information and hit the "Generate Report" button.
