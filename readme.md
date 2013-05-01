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

###postgres configuration

```bash
$sudo -u postgres psql

postgres=# CREATE ROLE vagrant SUPERUSER LOGIN;
postgres=# \q

```
Change the postgresql's configuration to make no need password for local user.change the md5 to trust.

```bash
sudo vim /etc/postgresql/9.2/main/pg_hba.conf
```

change the encoding 

```bash
sudo pg_dropcluster --stop 9.2 main
sudo pg_createcluster --locale=en_US.utf8 --start 9.2 main
```

```bash
sudo service postgresql restart
```

###Samba configuration

add vagrant to samba's user
```bash
pdbedit -a -u vagrant
```
update the configuration file

```bash
vim /ect/samba/smb.conf
```

```bash
 [Work]
     commemt = Work for all
     read only = no
    # public = yes
     writeable = yes
     path = /home/vagrant
     force user = root
```

restart the samba

```bash
sudo restart smbd
sudo restart nmbd
```

## THANKS

[Vagarnt](http://vagrantup.com/)

[Railscast.com](http://railscasts.com/episodes/293-nginx-unicorn)

All of You!
