**Commands which you should input after receiving clear server**

```sudo apt update && sudo apt upgrade -y```

```sudo apt install make clang pkg-config libssl-dev libclang-dev build-essential git curl ntp jq llvm tmux htop screen -y```

**Installation Goland 1.18.3**

`wget https://golang.org/dl/go1.18.3.linux-amd64.tar.gz`

`sudo tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz`

```
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GO111MODULE=on
export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin
EOF
source ~/.profile
go version
rm -rf go1.18.3.linux-amd64.tar.gz
