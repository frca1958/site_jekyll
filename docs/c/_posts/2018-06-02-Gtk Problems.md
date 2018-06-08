---
title: "Getting rid of Gtk Theme icon warnings"
---
## Intro
A recurring problem is this type of message:
```
Gtk-WARNING **: Error loading theme icon 'edit-clear' for stock:
```

What is this kind of problem and what to do about it?

## Refs

[The problem](https://jjacky.com/2013-10-08-fixing-the-gnome-3.10-upgrade/)

## So what to do?

Apparently, the problem is related to a decision of the Gnome folks to eliminate support for symbolic stock icons.
Which means that older applications will not find their icons anymore. Apart from the obvious stupidity of such a decision disrespecting users,
the question is what to do about it.

### Things that may have an effect

After a change of the icon theme, it may be useful to ```sudo update-icon-caches /usr/share/icons/*```.
It is possible to see the loaded icons (```sudo apt install gtk-3-examples``` then run ```gtk3-icon-browser```)


Maybe I should install ```sudo apt install gnome-icon-theme-symbolic```. I tried it, but nothing seems to happen.

Maybe I can find a better icon theme? I opened an application with gtk+ icon theme warnings, and with that on screen I selected other icon themes.
This gives some success:
- Theme Humanity-xx is OK
- Theme Ubuntu-Mono-xx is OK
- all other themes (adwaita,faba,lubuntu,moka,nuovext) have problems.

## Conclusion

I settled for Humanity-Dark.
