Screenshots
============================
Capture screenshots of websites

[![npm package](https://nodei.co/npm/screenshots.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/screenshots/)

## Configuring a server

Install nodejs from [nvm](https://github.com/creationix/nvm):

```
sudo apt-get update
sudo apt-get install build-essential libssl-dev
curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh -o install_nvm.sh
bash install_nvm.sh
source ~/.profile
nvm install node
nvm use node
```

Install [Google Chrome](http://help.ubuntu.ru/wiki/google_chrome):

```
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update
sudo apt-get install google-chrome-stable
```

## Installation

`npm install screenshot`

## Usage

You can see example on the `demo.js` file

```
const Screenshot = require('screenshots');

let url = `https://www.google.com.ua/`
new Screenshot()
    .setWait(1000)
    .setFilePath('./tmp')
    .setFileName('image_name')
    .setSizes({'desktop':[1280, 1024], 'tablet':[664, 920], 'mobile':[320, 533]})
    .setResizes({'desktop':[180, 120]}, true)
    .shot(url, (err, images)=>{
        if(err) console.log(err);
        console.log(images);
    });
```