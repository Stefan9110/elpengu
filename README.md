<img align="right" src="https://elpengu.com/logos/elpengu.png" height="235" width="235">

# [ElPengu website](https://elpengu.com)

**ElPengu** is a site about **software freedom**. Created in 2021, this site aims to promote the benefits of software freedom to as many people as possible, in a layout that reminds of the old web days, but at the same time provides modern features and design. This website is also used as a homepage for the many privacy-friendly instances hosted on my server.
ElPengu uses **no javascript, trackers or ads** and is statically generated using **Hugo**.

## Hugo
This website is built with [Hugo](https://gohugo.io/). If you don't have
already make sure to install it.
* Arch Linux
```sh
$ sudo pacman -S hugo
```
* Debian
```sh
$ sudo apt install hugo
```
* Default
```sh
$ sudo go install github.com/gohugoio/hugo@latest
```

## How to build
First, pull the root directory to your filesystem:
```sh
$ git pull https://git.elpengu.com/stefan911/elpengu.git
$ cd elpengu/
```
Using hugo, this site can be easily built using:
```sh
$ hugo
```

All static files are then put in the `public/` directory, found in the
project's source root directory.

## ElPengu's site script
The `blog` script can be found in `./script/blog`. To start using this script
simply symlink it to a directory present in your `$PATH`.
```sh
$ ln -s $(realpath script/blog) $HOME/.local/bin
```

### Usage:
* Create or edit a new blog post
```sh
$ blog edit <post_name>
```
* Delte a post (move it to `./.trash/`)
```sh
$ blog remove <post_name>
```
* Publish site
```sh
$ blog publish
```

### Editing the script
You might want to edit the script to modify some variables, such as the editor
the file is opened in or to integrate the `sync-elpengu` additional script into
its source.

## Deploying
Deploying can be either done by copying all files from `public/` after build to
a server, or by using the [elpengu site script](#elpengus-site-script).

If you want to use the `blog publish` functionality, you must create a new
script in the `~/.local/bin` directory, with the name `sync-elpengu`. This
script is not published on github to preserver personal information.

1. Install rsync

Rsync should already come installed on your server. You need to have rsync
installed on **both your machine and your server**.

```sh
# Arch Linux
$ sudo pacman -S rsync
```

```sh
# Debian
$ sudo apt install rsync
```

2. Edit the `~/.local/bin/sync-elpengu` file
```sh
# Use your favourite text editor
$ vim ~/.local/bin/sync-elpengu
```
3. Paste and edit the following into the file:
```sh
#!/bin/sh
rsync -avW $1 SSH_USERNAME@YOUR_SERVER_HOST:/PATH_TO_YOUR_WEBPAGE_ROOTDIR --delete
```
4. Replace variables with your specific server information and save the file.

**Example**:
```sh
#!/bin/sh
rsync -avW $1 root@example.com:/var/www/site --delete
```

5. When done, add execute permissions.
```sh
$ chmod +x ~/.local/bin/sync-elpengu
```

6. Now you can easily deploy your site using
```sh
$ blog publish
```

#### ! ! ! Rsync permissions
Your site directory must have read and write permissions for the user you are
logging in with. To ensure this, simply change your site directory's owner to
the user you are **ssh logging in** with.

```sh
$ chown your_user /path/to/dir
```

## License
This project is licensed under `AGPL-3.0`. For more information about
licensing, please see the
[LICENSE](https://github.com/Stefan9110/elpengu/blob/master/LICENSE) file.
