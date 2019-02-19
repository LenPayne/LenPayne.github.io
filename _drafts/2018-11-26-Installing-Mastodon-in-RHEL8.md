---
title: Installing Mastodon in RHEL 8
layout: post
category: Learning
---
Today I'm exploring the process of install Mastodon on RHEL 8 Beta.

Because I'm a sucker for punishment.

    sudo yum install wget git ruby ruby-devel postgresql-server redis nodejs gcc make autoconf redhat-rpm-config nginx

    sudo yum group install "Development Tools"
      imagemagick ffmpeg \
      libpq-devel libxml2-devel libxslt-devel \
      protobuf-c protobuf \
      libicu-devel \
      bison build-essential libssl-devel libyaml-devel libreadline6-devel \
      zlib1g-dev libncurses5-dev libffi-dev libgdbm5 libgdbm-dev \
      nginx redis-server redis-tools postgresql postgresql-contrib \
      certbot yarn libidn11-dev libicu-dev libjemalloc-dev


wget https://github.com/protocolbuffers/protobuf/releases/download/v3.6.1/protobuf-cpp-3.6.1.tar.gz
tar zxvf protobuf-cpp-3.6.1.tar.gz
cd protobuf-3.6.1
./configure --prefix=/usr
make
sudo make install
sudo ldconfig

    sudo npm install -g yarn

    sudo adduser mastodon
    sudo su - mastodon

    gem install bundler --no-ri --no-rdoc

    exit

    sudo systemctl start postgresql redis
    sudo systemctl enable postgresql redis

    sudo -u postgres postgresql-setup --init
    sudo systemctl restart postgresql

    sudo -u postgres psql

    CREATE USER mastodon CREATEDB;
    \q

    sudo su - mastodon

    git clone https://github.com/tootsuite/mastodon.git live && cd live
    git checkout $(git tag -l | grep -v 'rc[0-9]*$' | sort -V | tail -n 1)

    bundle install \
      -j$(getconf _NPROCESSORS_ONLN) \
      --deployment --without development test
    yarn install --pure-lockfile
