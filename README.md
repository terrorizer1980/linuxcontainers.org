# linuxcontainers.org

This branch contains the content and site generator of the
https://linuxcontainers.org website. Backend code for [Try it](https://linuxcontainers.org/lxd/try-it/)
part is located at https://github.com/lxc/lxd-demo-server

## Contributing

Fixes, new content and translations are greatly appreciated.
Read our [contributing guidelines](CONTRIBUTING.md) for details.

### Open Issues

Take a look at the [open issues on Github](https://github.com/lxc/linuxcontainers.org/issues/), to see where you could help.

For example:

* [Advanced Guide for LXD](https://github.com/lxc/linuxcontainers.org/issues/413)

## Generate & run a local copy

To generate & run a local copy of the website, follow the instructions below.

### Dependencies

Install the following software (naming may depends on your distribution):

 * man2html-base
 * python3 (>= 3.3)
 * python3-bs4
 * python3-jinja2
 * python3-markdown
 * python3-pygments

### Clone the repo

    git clone https://github.com/lxc/linuxcontainers.org
  
**Note:** The folder `downloads` is quite big, so you can skip that folder by using [git sparse-checkout](https://www.git-scm.com/docs/git-sparse-checkout) 
(The only exception is, when you work on the downloads page).

As a replacement for the missing `downloads` folder you need to create the following empty folders, before generating the website  (otherwise the generator shows an error):

```
downloads/cgmanager/
downloads/distrobuilder/  
downloads/lxc/  
downloads/lxcfs/  
downloads/lxd/
```

### Generating the website

    ./generate

### Launching the website 

After generating the website(above), run these commands(Ubuntu-specific):

    cd output
    python3 -m http.server 8777

Now you can access the website in your browser by using your local IP address and port:

    127.0.0.1:8777

#### (Alternative) Launching within a container 

**Inside the container:**

Install the dependencies, clone the repo and generate the website (same as above).

After generating the website, run these commands(Ubuntu-specific):

    cd output
    python3 -m http.server 8777

**On the host:**

You can now navigate to the site (in a browser of your choice) with the container's IP address, for example:

    185.5.3.12:8777

## Bug reports & Content requests

Bug reports, requests and ideas regarding the website can be filed at https://github.com/lxc/linuxcontainers.org/issues/new







