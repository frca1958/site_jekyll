---
layout: post
title: "Linux Commands"
---

## About apt

- apt policy *pkg*

  This shows the installed version of *pkg*
  
- test



# About LXDE

[About customization](https://www.addictivetips.com/ubuntu-linux-tips/customize-the-lxde-desktop/)

- Selecting Themes

A simple tool to choose better theme (I like Breeze-ob)
```
sudo apt install obconf
```

- Install other icons

Icon themes take around 100MB.
If you have access to the icon-theme file (xxx.tar.gz), then you can untar it in folder ~/.icons  
Then start Preferences -> Look and Feel -> Select icon-theme -> Apply

Some icon sets are available through launchpad
```
sudo add-apt-repository ppa:moka/daily
sudo apt-get update
sudo apt-get install moka-icon-theme
```


# About logging

#### sudo
Logs are by default available in /var/log/auth.log.
An easy way to extract all commands is this:
```
sudo grep COMMAND /var/log/auth.log | sed -n -e 's/^.*COMMAND=//p'
# -n: no printing
# p suffix: print result
```

#### user history

When using multiple terminals, user history is not correct. 
One way to solve this is to force a history append after every command by adding this in .bashrc
```
shopt -s histappend
PROMPT_COMMAND="history -a;$PROMPT_COMMAND"
```
Alternative is to create a second log.
```
[[ -d ~/.logs ]] || mkdir ~/.logs
PROMPT_COMMAND='echo -e "$(date "+%H:%M:%S")\t$(tty)\t$(pwd)\t$(history 1)" >> ~/.logs/bash-$(date +%Y-%m-%d).log;'
```

[Advanced use](https://www.digitalocean.com/community/tutorials/how-to-use-bash-history-commands-and-expansions-on-a-linux-vps)

