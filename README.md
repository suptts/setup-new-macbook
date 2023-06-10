# macbook-utility
Recommendation apps for macOS 2023 (all free!!!)
แนะนำให้ติดตั้ง apps เหล่านี้บนเครื่อง mac M1 and M2

## Table of contents

- [Install Chrome](#install-chrome)
- [Install Homebrew](#install-homebrew)
- [Install iTerm2](#install-iterm2)
- [Install Git](#install-git)
- [Install OhMyZsh](#install-ohmyzsh)
- [Install Powerlevel10K](#install-powerlevel10k)
- [Install Development Tools](#install-development-tools)
- [Install VSCode extensions](#install-vscode-extensions)
- [Install NODE/NVM](#install-node/nvm)
- [Setup SSH-Key](#setup-ssh-key)


## Install Chrome

สามารถ download และติดตั้งได้จาก link นี้

## Install Homebrew

Homebew เป็น software package manager สำหรับ Mac มันจะช่วยในการติดตั้งโปรแกรมต่างๆ ลงในเครื่อง mac เราผ่าน commandline ที่ terminal
ติดตั้งโดยการรัน command line และเราต้องใส่ password ของเครื่องเพราะมันต้องการสิทธิ์ aministrator เพื่อ install

```bash
export HOMEBREW_NO_INSTALL_FROM_API=1
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## Install Development Tools

เมื่อเรา install homebrew เสร็จ เราจะต้องรัน commands เพิ่มเติมอีก 2 คำสั่งเพื่อ add ไปที่ PATH เพื่อให้เรียกใช้งานได้ คำสั่งแรกมันจะสร้างไฟล์ไหม่ขีึ้นมาให้ชื่อ
.zprofile เราสามารถใช้ nano หรือ vi เข้าไปอ่าน file content ส่วนคำสั่งที่ 2 เป็นการ register homebrew ไปที่ shell เราก็เรียกใช้งาน brew command ได้แล้วเช่น `brew --version` เป็นต้น

```bash
# Run คำสั่งเหล่านี้หลังการติตตั้ง Homebrew ให้ copy จากเครื่องตัวเอง เพราะ user จะไม่เหมือนกัน
# Run these two commands in your terminal to add Homebrew to your PATH:
    (echo; echo 'eval "$(/usr/local/bin/brew shellenv)"') >> /Users/supiwmi/.zprofile
    eval "$(/usr/local/bin/brew shellenv)"
 
 # ตรวจสอบโดยการเช็ค version
 brew --version
```
## Install iTerm2

เราติดตั้งด้วย brew command

`brew install --cask iterm2`

เมือติดตั้งแล้วให้เราเปลี่ยนมาใช้ iterm2 แทน 

## Install Git

เราติดตั้งด้วย brew command

`brew install --cask git`

## Install Oh My Zsh

เราติดตั้งด้วย command

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

## Install PowerLevel10K

จะเป็นการ Install PowerLevel10K Theme สำหรับ Oh My Zsh

`git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`

จากนั้นให้เราเข้าเปิดไฟล์ ~/.zshrc เพื่อระบุ Theme ที่อยากได้ เช่นตัวอย่างนี้

`ZSH_THEME="powerlevel10k/powerlevel10k"`

เพื่อให้มันมันมีผลต่อสิ่งที่เราเปลียนแปลงนี้ ต้อง ปิดเปิด iterm2 ใหม่หรือรันคำสั่งนี้ เพื่อให้มัน reflect

`source ~/.zshrc`

เมื่อเรามี brew command เราก็สามารถสั่งให้มันติดตั้งโปรแกรมอื่นๆได้โดยที่เราไม่ต้องไป download แล้วนำมาติดตั้งหรือลากไปที่ application แบบ manual 
ทดสอบโดยการติดตั้ง vscode ลงบนเครื่องนี้โดยใช้ homebrew แล้วมันจะนำไปติดตั้งใน application folder ให้อัตโนมัติ
```bash
brew install --cask visual-studio-code
code .
```
ให้ click ok ทั้งหมดเมื่อมีคำถามเรื่อง security บนเครื่องเรา และสามารถติดตั้ง VSCode extensions เช่น AWS codewhisperer

## VSCode extensions

แนะสำให้ติดตั้ง extenstion เหล่านี้ใน VSCode

- Python
- Git
- Lint
- Light server  สำหรับ view HTML page locally
- Rainbow CSV   ช่วยให้ตัวหนังสือมีสีอ่านง่าย
- Prettier Code Formatter for Visual Studio Code  ช่วยจ้ด code ที่เขียนดูง่าย

เมื่อเราเปิดโปรแกรมแล้วต้องการให้มัน pins ไว้ที่ tasks bard ด้านล้างให้ drange & drop icon program ที่ต้องการมาที่ pernanent area

## NODE and NVM

เราจะติดตั้ง nvm เพื่อช่วยให้เราสามารถติดตั้ง node ได้หลายๆ version บนเครื่องเราและสั่ง switch ไปมาระหว่าง version ที่ต้องการได้ง่ายๆ
ติดตั้ง nvm โดยการรันคำสั่งข้างล่างนี้ก่อน
เราจะใช้ node เมื่อมีการพัตนา app ด้วย programming language สำหรับ cross-platform tools เช่น NativeScript, ReacNative, Ionic เป็นต้น
`curl `

จะสั่งเกตุว่าเมื่อติดตั้ง nvm แล้ว มันจะแก้ไขไฟล์ .zprofile โดยการเพิ่ม 
เราดูข้อมูลได้ด้วย vim หรือ vscode 

`vim ~/.zprofile`

หรือ

`code ~/.zprofile`

เพื่อทดสอบว่า nvm ติดตั้งแล้วใช้งานได้เราต้องปิดแล้วเปิด terminal ขึ้นมาใหม่ก่อน
จากนั้นให้ทำการติดตั้ง node ด้วย nvm command

```bash
nvm install 18
nvm install 16
node --version
nvm use 18
npm install yarn -g
yarn --version
```
หมายเหตุ macos จะมาพร้อมกับ python version 3.9 เราไม่ต้องติดตั้งแต่เราอาจต้องการ version ใหม่กว่า เช่น 3.10 เราต้องติดตั้งเองเช่นใช้ homebrew

## SSH Key

ใช้ ssh-key มีประโยชน์ เพื่อช่วยให้ไม่ต้อง login เช่น Linux server, Windows server, GitHub ทำให้เราสามารถ clone หรือ uplode file ไปที่ remote repository โดยไม่ต้อง provide credentails (username และ password) เราต้องไป ที่ SSH Keys
```bash
# Generate new SSH Key
ssh-keygen -t rsa -b 4096 -C "EMAIL"

# Start ssh agent
eval "$(ssh-agent -s)"

# Mac OS 
ssh-add -K ~/.ssh/id_rsa

# Copy the key to a server
ssh-copy-id username@remote_host
หรือ
cat ~/.ssh/id_rsa.pub | ssh username@remote_host "mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys \
&& chmod -R go= ~/.ssh && cat >> ~/.ssh/authorized_keys"


# Add new SSH key to Github or Other Providers (public key)
cat ~/.ssh.id_rsa.pub
pbcopy < ~/.ssh/id_rsa.pub

# Fixing permission keys
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```
You're Done!
:smi:
