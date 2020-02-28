# SpaceVim 安裝筆記(以 typescript 環境為例)
## 一. Windows Subsystem for Linux
更新套件管理庫
```bash
sudo apt update&&upgrade
```
安裝 python 與 nodejs
```bash
sudo apt install python
sudo apt install python-pip
sudo apt install python3
sudo apt install python3-pip
sudo apt install nodejs
```
更新 nodejs
```bash
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```
更新 npm
```bash
sudo npm i -g npm
```
安裝 neovim
```bash
sudo apt install neovim
```
更新 neovim
```bash
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:neovim-ppa/unstable
sudo apt update
sudo apt install -y neovim
```
安裝 SpaceVim
```bash
curl -sLf https://spacevim.org/install.sh | bash
```
當安裝完成後執行
```bash
nvim # 第一次執行會選擇風格，可選2比較潮
nvim # 第二次執行會自動安裝插件
nvim # 第三次正式開始
```
此外，為使插件安裝後能順利執行，還需用 pip 與 npm 安裝 neovim
```bash
pip install neovim
pip3 install neovim
sudo npm i -g neovim
```
若出現部分字體無法顯示的問題，可由安裝 nerd font 字體解決(在此提供 [Sauce Code Pro Nerd Font](https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/SourceCodePro/Regular/complete/Sauce%20Code%20Pro%20Nerd%20Font%20Complete.ttf))，安裝完後將終端機的字體設定為"SauceCodePro Nerd Font"即可顯示完整字體。
## 二. Termux
#### 詳見 https://github.com/CSP-GD/notes/blob/master/termux/README.md