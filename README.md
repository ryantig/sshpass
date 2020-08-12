![travis-ci Build Status](https://api.travis-ci.com/ryantig/sshpass.svg?branch=master)
# sshpass
repo import from [sourceforge sshpass](https://sourceforge.net/p/sshpass/code/HEAD/tree/trunk/)


Just created a very simple travis-ci .travis.yml file, and it appears to be working.
Now this can build in ci for osx

```YAML
os: osx
osx_image: xcode12u
language: c
addons:
  homebrew:
    packages:
      autoconf
      automake
      libtool
before_script: autoreconf --install
script: ./configure && make && ./sshpass -h 2>/dev/null | grep -q used
```
