Creating a build environment Arch Linux
-------------------------------------
Switch to nano
```shel
git config --global core.editor /usr/bin/nano
```
Update and Upgrade
```shell
sudo pacman -Syyu && sudo pacman -Syu base-devel git gnupg gperf ccache lzip zlib curl python3 python-pip unzip openjdk11-jdk wget flex bison make clang lld llvm ncurses ninja libxml2 libxslt libxcrypt-compat repo perl dtc bc python-yaml
mkdir -p ~/.bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
chmod a+x ~/.bin/repo
export PATH=~/.bin:$PATH
echo 'export PATH=~/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
```
Install git
```shell
sudo pacman -S git 
```
Commit-msg id
```shell
curl -Lo .git/hooks/commit-msg https://review.lineageos.org/tools/hooks/commit-msg && chmod u+x .git/hooks/commit-msg
```
Install repo
```shell
wget -q https://storage.googleapis.com/git-repo-downloads/repo
chmod a+x repo
sudo install repo /usr/local/bin/repo
rm repo
```
Generate ssh keys
```shell
ssh-keygen -t ed25519 -C "mezaquegit@gmail.com"
```
Show ssh keys
```shell
cat ~/.ssh/id_ed25519.pub
```
Setup zsh terminal
```shell
curl -o .zsh_history https://raw.githubusercontent.com/guckesh/guckesh/refs/heads/master/profile/.zsh_history
sudo pacman -S zsh -y
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
```shell
sudo nano /etc/passwd
```
Install adb and fastboot
```shell
sudo pacman -S adb fastboot
```
Install packages required for compiling ROMs
```shell
git clone --depth 1 git@github.com:akhilnarang/scripts scripts && cd scripts && bash setup/arch-manjaro.sh
```
Install python dependencies
```shell
python3 -m pip install --user numpy
```
Setup ccache
```shell
sudo pacman -S ccache -y && export USE_CCACHE=1 && export CCACHE_DIR=~/.ccache && ccache -M 40G
```
For git lfs related errors (credits to haggertk)
```shell
sudo pacman -S git-lfs
git lfs install
```
Config git
```shell
git config --global user.email "mezaquegit@gmail.com"
git config --global user.name "Mezaque Silver"
```
Utilitarios
```shel
mkdir AndroidDumps
cd AndroidDumps
git clone git@github.com:ShivamKumarJha/android_tools
cd android_tools && bash setup.sh
```
```shel
git clone git@github.com:AndroidDumps/dumpyara
cd dumpyara && bash setup.sh
```
```shel
git clone git@github.com:LineageOS/android_tools_extract-utils
```
```shel
curl -o linux-stable.sh https://raw.githubusercontent.com/android-linux-stable/script/master/linux-stable.sh && chmod +x linux-stable.sh && ./linux-stable.sh -m -l
```
Sourceforge upload
```shell
sftp trickbot@frs.sourceforge.net
```
```shell
sudo yay -S python3
sudo yay -S python-pipx
```
```shell
sudo mkdir /mnt/Windows
sudo mount -t ntfs /dev/nvme1n1p3 /mnt/Windows
```
Creating a build environment Ubuntu
-------------------------------------
Update and Upgrade
```shell
sudo apt update -y && sudo apt upgrade -y 
```
Install git
```shell
sudo apt install git-core -y 
```
Setup zsh terminal
```shell
sudo apt install zsh -y
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
passwd
```shell
sudo nano /etc/passwd
```
Install adb and fastboot
```shell
sudo apt install android-tools-adb android-tools-fastboot -y
```
Install packages required for compiling ROMs
```shell
git clone --depth 1 git@github.com:akhilnarang/scripts scripts && cd scripts && setup/android_build_env.sh
```
Install python dependencies
```shell
sudo apt-get install 2to3 dh-python python-is-python3 python3 python3.10 python3-pip apt python3-pylint-common -y
```
Some dependencies
```shell
sudo apt-get install libxml2-dev libglib2.0  build-essential libgtk-3-dev libgtksourceview-4-dev libpeas-dev libjalali-dev libxapp-dev -y
sudo apt install python3-full
sudo apt install python3 python3-pip python3-venv
python3 -m venv path/to/venv
source path/to/venv/bin/activate
```
```shell
curl -o kernel-build.sh https://gist.githubusercontent.com/guckesh/f945625970d7146fd5123bac5a8139ec/raw/aaa22ea530e0eed996fd8fd04747c00abb86138c/kernel-build.sh
```
[![TG chat](https://img.shields.io/badge/Support-Telegram-%23e52c5f.svg?style=for-the-badge&logo=telegram&&labelColor=121217991103595)](https://t.me/guckesh)
