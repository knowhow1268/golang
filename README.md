## install golang on ubuntu using the apt-get

The Go project's official download page is at https://golang.org/dl/.

There are some other options for Debian based systems like Ubuntu. These packages were not created by the Go project, and we don't support them, but they may be useful for you.

Try:

$ sudo apt-get install golang-go
If that's too old for you, try:

$ sudo add-apt-repository ppa:gophers/archive
$ sudo apt update
$ sudo apt-get install golang-1.9-go
Note that golang-1.9-go puts binaries in /usr/lib/go-1.9/bin. If you want them on your PATH, you need to make that change yourself.

Using snaps also works quite well:

# This will give you the latest version of go
$ snap install --classic go
A restart is required for the command to be recognized.

If you're using Ubuntu 16.04 LTS and are unable to install golang-1.9-go, then you can also use the longsleep/golang-backports PPA:

sudo add-apt-repository ppa:longsleep/golang-backports
sudo apt-get update
sudo apt-get install golang-go


## How to Install Go 1.9 on Ubuntu 17.10, 16.04, 14.04 & LinuxMint

Go is an open source programming language developed by a team at Google. It provides easy to build simple, reliable, and efficient software. This language is designed for writing servers, that’s why it is using widely these days. Go has released latest version 1.9. This tutorial will help you to install Go 1.9 on your Ubuntu 16.04 LTS, 14.04 LTS, and 12.04 LTS systems.

Step 1 — Install Go Language
Login to your Ubuntu system using ssh and upgrade to apply latest security updates there.

sudo apt-get update
sudo apt-get -y upgrade
Now download the Go language binary archive file using following link. To find and download latest version available or 32 bit version go to official download page.

wget https://storage.googleapis.com/golang/go1.9.2.linux-amd64.tar.gz
Now extract the downloaded archive and install it to the desired location on the system. For this tutorial, I am installing it under /usr/local directory. You can also put this under the home directory (for shared hosting) or other location.

sudo tar -xvf go1.9.2.linux-amd64.tar.gz
$ sudo mv go /usr/local
Step 2 — Setup Go Environment
Now you need to setup Go language environment variables for your project. Commonly you need to set 3 environment variables as GOROOT, GOPATH and PATH.

GOROOT is the location where Go package is installed on your system.

export GOROOT=/usr/local/go
GOPATH is the location of your work directory. For example my project directory is ~/Projects/Proj1 .

export GOPATH=$HOME/Projects/Proj1
Now set the PATH variable to access go binary system wide.

export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
All above environment will be set for your current session only. To make it permanent add above commands in ~/.profile file.

Step 3 — Verify Installation
At this step, you have successfully installed and configured go language on your system. First, use the following command to check Go version.

go version

go version go1.9.2 linux/amd64
Now also verify all configured environment variables using following command.

go env

GOARCH="amd64"
GOBIN=""
GOEXE=""
GOHOSTARCH="amd64"
GOHOSTOS="linux"
GOOS="linux"
GOPATH="/root/Projects/Proj1"
GORACE=""
GOROOT="/usr/local/go"
GOTOOLDIR="/usr/local/go/pkg/tool/linux_amd64"
GCCGO="gccgo"
CC="gcc"
GOGCCFLAGS="-fPIC -m64 -pthread -fmessage-length=0 -fdebug-prefix-map=/tmp/go-build764105058=/tmp/go-build -gno-record-gcc-switches"
CXX="g++"
CGO_ENABLED="1"
CGO_CFLAGS="-g -O2"
CGO_CPPFLAGS=""
CGO_CXXFLAGS="-g -O2"
CGO_FFLAGS="-g -O2"
CGO_LDFLAGS="-g -O2"
PKG_CONFIG="pkg-config"
