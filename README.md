# osx-dotnetcore-docker
## Install .NET Core 
Installer can be found here http://dot.net 

## Install Docker engine
Installer can be found here http://www.docker.com/products/docker

## Install OpenSSL
OS X "El Capitan" (10.11) comes with 0.9.8 version of OpenSSL. .NET Core depends on versions >= 1.0.1 of OpenSSL. You can update the version by using Homebrew, MacPorts or manually. The important bit is that you need to have the required OpenSSL version on the path when you work with .NET Core. Below are the steps to do this manually since I couldn't get it to work with Homebrew.
```
curl -O https://www.openssl.org/source/openssl-1.0.2j.tar.gz
tar xzf openssl-1.0.2j.tar
./Configure darwin64-x86_64-cc shared enable-ec_nistp_64_gcc_128 no-ssl2 no-ssl3 no-comp --openssldir=/usr/local/ssl/macos-x86_64
make depend
sudo make install
udo ln -s /usr/local/ssl/macos-x86_64/bin/openssl /usr/local/bin/openssl
sudo ln -s /usr/local/ssl/macos-x86_64/lib/libssl.1.0.0.dylib /usr/local/lib/libssl.1.0.0.dylib
sudo ln -s /usr/local/ssl/macos-x86_64/lib/libcrypto.1.0.0.dylib /usr/local/lib/libcrypto.1.0.0.dylib
```
## Install Node
If you don't already have Node installed, this needs to be done. Installer can be found here https://nodejs.org/en/download/
## Install Yeoman, Bower, Grunt, and Gulp
You'll also need to install a number of command line tools that support ASP.NET core development. The command line templates use Yeoman, Bower, Grunt, and Gulp. You may already have many of these tools, but if not, the following step installs them all.
```
npm install -g yo bower grunt-cli gulp
```
## Install ASP.NET template for Yeoman
Once you've installed the core tools, you need to install the yeoman ASP.NET template generators.
```
npm install -g generator-aspnet
```
## Build the Docker container
The Dockerfile created by the ASP.NET template can be built be the following step.
```
docker build -t weather-service .
```
## Run the container
```
docker run -d -p 8080:5000 --name weather-service
```
