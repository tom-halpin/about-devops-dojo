# Katacoda
GitHub pages to embed Katacoda scenarios

[https://github.dxc.com/pages/pberthonneau/about-devops-dojo/](https://github.dxc.com/pages/pberthonneau/about-devops-dojo/)

# Setting up a dev environment for contribution

These pages make use of the [Jekyll](https://jekyllrb.com/) static website generator, specifically version 3.2.1, which aligns to the GitHub Pages implementation in GitHub Enterprise 2.7.0. The Gemfile in this repo can be used with the `bundle` Ruby Gem to resolve dependencies for Jekyll, but first you need to have a suitable Ruby environment in place.

## Windows

A working configuration for Windows hasn't been found yet. Attempts using [RubyInstaller](https://rubyinstaller.org/downloads/) have failed when it comes to building the native components of the RedCarpet Gem (which is a dependency of Octopress).

Any Windows 10 users may wish to try the Ubuntu subsystem for Windows 10.

## Docker (on Linux)

If you don't already have Docker installed follow the platform appropriate Get Docker instructions from the [Docker Home Page](https://www.docker.com/).

- Run an interactive bash shell in a copy of the Ruby image mapping host port 4000 to container port 4000 (Jekyll default)  
```shell
sudo docker run -it -p 4000:4000 --name DXCjekyll ruby /bin/bash
```
- Generate an ssh key within the container and display the public key  
```shell
ssh-keygen -t rsa -f ~/.ssh/id_rsa -N '' && cat ~/.ssh/id_rsa.pub
```
- Copy the public key and paste into [GitHub > Settings > SSH Keys](https://github.com/settings/keys) > New SSH Key  

# Contributing

- The Katakoda content is in the separate Git repository [Online DevOps Dojo](https://github.com/pberthonneau/online-devops-dojo).

- Clone the repository and checkout gh-pages branch  
```shell
git clone git@github.dxc.com:pberthonneau/about-devops-dojo.git
```
- Change directory into the repo  
```shell
cd Katacoda
```
- Install Jekyll and its dependencies
```shell
bundle install
```
- Run the site locally  
```shell
bundle exec jekyll serve --host 0.0.0.0
```
- A version of the site will now be available on port 4000 of the dev environment
- If using Docker it's possible to attach another shell to the environment for editing using:
```shell
sudo docker exec -it DXCjekyll /bin/bash
```

We love Pull Requests for fixing or adding content. Thanks!
=======
https://github.dxc.com/pages/pberthonneau/about-devops-dojo/
