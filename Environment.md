### Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Git
```
brew install git
git config --global user.name "yuyang041060120"
git config --global user.email "yuyang041060120@gmail.com"
git config --global core.editor "vim"
```

### Zsh
```
apt install zsh
```

### Oh My Zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Oh My Zsh Plugins

#### zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

#### zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Shadowsocks
install pip3
```
sudo apt install python3-pip
```
install shadowsocks and config
```
pip3 install https://github.com/shadowsocks/shadowsocks/archive/master.zip
```
> solve pipe3 error
```
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
sudo dpkg-reconfigure locales
```
```
mkdir /etc/shadowsocks
vim /etc/shadowsocks/config.json
```
config.json
```
{
  "server":"::",
  "server_port":8388,
  "local_address": "127.0.0.1",
  "local_port":1080,
  "password":"mypassword",
  "timeout":300,
  "method":"aes-256-cfb",
  "fast_open": false
}
```
start
```
ssserver -c /etc/shadowsocks/config.json -d start
```
Systemd Shadowsocks
```
vim /etc/systemd/system/shadowsocks-server.service
```
config 
```
[Unit]
Description=Shadowsocks Server
After=network.target

[Service]
ExecStart=/usr/local/bin/ssserver -c /etc/shadowsocks/config.json
Restart=on-abort

[Install]
WantedBy=multi-user.target
```
start
```
systemctl start shadowsocks-server
systemctl enable shadowsocks-server
```

### Nvm
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.7/install.sh | bash
```

### Nginx
```
brew install nginx
vim /usr/local/etc/nginx/nginx.conf
sudo nginx
sudo nginx -s stop
```

### Others
- [GIPHT CAPTURE](https://itunes.apple.com/us/app/giphy-capture.-the-gif-maker/id668208984?mt=12)
- [CheatSheet](https://www.mediaatelier.com/CheatSheet/)
- [Alfred](https://www.alfredapp.com/)
- [Gas Mask](https://github.com/2ndalpha/gasmask)
