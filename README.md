# Setup
## chezmoi のインストール
- chezmoi のバイナリの配置先のパスを追加する
  - `echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc`
  - `source ~/.bashrc`
- chezmoi を `$HOME/.local/bin` へインストール`  
  - `sh -c "$(curl -fsLS https://get.chezmoi.io)" -- -b $HOME/.local/bin`

## dotfiles リポジトリの設定をマシンに反映
- `chezmoi init https://github.com/byeron/chezmoi-dotfiles.git`

## brew のインストール
```
# homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# after brew install
echo >> /home/magi/.bashrc
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv bash)"' >> /home/magi/.bashrc
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv bash)"
sudo apt install build-essentia
```

## ここで reboot する

brew 実行前に更新された実行パスを反映させる

## brew で管理されているパッケージをインストールする
- `brew bundle`
  - Brewfile を参照し、イントールする
  - `HOMEBREW_BUNDLE_FILE="$HOME/.config/brew/Brewfile"` が .profile に記載されている

## ここで reboot する

brew で導入されたツールとそれに関連するパスの更新を反映させる

## tailscale を導入する
- `curl -fsSL https://tailscale.com/install.sh | sh`
