# FireUp

FireUp use puppet to deploy ur ruby/rails code to VPS.

It contains `postgresql`, `redis` and `nginx` recipes.

## How to use FireUp

### Vagrant

```bash
git clone git://github.com/SaitoWu/fireup.git
cd fireup
gem install librarian-chef
librarian-chef install
vagrant up
```

vagrant ssh

```bash
sudo /vagrant/install.sh
```


## THANKS

[Vagarnt](http://vagrantup.com/)

[Railscast.com](http://railscasts.com/episodes/293-nginx-unicorn)

All of You!
