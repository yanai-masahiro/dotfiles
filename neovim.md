# neovim

[公式サイト](https://neovim.io/)

[neovim/neovim](https://github.com/neovim/neovim)

## install

[Installing Neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)

```
brew install neovim/neovim/neovim
brew install python3
pip3 install neovim
```

## setting

.zshrcに下記を追加して、設定ファイルのHOME_PATHを設定
```
export XDG_CONFIG_HOME="$HOME/.config"
```

## neovimにおけるvimrcを設定する

### nvim 設定ファイルパス

~/.config/nvim/init.vim

### プラグインマネージャ

[dein.vim](https://github.com/Shougo/dein.vim)

### ファイルタイプごとに設定を変えたい場合の設定

~/.config/nvim/ftplugin/go.vim
