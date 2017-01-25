### Prezto

[新規の場合はPreztoをインストールから](#Preztoをインストール)

※ [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)から[Prezto](https://github.com/sorin-ionescu/prezto)に移行する

#### zshの設定ファイルを退避

前に書いた設定とかが消えないようにする。cpでも良いです。

```ruby
mv .zlogin .zlogout .zprofile .zshenv .zshrc <zsh_orig_dir>

# 下記でも良いんじゃないですかねぇ
cp .zlogin .zlogout .zprofile .zshenv .zshrc ~/backup
```

#### zsh起動 (デフォルトzshにしてなければ)

```
zsh
```

##### 確認方法

```
echo $SHELL

/bin/zsh
```

#### oh-my-zshをアンインストール

```
uninstall_oh_my_zsh
```

#### Preztoをインストール

```
git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
```

#### 設定ファイルを作成

```Shell
setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
```

#### デフォルトのShellをzshにする(してなければ)

```Shell
chsh -s /bin/zsh
```

#### Preztoの更新

```
cd ~/.zprezto
git pull && git submodule update --init --recursive
```

#### テーマ

##### 使用できるテーマのリストを表示

```
prompt -l
```

##### テーマのプレビュー

```Shell
prompt -p <name>
# 例えば
prompt -p fire
```

##### テーマの変更

```
prompt fire
```

##### テーマの固定

.zpreztorc
```
zstyle ':prezto:module:prompt' theme 'fire'
```

#### gitのフォルダに入った時にブランチを表示させる

```
  zstyle ':prezto:load' pmodule \
  'environment' \
  'terminal' \
  'editor' \
  'history' \
  'directory' \
  'spectrum' \
  'utility' \
  'completion' \
  'git' \ # この行を追加すると、gitリポジトリのフォルダに移動したときに、ブランチ名が表示されるようになる
  'prompt'
```
