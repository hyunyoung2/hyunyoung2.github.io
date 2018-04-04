---
layout: post
title: pyvenv, venv, and virtualenv on python
subtitle: How to use virtual environment
category: Python
tags: [python, tip]
permalink: /2017/06/28/Virtual_Environment_With_Python/
bigimg: 
  - "/img/Image/BigImages/carmel.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/monterey.jpg" : "Monterey, CA (2016)"
  - "/img/Image/BigImages/stanford_dish.jpg" : "Stanford Dish, CA (2016)"
  - "/img/Image/BigImages/marian_beach_in_sanfran.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/carmel2.jpg" : "Carmel-by-the-Sea, CA (2016)"
  - "/img/Image/BigImages/marina.jpg" : "MRINA of San Francisco, CA (2016)"
  - "/img/Image/BigImages/sanfrancisco.jpg" : "San Francisco, CA (2016)"
---

Python has a greate functionality which is called Virtual environment.

Virtual environment you would use helps you manage a variety of library version. 

If you are python2.* user, you are used to virtualenv command like this:

{% highlight Shell linenos %}
$ virtualenv [environment_name]
# if you want to use a particular python vertion in virtual environment
# $ virtualenv -p python3 [environment_name]
{% endhighlight %}

When you type in thing above, you have to install virtualenv like this:

{% highlight Shell linenos %}
#If you have pip 
sudo pip insatll virtualenv
# if you have pip3
sudo pip install virtualenv
# Also you can use software management of linux like this:
sudo apt install pyton-virtualenv
{% endhighlight %}

If you are python3* user, you are used to pyenv or python3 -m venv [directory name you want to make to virtual environment]

i.e. since Python 3.4 python has moduel for virtual environment. 

So as soon as you install pyton 3 with command such as **sudo apt-get install python3-pip python3-dev**

you can create virtual environment typing like :

> python3 -m venv [direcotry name]

**BUT** If you want to use the way, Also pyvenv exists, 

install **python-venv** with apt like this:

> sudo apt install -y python-venv

Let's say we have already installed python-venv. 

In order to create virtual environment, I have typed in like this:

> pyvenv my_env

At the loction you type in the command above, my_env directory is created like this :

{% highlight Shell linenos %}
# hyunyoung2 @ hyunyoung2-desktop in ~/my_env [17:43:07] 
$ ll
total 20K
drwxrwxr-x 2 hyunyoung2 hyunyoung2 4.0K  4월  4 17:39 bin
drwxrwxr-x 2 hyunyoung2 hyunyoung2 4.0K  4월  4 17:39 include
drwxrwxr-x 3 hyunyoung2 hyunyoung2 4.0K  4월  4 17:39 lib
lrwxrwxrwx 1 hyunyoung2 hyunyoung2    3  4월  4 17:39 lib64 -> lib
-rw-rw-r-- 1 hyunyoung2 hyunyoung2   69  4월  4 17:39 pyvenv.cfg
drwxrwxr-x 3 hyunyoung2 hyunyoung2 4.0K  4월  4 17:39 share
{% endhighlight %}

So when you activate your virtual environment. you have to type in like this :

>  source bin/activate 

source command make the virtual enviroment actvative activate the file under bin direcotry like this

{% highlight Shell linenos %}
# hyunyoung2 @ hyunyoung2-desktop in ~/my_env [18:08:42] 
$ ll bin/ 
total 32K
-rw-r--r-- 1 hyunyoung2 hyunyoung2 2.1K  4월  4 17:39 activate
-rw-r--r-- 1 hyunyoung2 hyunyoung2 1.3K  4월  4 17:39 activate.csh
-rw-r--r-- 1 hyunyoung2 hyunyoung2 2.4K  4월  4 17:39 activate.fish
-rwxrwxr-x 1 hyunyoung2 hyunyoung2  252  4월  4 17:39 easy_install
-rwxrwxr-x 1 hyunyoung2 hyunyoung2  252  4월  4 17:39 easy_install-3.5
-rwxrwxr-x 1 hyunyoung2 hyunyoung2  224  4월  4 17:39 pip
-rwxrwxr-x 1 hyunyoung2 hyunyoung2  224  4월  4 17:39 pip3
-rwxrwxr-x 1 hyunyoung2 hyunyoung2  224  4월  4 17:39 pip3.5
lrwxrwxrwx 1 hyunyoung2 hyunyoung2    7  4월  4 17:39 python -> python3
lrwxrwxrwx 1 hyunyoung2 hyunyoung2   16  4월  4 17:39 python3 -> /usr/bin/python
{% endhighlight %}

{% highlight Shell linenos %}
# hyunyoung2 @ hyunyoung2-desktop in ~/my_env [17:42:07] 
$ source bin/activate 
(my_env) 
{% endhighlight %}

In my case of zsh, the beneth take the name of your virtual enviroment. 

At the time, if you install some module of pytohe with pip or pip3. This doesn't bother your real system(root) of python. 

Bucasue **PATH** variable was changed like this:

{% highlight Shell linenos %}
# After activating
# hyunyoung2 @ hyunyoung2-desktop in ~/my_env [18:16:58] 
$ echo $PATH
/home/hyunyoung2/my_env/bin:/usr/local/cuda-9.0/bin:/usr/local/cuda-9.0/bin:/home/hyunyoung2/bin:.......
(my_env) 

# After deactivating 
# hyunyoung2 @ hyunyoung2-desktop in ~/my_env [18:17:32] 
$ echo $PATH
/usr/local/cuda-9.0/bin:/usr/local/cuda-9.0/bin:/home/hyunyoung2/bin:/home/hyunyoung2/.local/bin:.......
{% endhighlight %}

Finally, If you don't want to use virtual environment, you have to deactivate the activated environment with the command like:

> deactivate

# Reference 
 
  - [CS231's Assignment1](http://cs231n.github.io/assignments2017/assignment1/)
  
  - [Virtual Python Environment](http://docs.python-guide.org/en/latest/dev/virtualenvs/)
  
  - [A introduction to venv](http://cewing.github.io/training.python_web/html/presentations/venv_intro.html)