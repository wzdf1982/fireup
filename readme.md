# FireUp

FireUp use puppet to deploy ur ruby/rails code to VPS.

It contains `rvm`, `ruby`, `unicorn`, `mysql` and `nginx` recipes.

## How to use FireUp

### Vagrant

```bash
git clone git://github.com/SaitoWu/fireup.git
cd fireup
git submodule update --init

# edit example variables
vim manifests/base.pp
vagrant up
```

### VPS

```bash
./install.sh
```

## NOTICE

The current puppet(v2.7.x) is not compatibility with ruby 1.9.3.

The best version is ruby 1.8.7.
