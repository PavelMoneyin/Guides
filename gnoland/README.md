In this article we will look at how to set up a node and complete the first task, which may be rewarding.

*Well, we’re excited to tell you that there is an ongoing task available on GNO.LAND for anyone to try out. The tricky part is that you have to participate using the CLI. We’ve created this guide for adventurous Gnomes who are willing to challenge themselves to complete the task for **potential rewards.***

**1. requirements**

There are no official requirements. Launched on: 
- 2vCPU
- 2 GB RAM 
- GB SSD — 40
- I recommend [Hetzner](https://hetzner.cloud/?ref=NY9VHC3PPsL0)
- I recommend the SSH terminal for convenience - [MobaxTerm](https://mobaxterm.mobatek.net/download.html)

**2. Server preparation**
```
sudo apt update && sudo apt upgrade -y
```
```
sudo apt install make clang pkg-config libssl-dev libclang-dev build-essential git curl ntp jq llvm tmux htop screen -y
```
```
wget https://golang.org/dl/go1.18.3.linux-amd64.tar.gz
```
```
sudo tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz
```
```
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GO111MODULE=on
export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin
EOF
source ~/.profile
go version
rm -rf go1.18.3.linux-amd64.tar.gz
```
**3. Installing a node**
```
git clone https://github.com/gnolang/gno/
```
```
cd gno
```
```
make
```
```
./build/gnokey generate
```
Command will give you the mnemonic. Save it to a safe place.
```
./build/gnokey add account --recover
```
- Create your password. 
- Repeat your password.
- Enter your mnemonic.
```
./build/gnokey list
```
Copy your address that starts with "g1qpyg1qpy5..." and save it somewhere easily accessible.
```
./build/gnokey query auth/accounts/address --remote gno.land:36657
```
Replace **address** with your address.

**4. Registering our account.**

We need a minimum of 2,200 tokens to start with. 2,000 tokens will go to registration, 100 tokens to confirm the transaction. The other 100 will be left to cover future commissions. Please don't milk the faucet unnecessarily. There will be no privileges for a billion tokens.

Run the script, which will allow us to milk a minimum of 2200 tokens. If the script does not work, you can try [this faucet](https://gno.land/faucet). If this faucet doesn't work either, it's probably empty and you should go straight to [Discord](https://discord.gg/DDC6akkQnT).
```
while true; do curl 'https://gno.land:5050/' --data-raw 'toaddr=address'; ./build/gnokey query "bank/balances/address" --remote gno.land:36657; sleep 2; done
```
- Replace **address** with your address
- Once you have collected 2200 tokens, press **CTRL+C**.

**5. Registering our account**

Create a file that will contain our registration information
```
./build/gnokey maketx call ADDRESS --pkgpath "gno.land/r/users" --func "Register" --gas-fee 1gnot --gas-wanted 3000000 --send "2000gnot" --args "" --args "USERNAME" --args "" > unsigned.tx
```
- Replace **ADDRESS** and **USERNAME** with your own values. 
- **USERNAME** can only contain small letters and must be 6~17 characters.

**Creating a transaction**
```
./build/gnokey sign ADDRESS --txpath unsigned.tx --chainid testchain --number ACCOUNTNUMBER --sequence SEQUENCENUMBER > signed.tx
```
- Replace **ADDRESS** , **ACCOUNTNUMBER** and **SEQUENCENUMBER** with your values.

Conducting the transaction
```
./build/gnokey broadcast signed.tx --remote gno.land:36657
```
Check our username against the [link](https://gno.land/r/users). If it's there, it's done.

**6. Performing the task**

To complete the task, you need to write a post about the Gno.Land project and run it through our terminal. This can be done with the following command.
```
./build/gnokey maketx call ADDRESS --pkgpath "gno.land/r/boards" --func "CreateReply" --gas-fee 1gnot --gas-wanted 3000000 --send "" --broadcast true --chainid testchain --args "1" --args "8" --args "8" --args "URL" --remote gno.land:36657
```
- Replace **address** and **URL** with your values.

Your work should appear on the [website](https://gno.land/r/boards:gnolang/8).
- [Hetzner - server rental](https://hetzner.cloud/?ref=NY9VHC3PPsL0)
- [SSH terminal MobaxTerm](https://mobaxterm.mobatek.net/download.html)
- [Discord](https://discord.gg/DDC6akkQnT)
- [Website](https://gno.land/)
- [Github](https://github.com/gnolang/gno)
- [Official guide](https://medium.com/@onbloc/a-beginners-guide-to-the-gnoland-testnet-6fdc693a48f4)
- [Blog post about first task](https://medium.com/@onbloc/a-guide-to-your-first-task-on-gnoland-8533dcdb71f6)
- [Gno Faucet](https://gno.land/faucet)
- [Gno User Register](https://gno.land/r/users)
- [Gno Taskboard](https://gno.land/r/boards:gnolang/8)

*Pavel-LV | C.Sailors#7698 / @SeaInvestor*







