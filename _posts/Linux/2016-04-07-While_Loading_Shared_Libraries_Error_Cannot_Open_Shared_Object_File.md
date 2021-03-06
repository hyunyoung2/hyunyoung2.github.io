---
layout: post
title: Error, Cannot Open Shared object file
subtitle: While Loading shared Libraries, Error happen, That error is "Cannot Open Shared object file"
category: Linux
tags: [error]
permalink: /2016-04-07-While_Loading_Shared_Libraries,_error_Cannot_Open_Shared_Object_File
---

In linux, there are both static(.a file) and dynamic(.so file).

To run ./db_bench executable compiled from rocksDB to benchmark SSD. I read the installation of <a href ="https://github.com/facebook/rocksdb/blob/master/INSTALL.md">facebook's install.md</a>. after I did, the problem happened

it was :

```shell
[hyunyoung.lee@localhost rocksdb]$ ./db_bench

./db_bench: error while loading shared libraries: libgflags.so.2: cannot open shared object file: No such file or directory
```

So I haved looking for way to make it. the solution refers to <a href = "https://lonesysadmin.net/2013/02/22/error-while-loading-shared-libraries-cannot-open-shared-object-file/">this site(lonesysadmin)</a>

# error, Cannot open shared object file : No such file or directory.
  
the article below refer to <a href = "https://lonesysadmin.net/2013/02/22/error-while-loading-shared-libraries-cannot-open-shared-object-file/">this site(lonesysadmin)</a>
After I watched "./db_bench: error while loading shared libraries: libgflags.so.2: cannot open shared object file: No such file or directory", I checked /usr/local/lib and the files are there.

there are five fixes, which <a href = "https://lonesysadmin.net/2013/02/22/error-while-loading-shared-libraries-cannot-open-shared-object-file/">this site(lonesysadmin)</a>. introduces. and the site divided five fixes into good idea & terrible idea. 

# Suboptimal Fixes / Terrible Ideas[0]
  
  * Install the libraries to /usr/lib instead of /usr/local/lib. 
  
   - I think of this is not good method because you're installing add-on software into a system directory, and you might introduce a conflict, overwrite a pre-existing library, and/or destablize other parts of the system. People complain about Windows being unstable, and this sort of thing is exactly why it gets unstable - installers overwrite system DLLs with their own all the time, Linux doesn't have something that deals with the problem, it just assumes that you know what you're doing. Such is the power of UNIX.
  
   - When you're building open-source software under a UNIX OS, you often use the "configure" command. You can change where the software installs by using the "prefix" flag.
  
    $ ./configure -prefix =/usr

   - this will also install all the binaries, header files, etc. into the system directories. If you were one of my system administrators I'd get on your case for doing this and make you go back and do it right. This isn't the right way. Don't do it this way. The right ways are simple, do those instead.

  * Make a symbolic link from /lib to the files in /usr/local/lib
  
   - This is less intrusive than installing everyhing to /usr, but It's still bad idea. 
  
    $ sudo ln -s /usr/loca/lib/libgflags.so.2 /usr/lib/libgflags.so.2
    $ sudo ldconfig

   - Obviously substitute the correct file name for libgflags.so.2. The 'ldconfig' command updates the system's dynamic library cache so it sees the chandged libraries.
   - Still, don't do this. Bad sysadmin.
  
  * Copy the files from /usr/local/lib into /usr/lib. 
  
   - this is even more of a bad idea than #2, because now you've got two sets of libraries, and if you ever have to patch or upgrade it, you'll probably forget about ont set. 
  
    $ sudo cp /usr/local/lib/libev.* /usr/lib    
    $ sudo ldconfig

   - With all these ideas you're also very likely to run afoul of the 32-bit vs 64-bit thing with newer OSes, where 32-bit libraries go in /usr/lib and 64-bit libraries go in /usr/lib64.it might work, it might not work, but the better ways are a heck of a lot simpler.
    
  
# Better Idea

  * Set the enviroment variable LD_LIBRARY_PATH to point to /usr/local/lib.
  
   - If you are new to UNIX/LINUX and don't know what shell you're running, use the 'ps' command to see the processes you're running. 
  
```shell
[hyunyoung.lee@localhost lib]$ ps
  PID TTY          TIME CMD
 5501 pts/0    00:00:00 bash
32736 pts/0    00:00:00 ps
```

  - Hey look, I'm running bash, so my command would be :
   
  export LD_LIBRARY_PATH="/usr/local/lib"

  - and you can put that into your ~/.bashrc so it's always there.
    
   Changing the environment is a per-user thing, so other users on the system will need to do this, or you'd need to put the fixes in /etc/bashrc, the system-wide login scripts. This fix is nice,though, if you don't have root-level privileges on a system, and/or want to install those things into your own home directory.
  
# Abolutely Simple, Best Fix Ever[2]

 * If you have root privileges on this Linux box, why not just ask the dynamic linker to check /usr/local/lib, too? 
  
  - Edit the file /etc/ld.so.conf and add "/usr/local/lib" on its own line at the bottom. DO NOT REMOVE THINGS FROM THIS FILE. When you're done, it might look somegthing like :

```shell
[hyunyoung.lee@localhost etc]$ cat /etc/ld.so.conf
include ld.so.conf.d/*.conf
/usr/local/lib
```

   or it might look completely different, with the exception of the last line. Run ldconfig to tell it to update the cache :
  
     $ sudo ldconfig

   You can check your work with :
  
    $ ldconfig -p  | grep local

```shell
[hyunyoung.lee@localhost etc]$ ldconfig -p | grep local
	libsvn_ra_local-1.so.0 (libc6,x86-64) => /lib64/libsvn_ra_local-1.so.0
[hyunyoung.lee@localhost etc]$ sudo ldconfig
[sudo] password for hyunyoung.lee: 
[hyunyoung.lee@localhost etc]$ ldconfig -p | grep local
	libsvn_ra_local-1.so.0 (libc6,x86-64) => /lib64/libsvn_ra_local-1.so.0
	libgflags_nothreads.so.2.2 (libc6,x86-64) => /usr/local/lib/libgflags_nothreads.so.2.2
	libgflags_nothreads.so.2 (libc6,x86-64) => /usr/local/lib/libgflags_nothreads.so.2
	libgflags_nothreads.so (libc6,x86-64) => /usr/local/lib/libgflags_nothreads.so
	libgflags.so.2.2 (libc6,x86-64) => /usr/local/lib/libgflags.so.2.2
	libgflags.so.2 (libc6,x86-64) => /usr/local/lib/libgflags.so.2
	libgflags.so (libc6,x86-64) => /usr/local/lib/libgflags.so
```

something above is my state on my system. You should see the stuff in /usr/local/lib show up now, and your binary works. Boy, that was easy, and you didn't make more work for yourself down the road, destablize the system, overwrite system files, or leave security vulnerabilities lying around.
 
so if you know more about library on the linux, refer to <a href = "http://www.ibm.com/developerworks/library/l-dynamic-libraries/">this site(ibm's l-dynamic-libraries)</a>

if you want brief detail. plead refers to <a href = "https://www.gnu.org/software/gsl/manual/html_node/Shared-Libraries.html">this site(gnu's Shared-Libraries)</a>
