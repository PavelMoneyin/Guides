**1. Update you server**

``sudo apt update && sudo apt upgrade -y``

``sudo apt install make clang pkg-config libssl-dev libclang-dev build-essential git curl ntp jq llvm tmux htop screen``

**2.Install Git LFS**

``sudo apt-get install software-properties-common``

``sudo curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash``

``sudo apt-get install git-lfs``

``git lfs install``

**3.Download Binary with Git LFS**

``git lfs clone https://github.com/bnb-chain/node-binary.git``
