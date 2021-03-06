---
layout: post
title: Static Website with Jekyll
subtitle: What is the Jekyll ? and this is my summary about jekyll.
category: Web Programming
tags: [jekyll]
permalink: /2016/02/01/Static_Website/
bigimg: 
  - "/img/Image/BigImages/sanfrancisco.jpg" : "San Francisco, CA (2016)"
---

I recommend [this site](http://jekyllbootstrap.com/lessons/jekyll-introduction.html) for beginners to start jekyll. 

![](/img/Image/WebProgramming/2016-02-01-Static_Website/Jekyll.png)

- Jekyll은 static websites 생성 프레임워크이다. 이는 Ruby로 만들어 졌다. 이것은 Markdown 파일을 __posts 디렉토리에 생성하는 것만으로 멋진 static website를 만들어 준다. 

node.js 의 npm(Node Packaged Modules) 이 있는 것처럼 Ruby에도 gem이라는 것이 존재한다. 

즉  website를 구성하는데 필요한 라이브러리들을 Gemfile안에 작성한다. 

Gemfile은 내가 사용하는 라이브러리를 작성해놓고

“bundle install”이라는 instruction을 이용해서 Gemfile안에 있는 라이브러리를 한번에 설치가 가능하도록 하는 파일이다. 

config.yml 파일은 Jekyll의 모든 설정은 __config.yml파일에 저장되어진다. 즉 이 파일을 수정하여 우리에 맞는 설정으로 바꾸면 된다. 

Jekyll은 markdown 파일을 자동으로 정적 페이지로 만들어준다.

1. 파일 이름은 YYY-MM-dd-{제목}.md 형태로 만든다. 
2. Front Matter를 작성한다. Front Matter는 Jekyll이 정적 페이지를 만들때의 메타 정보를 기입하는 곳이다. 자세한 정보는 <a href = "http://jekyllrb.com/docs/frontmatter/">링크</a>를 참조한다. 

이 <a href = "http://jekyllrb.com/docs/frontmatter/" >블로그</a>를 이용하면 기본적인 Jekyll를 이용해서 github page 제작의 기본을 배울 수 있다. 

이 메모는 Jekyll 영문 사이트 내용을 요약한 글이다.

Jekyll은 static website generator이고 github pages을 생성하는 엔진으로 이용한다.

![](/img/Image/WebProgramming/2016-02-01-Static_Website/Jekyll2.png)
![](/img/Image/WebProgramming/2016-02-01-Static_Website/Jekyll3.png)
![](/img/Image/WebProgramming/2016-02-01-Static_Website/Jekyll_last.png)


# Reference 

 - [Jekyll's theme](http://jekyll.tips/templates/) shows you that kind of Jekyll's Theme
 
 - [Static generator's types](https://www.staticgen.com/) shows you how many types there is as static site generator.
