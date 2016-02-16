NPM packages that I care about.  Disclaimer: if you choose to use this project
directly, packages may appear/disappear and/or history may be rewritten at any
time.

# Quick start
```
$ npm i -g npm-proxy-cache
$ git clone https://github.com/mvines/npm-package-cache.git
$ npm-proxy-cache -f -s npm-package-cache --ttl 307584000 --expired --port 4242
$ npm config set https-proxy http://localhost:4242/
$ npm config set proxy http://localhost:4242/
$ export DISABLE_NODE_MODULES_CACHE=1
```

# Refresh
```
$ cd npm-package-cache
$ git pull --rebase
```

# Caveats
When a new package version is published, you need to manually go into the cache
and erase the metadata so that npm will fetch from the upstream registry.
Imagine the new version of left-pad is published and you want it, you need to
manually do this:
```
$ ls -l npm-package-cache/l/e/f/left-pad
-rw-rw-r-- 1 mvines 4920 Feb 16 21:30 npm-package-cache/l/e/f/left-pad
-rw-rw-r-- 1 mvines  664 Feb 16 21:30 npm-package-cache/l/e/f/left-pad-0.0.3.tgz
$ rm /ws/npmcache/l/e/f/left-pad
```

