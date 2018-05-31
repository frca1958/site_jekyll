---
title: "Working with nodejs"
---

## Installing NVM

NVM has the same role for nodejs as rvm for ruby: managing different versions of the nodejs ecosystem.

```
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
```

Logout from gui and console, then re-login and install nodejs (here the lts and latest dev versions)
```
nvm --version
nvm ls-remote | grep Latest
# this shows the latest LTS versions.
nvm install v8.11.2
nvm install node
nvm ls
nvm use node
nvm use lts/carbon
nvm alias default node 
```


### Refs
[NVM github site](https://github.com/creationix/nvm)
[NodeJS site](https://nodejs.org/en/)
[DO tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04)
[Express example](https://expressjs.com/)
[Building a static site generator](https://hackernoon.com/building-a-simple-static-page-generator-with-node-js-4f58f680c47d)
