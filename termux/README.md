# Termux安裝與設定
## 一、下載
#### 至 Google Play 下載 [Termux](https://play.google.com/store/apps/details?id=com.termux)

## 二、安裝套件

### 1. 更新套件管理器
#### 執行：pkg update&&upgrade

### 2. 安裝常用套件
#### 安裝模擬root：pkg install proot
#### 安裝 git
```shell
pkg install git #安裝 git
pkg install wget #安裝 wget
pkg install make #安裝 make
pkg install python #安裝 python
pip install --upgrade pip #更新 pip
pkg install nodejs #安裝 nodejs
npm install npm -g #更新 npm
```

## 三、更改介面風格

### 1. 安裝 termux-ohmyzsh
#### 執行：sh -c "$(curl -fsSL https://github.com/Cabbagec/termux-ohmyzsh/raw/master/install.sh)"

在 termux-ohmyzsh 安裝完後即可選擇色彩風格與字體，若往後要更改時可執行：
`~/.termux/colors.sh`