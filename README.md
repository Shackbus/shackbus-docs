# Shackbus.org documentation

This repository contains the documentation shown at
[https://shackbus.org](https://shackbus.org). The documentation is written in
[Markdown syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
and compiled into HTML using the superb static website generator
[HUGO](https://gohugo.io).

## Install Hugo

### Windows & Linux

Go to Hugo's [download page](https://github.com/spf13/hugo/releases), download
the package for your architecture and install the lastest release.

### MacOS

Use the superb packet manager [Homebrew](http://brew.sh) and execute:

```sh
    $ brew update && brew install hugo
```

There are also more detailed installation instructions available on the
[Hugo website](https://gohugo.io/overview/installing/).

## Download Shackbus documentation

The easiest way to download the documentation is by doing a `git clone` of
this repository.

```sh
    $ git clone https://github.com/shackbus/shackbus-docs.git
```

If you expect to make (and submit) changes to the docs, the best would be
to create a Fork and then checkout your fork.

### Start local http server

Go the the path of the repository and execute

```sh
    $ cd shackbus.org
    $ hugo server -w --theme=hugo-material-docs
```

This will launch an http server at
[http://localhost:1313](http://localhost:1313) which you can access with your
favorite web browser.

Please note that the pages will automatically be refreshed whenever a file
has been modified.

## How to collaborate

You are welcome to improve the documentation. Please **Fork** this repository
and submit a **Pull Request** with your changes.

