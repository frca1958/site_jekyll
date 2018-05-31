---
layout: post
title: "Working with Ruby"
---

## Intro

I think that programming environments should never be installed as root, unless there is no alternative.
Cases in point are ruby and nodejs (having different versions which need to remain separately available). 
Since each of these languages are really ecosystems with lots of related tools, switching versions often introduces difficult bugs.
So: no root installs for these tools.

For ruby, I have not really been happy with the shell modifying tools, but I did not find better:
- using a docker image might be nice, but there are problems with user permissions (e.g. mounting a volume gives root rights from the image to the host!)
- maybe lxd might be better, but I didn't find easily how to manage all the system resources.

## Installation of rvm

[RVM can be found here](https://github.com/rvm) along with tools such as an ansible playbook. 
However there are always problems with this , so I install according to the official guide:

```shell
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | rvm_ignore_dotfiles=yes bash -s stable
```

Now some changes are needed in the dotfiles. Since I start ubuntu in single user, and then start x, settings should be set in .profile only. So these instructions must be added to .profile:
```
#add at end of .profile
export PATH="$PATH:$HOME/.rvm/bin"
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*
```

Now logout complete (out of gui, out of console) and re-login. Check with ```rvm list known```


## Installation of ruby environment

```
rvm install ruby
rvm list
rvm alias create default ruby-2.4.1
rvm use default
```



