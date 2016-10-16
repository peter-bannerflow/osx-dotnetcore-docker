# osx-dotnetcore-docker
## Install Homebrew
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
## Install OpenSSL
`wget https://www.openssl.org/source/openssl-1.0.2j.tar.gz
tar xzf openssl-1.0.2j.tar
./Configure darwin64-x86_64-cc shared enable-ec_nistp_64_gcc_128 no-ssl2 no-ssl3 no-comp --openssldir=/usr/local/ssl/macos-x86_64
make depend
sudo make install`
## Install Node
`brew install node`
## Install Yeoman, Bower, Grunt, and Gulp
`npm install -g yo bower grunt-cli gulp`
## Install ASP.NET template for Yeoman
`npm install -g generator-aspnet`
