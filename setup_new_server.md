# Setup New Ubuntu 16.04 for Python Server

Do like in [Digital Oceans](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-16-04-server#step-2-—-setting-up-a-virtual-environment)

To install Virtualenv:
```
sudo apt-get install virtualenv
```

If ``setuptools pkg_resources pip wheel failed with error code 1`` :

```
export LC_ALL="en_US.UTF-8"

export LC_CTYPE="en_US.UTF-8"
```
