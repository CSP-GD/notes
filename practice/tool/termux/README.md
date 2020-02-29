# [目錄](../../../) >> [實務篇](../../) >> [工具](../) >> Termux
> Termux 是一款在 Android 上的模擬終端機

---

# Termux安裝與設定
## 一、下載
#### 至 Google Play 下載 [Termux](https://play.google.com/store/apps/details?id=com.termux)

---

## 二、安裝套件

### 1. 更新套件管理器
```bash
pkg update&&upgrade
```

### 2. 安裝常用套件
```bash
pkg install proot # 模擬 root
pkg install git # 安裝 git
pkg install wget # 安裝 wget
pkg install make # 安裝 make
pkg install python # 安裝 python
pip install --upgrade pip # 更新 pip
pkg install nodejs # 安裝 nodejs
npm install npm -g # 更新 npm
```

---

## 三、更改介面風格

### 1. 安裝 termux-ohmyzsh
```bash
sh -c "$(curl -fsSL https://github.com/Cabbagec/termux-ohmyzsh/raw/master/install.sh)"
```

在 termux-ohmyzsh 安裝完後即可選擇色彩風格與字體，若往後要更改時可執行：
```bash
~/.termux/colors.sh # 更改顏色
~/.termux/fonts.sh # 更改字體
```

### 2. 安裝字體
將選定的字體放到資料夾中
```bash
cd ~/.termux/fonts/
mkdir {font_dir} # font_dir 為自訂的名稱，用來存放新增的字體
cd {font_dir}
wget 字體連結
```
然後執行
```bash
~/.termux/fonts.sh
```
就會出現剛剛新增的字體
 
#### 以 Sauce Code Pro Nerd Font 為例
```bash=
cd ~/.termux/fonts/
mkdir SauceCodeProNerdFont
cd SauceCodeProNerdFont
wget https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/SourceCodePro/Regular/complete/Sauce%20Code%20Pro%20Nerd%20Font%20Complete.ttf
~/.termux/fonts.sh
```

---

## 四、SpaceVim安裝配置

### 1. 安裝 neovim
```bash
pkg install neovim
```

### 2. 安裝 SpaceVim
```bash
curl -sLf https://spacevim.org/install.sh | bash
```
當安裝完成後執行
```bash
termux-chroot # 進入模擬 root 的狀態
nvim # 第一次執行會選擇風格，可選2比較潮
nvim # 第二次執行會自動安裝插件
nvim # 第三次正式開始
```
此外，為使插件安裝後能順利執行，還需用 pip 與 npm 安裝 neovim
```bash
pip install neovim
npm i -g neovim
```
### 3. 設定 SpaceVim
執行`nvim`進入 SpaceVim

依序按下<kbd>SPC</kbd> <kbd>f</kbd> <kbd>v</kbd> <kbd>d</kbd>開啟 SpaceVim 設定檔( ~/.SpaceVim.d/init.toml)
```toml
[options] # 於 options 加入以下的設定
    # 使用 deoplete 作為自動補全引擎
    autocomplete_method = "deoplete"
    # 使用 ale 作為程式碼檢測工具
    enable_neomake = false
    enable_ale = true
    
[[layers]] # 增加格式化模組
    name = "format"
```

### 4. 特定語言支持

#### typescript
```toml
[[layers]]
    name = "lang#typescript"
```
另外需安裝 typescript
```bash
npm i -g typescript
```

#### javascript
```toml
[[layers]]
    name = "lang#typescript"
```
另外可安裝 eslint-cli 與 js-beautify 完成語法檢查與代碼格式化
```bash
npm i -g eslint-cli
npm i -g js-beautify
```