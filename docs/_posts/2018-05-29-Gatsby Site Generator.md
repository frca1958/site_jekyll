---
layout: post
title: "Gatsby site Generator"
---


## Installation and basic startup

### References

- [Gatsby Docs](https://www.gatsbyjs.org/docs/)
- [Git Docs](https://git-scm.com/doc)
- [Visual Studio Code](https://code.visualstudio.com/docs)

### Install gatsby

We will use the current development version of node:
```sh

$ nvm use node
Now using node v10.2.1 (npm v5.6.0)

$ nvm list
        v8.11.2
->      v10.2.1
default -> v8.11.2
node -> stable (-> v10.2.1) (default)
stable -> 10.2 (-> v10.2.1) (default)
iojs -> N/A (default)
lts/* -> lts/carbon (-> v8.11.2)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.14.2 (-> N/A)
lts/carbon -> v8.11.2

$ npm install --global gatsby-cli
...
$ cd Work/gatsby
$ gatsby new gatsby-site
$ cd gatsby-site
$ gatsby develop -H 0.0.0.0
```

Now it is possible to reach the server at ip:8000.

### Add Git version control

#### setup git

First create an empty repo on bitbucket (or other remote), and check its clone command to get the git url.
Add public ssh keys if necessary. 

Provide the key to ssh-agent if needed.
```sh
ssh-add-fc
#or
ssh-add <path-to-pem>
```

Now clone the repo.

```sh
git clone git@bitbucket.org:frca1958/gatsby-site.git
git status
#copy whatever you want, then
git add .
git commit -m "first commit"
git push
```

## Tutorial Notes - [see here](https://www.gatsbyjs.org/tutorial/)

### Using a starter to setup a new site

```sh
gatsby new tutorial-part-one https://github.com/gatsbyjs/gatsby-starter-hello-world
cd tutorial-part-one
gatsby develop -H 0.0.0.0
```

*Note: it turns out that watching changes is very memory intensive. At least 500MB is needed to avoid not-enough-space problems.*

### Using surge to make the site public

Surge.sh is a free site for static websites.


```sh
npm install -g surge
gatsby build
ls public
surge public
```
The last command returns a url where the site is deployed.

It is possible to build for a specific domain.
- Create a CNAME record in the DNS  
  ```gatsby.casier.nl	CNAME		na-west1.surge.sh```
- Create a file ./static/CNAME containing ```gatsby.casier.nl```
- Use ```surge public gatsby.casier.nl```

*Note: these free sites do not support https! Choose github for this.*

- To teardown a site, do this  
  ```surge teardown gatsby.casier.nl```

*Note: https is supported for surge.sh subdomains. Execute the last 2 steps with casier.surg.sh for instance.
- Create a file ./static/CNAME containing ```fc.surge.sh```
- Use ```surge public https://fc.surge.sh```





### Various

- I installed vscode using  
```sudo snap install --classic vscode```





