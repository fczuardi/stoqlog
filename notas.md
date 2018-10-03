# October 3
- openssl custom recompile
  - SSL v3
    - http://vaughanhilts.me/blog/2017/02/06/openssl-with-sslv3-on-arch-linux-for-dot-net-core.html
    - install `customizepkg-git` from AUR
    - edit `/etc/customizepkg.d/openssl`
    - edit `/etc/customizepkg.d/openssl-1.0`
    - add the following lines:
```
replace#global#no-ssl3-method#zlib
replace#global#no-ssl3#zlib
```
    - run `yaourt -S openssl` and if the pgp signature fails...
    - `gpg --recv-keys D9C4D26D0E604491`
- Jenkins
  - signup
  - request accesss to private repos


# October 2

- Gerrit (pull requests + code review)
  - https://gerrit.async.com.br
  - Private repos
    - signup SSO (Google)
    - ask to be added on chat
  - test with ssh
    - `ssh gerrit.async.com.br -p 294i8`
  - https://wiki.stoq.com.br/index.php/Getting_started
  - https://www.mediawiki.org/wiki/Gerrit/Tutorial#Installing_git-review

- Wiki
  - https://wiki.stoq.com.br/
  - request user on chat

---

- Fetch all repos
  - https://wiki.stoq.com.br/index.php/Repo_instructions
  - install repo
  - remove previous .repo
  - `repo init -u ssh://gerrit.async.com.br:29418/stoq-manifest-private` 
  - `repo sync`
  - `repo forall -c git submodule init`
  - `repo forall -c git submodule update`

- Jenkins
  - signup, request via chat

- Env vars
  - source stoq/utils/env.sh
    - (bash)

---

- stoq
  - Dependencies
    - swig
    - webkitgtk
      -  https://github.com/archlinuxcn/repo/blob/master/README.md
    - storm fork
      - https://launchpad.net/~stoq-maintainers/+archive/ubuntu/unstable/+sourcefiles/storm/0.20.0.100-2~py3-1xenial/storm_0.20.0.100-2~py3-1xenial.tar.gz
      - `tar -xvf storm_0.20.0.100-2~py3-1xenial.tar.gz`
      - `cd storm-0.20.0.99`
      - `ls`
      - `python setup.py install`
  - Virtualenv
    - `python3 -m venv stoqenv --system-site-packages`
    - `source stoqenv/bin/activate`
    - `pip install -r requirements.txt` 
    - `stoq`

- postgresql
  - https://wiki.archlinux.org/index.php/PostgreSQL
  - `sudo -u postgres -i`
  - `initdb --locale en_US.UTF-8 -E UTF8 -D '/var/lib/postgres/data'`
  - `sudo systemctl start postgresql`
  - `sudo -u postgres createuser fcz -ds`

- stoqdbadmin
  - Dependencies
    - pip install future
    - postgres
  - `stoqdbadmin init --help`
  - `stoqdbadmin init -ev`
  - `stoqdbadmin enale_plugin ntk`

- stoq-server
  - locale pt_BR
    - uncomment line on /etc/locale.gen and then run locale-gen
  - SSL v3
    - http://vaughanhilts.me/blog/2017/02/06/openssl-with-sslv3-on-arch-linux-for-dot-net-core.html
    - install `customizepkg-git` from AUR
    - edit `/etc/customizepkg.d/openssl`
    - add the following lines:
```
replace#global#no-ssl3-method#zlib
replace#global#no-ssl3#zlib
```
    - run `yaourt -S openssl` and if the pgp signature fails...
    - `gpg --recv-keys D9C4D26D0E604491`

# October 1


