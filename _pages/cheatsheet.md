---
permalink: /cheatsheet/
title: "Code Snippet Cheatsheet"
author_profile: true
redirect_from: 
  - /cheatsheet.html
---

## Unix Server Commands

* Use [setfacl](https://linux.die.net/man/1/setfacl) to control file access groups
  * Grant `siconghuang` *read*, *write*, and *execute* access to the `/data/datasets/` directory
> ```setfacl -R -m u:siconghuang:rwx /data/datasets/ ``` 

* Use [tmux](https://tmuxcheatsheet.com/) to create a persistent window for long experiments or persistent processes 
  * Create a new persistent window named `sicong`
> ``` tmux new -s sicong```
  * Detach from a persistent window 
> Press `Ctrl` + `B`, then press `D`
  * list all existing persistent windows 
> ``` tmux ls ```
  * attach to the persistent window named `sicong`
> ``` tmux a -t sicong ```
  * If you (sadly) don't have tmux, try [screen](https://linux.die.net/man/1/screen)

* To check server space
  * Use [df](https://linux.die.net/man/1/df) to check the entire storage space 
> ``` df -h ```
  * Use [du](https://linux.die.net/man/1/du) to check the `/data/datasets/` diectory
> ``` du -sh /data/datasets/ ```

* To find a file or directory from a scoped directory
  * Use [find](https://www.cyberciti.biz/faq/howto-find-a-directory-linux-command/) to locate directories with keyword `MNIST` from `/data/datasets/` directory
> ``` find /data/datasets/ -type d -name "MNIST" ```

* To reload swap memory memory
  * Use [swapoff/swapon](https://www.redhat.com/sysadmin/clear-swap-linux#:~:text=To%20clear%20the%20swap%20memory,in%20swap%20and%20in%20RAM.) to switch on and off
> ``` free -m; swapoff -a; swapon -a; free -m ```