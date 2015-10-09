---
layout: default
title: 恢复博客的写作环境
category: 博客搭建
comments: true
---

由于公司中使用的Linux操作系统为CentOS release 6.6 (Final)，所以最开始是希望可以在这个操作系统上搭建起我博客的写作环境，折腾了一天我放弃了，有空再看该怎么弄吧！

1. 安装Windows7
2. 安装VMware workstation
3. 下载Ubuntu14.04 LTS，在VMware workstation的虚拟机中安装
4. 下载ruby-2.2.3.tar.gz，并安装ruby-2.2.3

    ```
    cd /home/donghao
    wget http://cache.ruby-lang.org/pub/ruby/ruby-2.2.3.tar.gz
    tar zxvf ruby-2.2.3.tar.gz
    cd ruby-2.2.3
    ./configure
    sudo make
    sudo make install
    ruby -v
    ```

5. 下载rubygems-2.2.2.tgz，并安装rubygems-2.2.2

    ```
    cd /home/donghao
    wget http://production.cf.rubygems.org/rubygems/rubygems-2.2.2.tgz
    tar zxvf rubygems-2.2.2.tgz
    cd rubygems-2.2.2
    sudo ruby setup.rb
    gem -v
    ```

6. 安装zlib

    ```
    sudo apt-get install zlib1g-deb
    cd /home/donghao/ruby-2.2.3/ext/zlib/
    sudo ruby extconf.rb
    sudo make
    sudo make install
    ```

7. 安装Jekyll

    ```
    gem sources -r https://rubygems.org/
    gem sources -a http://rubygems.org/
    gem sources -l
    sudo gem install jekyll
    jekyll -v
    ```

8. 运行jekyll出现错误：Could not find a Javascript runtime，解决：

    ```
    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:chris-lea/node.js
    sudo apt-get update
    sudo apt-get install nodejs
    ```

9. 安装git，并设置

    ```
    sudo apt-get install git
    git config --global user.name "xiaofandh12"
    git config --global user.email "photodh@126.com"
    git config --list
    ```

10. 获取xiaofandh12.github.io

    ```
    cd /home/donghao/
    git clone https://github.com/xiaofandh12/xiaofandh12.github.io.git/
    ```

11. 写博客

    ```
    cd /home/donghao/xiaofandh12.github.io/
    git checkout source
    cd _posts
    使用Markdown，按照要求写好博客
    cd /home/donghao/xiaofandh12.github.io/
    make
    在浏览器中输入xiaofandh12.github.io即可看到了
    ```

12.
关于Openssl：可以看到我们的gem源使用的是http://rubygems.org/，而不是https://rubygems.org，原因就是没有安装Openssl，无法使用https://rubygems.org，而Openssl的安装总是出错，故就选择不安装Openssl了，幸好http://rubygems.org这个源没有出问题，不然没办法还得返回去安装Openssl。国内gem源很有名的就是https://ruby.taobao.org/，因为没有Openssl，所以无法使用，在网站ruby.taobao.org上我们看到了通知”我们将于2015年10月1日起停止http协议的镜像，请在配置中使用https协议代替“。哎，再早一点的话gem源应该还是可以使用http://ruby.taobao.org的。


