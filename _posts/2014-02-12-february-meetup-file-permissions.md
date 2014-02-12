---
layout: post
title: February Meetup - File permissions, Chrome Dev Tools
categories:
- linux
- dev_tools
- chrome
---

Our first meetup this year was compromised a bit by the bad weather, but there were 7 of us in the end and we had some good chats, not only about the chosen topics. 

True to my word (so far), I am putting up some documentation which for this time mainly consists of an example of working with file permissions. If you are like me this is something you often kind of 'muddled through' without knowing all the details. I have certainly benefited form looking more closely at it.

Chrome Dev Tools
----------------
For the Chrome Dev Tools, this is a good tutorial to work through: 
[http://discover-devtools.codeschool.com/](http://discover-devtools.codeschool.com/)

File Permissions and Ownership
------------------------------
To get an overview about file permissions and ownership in your current directory, use the <strong>ls</strong> with the -l flag (and -a for including dot files):

{% highlight bash %}    
  $ ls -al #for detailed information about files in current directory
  
  drwxrwxr-x  4 katja    katja    4096 Feb 11 00:06 .
  drwxrwxr-x 18 katja    katja    4096 Feb 11 00:04 ..
  -rw-r-----  1 katja    www-data   13 Feb 11 11:24 index.html
  drwxr-x---  4 katja    www-data 4096 Feb 11 00:27 modules
  drwxrwx---  2 www-data katja    4096 Feb 11 00:05 upload   
{% endhighlight %}  
You can also check a single file by using the comand like this: <strong>ls -l [filename] </strong>:

{% highlight bash %}    
  $ ls -dl index.html
    
  -rw-r-----  1 katja    www-data   13 Feb 11 11:24 index.html
{% endhighlight %}  

Each file is owned by a user(u) and a group user(g). A third category are all the other users(o).
<p>&nbsp;</p>

### CHMOD - Change permissions

The first column shows the set of permissions for the three types of users. 
There are many good resources on how the symbols map to the three user types, and how they can be translated into numbers, for example here:
[http://linuxcommand.org/lts0070.php](http://linuxcommand.org/lts0070.php)

For changing permissions, you can then use the <strong>chmod</strong> command with symbols, for example:
{% highlight bash %}   
  $ chmod ugo+rwx file
{% endhighlight %}
or using the numeric interpretation:
{% highlight bash %}   
  $ chmod 777 file
{% endhighlight %}
<p>&nbsp;</p>

### About users and groups
Each user belongs to a group. When a new user is created, as default option a group with the user's name will be created and the user assigned to it. 

In this example, we will work with three users: root, www-data (the server user - or apache user), and the login user

Some useful commands:

Who are you logged in as?
{% highlight bash %}
  $ whoami
  katja
{% endhighlight %}

What groups do you belong to?
{% highlight bash %}
  $ groups katja
  katja : katja adm dialout cdrom plugdev lpadmin admin sambashare
{% endhighlight %}

Some more information (IDs for the user and all the user's groups) :
{% highlight bash %}
  $ id  
  uid=1000(katja) gid=1000(katja) groups=1000(katja),4(adm),20(dialout),24(cdrom),46(plugdev),116(lpadmin),118(admin),124(sambashare)
{% endhighlight %}

A list of all users on the system can be found in the file /etc/passwd, a list of all groups in /etc/group. Caveat: On a Mac things seem to be [organised somewhat differently](http://superuser.com/questions/191330/users-in-etc-passwd-on-mac-os-x). 
<p>&nbsp;</p>

### CHOWN - Change ownership
Syntax:

chown [OPTION]... [OWNER][:[GROUP]] FILE...  

chown [OPTION]... --reference=RFILE FILE... 

We will see this in action below.

Note: For changing permissions, it is sufficient to be the file owner, for changing ownership you always need root access.
<p>&nbsp;</p>

### A practical example - Increase security by restricting access

In your home directory - or even a local website directory if you have one for testing -, create a folder called  'mycms', then cd into it

{% highlight bash %}
  $ mkdir mycms
  $ cd mycms
{% endhighlight %}

Inside our cms we create an index file, a modules directory with two modules, and an upload director.

{% highlight bash %}
  $ touch index.html
  $ mkdir modules upload
  $ cd modules 
  $ mkdir module1 module2
  $ cd ../

  # check with ls -al
{% endhighlight %}

What do we really need? The crucial thing is that the Apache user (www-data) needs to:<br />
\- read index.html<br />
\- read and traverse modules folders<br />
\- read and write to upload folder only<br />

How can we do that?<br />
\- Keep ownership and write access with the login user<br />
\- Change the group to that of the apache user, and assign it only read access<br />
\- The 'other' group will then not need any access at all for files being served<br />

So we change group ownership recursively for the modules. Then we can change the permissions of 'others' to 0 (---), that of the Apache user to 5 (r-x)

{% highlight bash %}
  $ sudo chown -R :www-data modules
  $ chmod -R 750 modules
{% endhighlight %}

Next, we change the group ownership for *index.html*. We don't need executing rights here, because it's a file, so we change permissions to 640 (- rw- r-- ---)
{% highlight bash %}
  $ sudo chown :www-data index.html
  $ sudo chmod 640 index.html
  
  # Check with ls -al 
{% endhighlight %}

Uploads is a special case, because *www-data* needs to write here as well. We could still have *www-data* as group owner, and give write permissions, but can just as well have *www-data* as the user owner of the directory, and have a group of users as the group owner. The 'others' group still does not need any rights.

{% highlight bash %}
  $ sudo chown www-data:cms-users upload
  $ sudo chmod 770 upload
  
  $ ls -al
  
  drwxrwxr-x  4 katja    katja    4096 Feb 11 00:06 .
  drwxrwxr-x 18 katja    katja    4096 Feb 11 00:04 ..
  -rw-r-----  1 katja    www-data   13 Feb 11 11:24 index.html
  drwxr-x---  4 katja    www-data 4096 Feb 11 00:27 modules
  drwxrwx---  2 www-data katja    4096 Feb 11 00:05 upload  
{% endhighlight %}

Question: What would be displayed if you have this running on a server, and you change the group of index.html back to your login user, but leave the permissions? 
<p>&nbsp;</p>

### Setting permissions recursively 
 
The above example was of course a very simplified version of a real CMS. You will often have many subdirectories with files and directories in there. In the [Wordpress Codex](http://codex.wordpress.org/Hardening_WordPress), there is a good recipe for setting permissions for both recursively. 

For Directories:
{% highlight bash %}
    
  $ find . -type d -exec chmod 755 {} \;
{% endhighlight %}

For Files:
{% highlight bash %}
    
  $ find . -type f -exec chmod 644 {} \;
{% endhighlight %}
<p>&nbsp;</p>

### References/Resources: 
Security through restricting access      
[https://drupal.org/node/244924](https://drupal.org/node/244924)
[http://codex.wordpress.org/Hardening_WordPress](http://codex.wordpress.org/Hardening_WordPress)
[http://blog.sucuri.net/2012/07/wordpress-and-server-hardening-taking-security-to-another-level.html](http://blog.sucuri.net/2012/07/wordpress-and-server-hardening-taking-security-to-another-level.html)
   
Also interesting: Four different ways to create a user
[http://www.thegeekstuff.com/2009/06/useradd-adduser-newuser-how-to-create-linux-users/](http://www.thegeekstuff.com/2009/06/useradd-adduser-newuser-how-to-create-linux-)users/)

Learning linux commands and shell scripting from scratch:
[http://linuxcommand.org/](http://linuxcommand.org/)
<p>&nbsp;</p>

   

 
 
      
      

      
      
    

   
    

   




    

   
    
     

    

    
     
    

   

  

