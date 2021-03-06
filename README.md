<p align="center">
    <a href="#deadsimplelog">
        <img alt="logo" src="asset/logo/200x200.png">
    </a>
</p>

# deadsimplelog

[![][build-img]][build]
[![][dependencies-img]][dependencies]
[![][devdependencies-img]][devdependencies]
[![][npm-img]][npm]

Configless static blog generator.  
Reads `.md` files from the current directory and generates a blog out of it into `html/`.

[build]:               https://travis-ci.org/tallesl/node-deadsimplelog
[build-img]:           https://travis-ci.org/tallesl/node-deadsimplelog.svg
[dependencies]:        https://david-dm.org/tallesl/node-deadsimplelog
[dependencies-img]:    https://david-dm.org/tallesl/node-deadsimplelog.svg
[devdependencies]:     https://david-dm.org/tallesl/node-deadsimplelog#info=devDependencies
[devDependencies-img]: https://david-dm.org/tallesl/node-deadsimplelog/dev-status.svg
[npm]:                 https://npmjs.com/package/deadsimplelog
[npm-img]:             https://badge.fury.io/js/deadsimplelog.svg

## Usage

Install it:

```
$ npm install -g deadsimplelog
```

Then run it on the desired folder:

```
$ deadsimplelog
```

## Timestamps and git

When using a git repository, you can change the file modification date to the author date of the git commit that created the file with the script(s) below.

Linux:

```sh
for article in *; do touch -d "$(git log --follow --format=%aD -- "$article" | tail -1)" "$article"; done;
```

Mac:

```sh
for article in *; do touch -t "$(date -r "$(git log --follow --format=%at -- "$article" | tail -1)" "+%Y%m%d%H%M.%S")" "$article"; done;
```
