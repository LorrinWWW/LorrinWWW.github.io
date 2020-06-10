---
title: CheatSheet for Setting up New VPS
date: 2020-02-09 16:18:11
categories: other
tags: [vps]
---

# Basics

## Create New Users

first login in the root account.

to add a user:

```bash
adduser [UserName]
```

if want it to have sudo privilege, then:

~~~bash
usermod -aG sudo [UserName]
~~~

## Set Up SSH Config

add these to ~/.ssh/config

```
Host [ShortNameForTheVPS]
HostName [ItsIPOrDomain]
User [TheUserToLogin]
IdentitiesOnly yes
```

if you want to ssh via proxy, for MacOS users:

```
Host [ShortNameForTheVPS]
HostName [ItsIPOrDomain]
ProxyCommand nc -X 5 -x 127.0.0.1:1082 %h %p
User [TheUserToLogin]
IdentitiesOnly yes
```

-X 5 means using socks5; -x specify proxy server ip and port.

then ssh-copy-id, so we don't have to type password every time we ssh:

```bash
ssh-copy-id [ShortNameForTheVPS]
```

As the result, we only need to type to login:

```bash
ssh [ShortNameForTheVPS]
```

## Powerful Vim

Life is short, I use spf13.

```bash
curl https://j.mp/spf13-vim3 -L > spf13-vim.sh && sh spf13-vim.sh
```

if every thing goes fine, it will usually take within 5 minnutes.

## Powerful Zsh

Bash is good but Zsh is better. For ubuntu users:

```bash
sudo apt install zsh
```

Again, life is short, I use oh-my-zsh.

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

it is installed instantly.

# Network Related

Usually it is suggested to expose ports as few as possible, and only preserve 80(HTTP) and 443(HTTPS).

We can use nginx/caddy/... to do HTTP(S) reverse proxy.

## Caddy

install go

```bash
sudo apt install golang
```

install caddy. we choose caddy 1 here.

```bash
curl https://getcaddy.com | bash -s personal
```

run caddy, and it should run as a simple server on port 2015. it should return 404 when visit.

```bash
caddy
```

to run caddy as server, follow instructions [here](https://github.com/caddyserver/caddy/tree/master/dist/init/linux-systemd).

to use CloudFlare CDN, follow instuctions [here(chinese)](https://melty.land/blog/caddy-and-cloudflare)

# Scientific Purpose

e.g. interactive demo.

## Python Environment

download anaconda, the latest address can be found [here](https://www.anaconda.com/distribution/).

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2019.10-Linux-x86_64.sh
```

install it.

```bash
bash Anaconda3-2019.10-Linux-x86_64.sh
```

if use zsh, the install script won't add initialization script to .zshrc, so we need to copy from .bashrc

re-login, so the initialization script will work.

install pytorch will be another long story, so we won't go in deep here.

