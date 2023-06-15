# macbook-utility
Recommendation apps for macOS 2023 (all free!!!)
แนะนำให้ติดตั้ง apps เหล่านี้บนเครื่อง mac M1 and M2

## Table of contents

- [Install Chrome](#install-chrome)
- [Install iTerm2](#install-iterm2)
- [Install Homebrew](#install-homebrew)
- [Install Development Tools](#install-development-tools)
- [Install VSCode extensions](#install-vscode-extensions)
- [Install NODE/NVM](#install-node/nvm)
- [Install Git](#install-git)
- [Install OhMyZsh](#install-ohmyzsh)
- [Install Powerlevel10K](#install-powerlevel10k)
- [Add Plugins](#add-plugin)
- [Setup SSH-Key](#setup-ssh-key)
- [Terminal Shortcut](#terminal-shortcut)
- [Install Terraform](#install-terraform)
- [Install the Azure CLI tool](#install-the-azure-cli-tool)

## Install Chrome

สามารถ download และติดตั้งได้จาก [link](https://www.google.com/chrome/)


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

เมื่อเรามี brew command เราก็สามารถสั่งให้มันติดตั้งโปรแกรมอื่นๆได้โดยที่เราไม่ต้องไป download แล้วนำมาติดตั้งหรือลากไปที่ application แบบ manual 
ทดสอบโดยการติดตั้ง vscode ลงบนเครื่องนี้โดยใช้ homebrew แล้วมันจะนำไปติดตั้งใน application folder ให้อัตโนมัติ
```bash
brew install --cask visual-studio-code
code .
```
ให้ click ok ทั้งหมดเมื่อมีคำถามเรื่อง security บนเครื่องเรา และสามารถติดตั้ง VSCode extensions เช่น AWS codewhisperer

## VSCode extensions

แนะสำให้ติดตั้ง extenstion เหล่านี้ใน VSCode

- vscode-icons เห็น icons 
- Shell format สำหรับ syntax highlight
- YAML สำหรับ derect code error เพราะมันดูยาก
- Makefile tools สำหรับ make 
- Remote – SSH สำหรับ ssh ไปยัง remote server จาก vscode screen
- Live Server สำหรับ view HTML page locally
- Rainbow CSV   ช่วยให้ตัวหนังสือมีสีอ่านง่าย
- Prettier Code Formatter for Visual Studio Code  ช่วยจ้ด code ที่เขียนดูง่าย
- Project Manager

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

## Install Git

เราติดตั้งด้วย brew command

`brew install --cask git`

## Install Oh My Zsh

เราติดตั้งด้วย command

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

## Install PowerLevel10K

จะเป็นการ Install PowerLevel10K Theme สำหรับ Oh My Zsh

`git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`

จากนั้นให้เราเข้าเปิดไฟล์ ~/.zshrc เพื่อระบุ Theme ที่อยากได้ เช่นตัวอย่างนี้ (อยู่ประมาณบรรทัดที่ 22) ให้ copy ค่านี้ไปใส่แทน

`vim ~/.zshrc`

แก้ตรงชื่อ THEME ให้เป็นแบบข้างล่าง

`ZSH_THEME="powerlevel10k/powerlevel10k"`

แก้ไขเสร็จสั่ง save แล้วปิดไฟล์
เพื่อให้มันมันมีผลต่อสิ่งที่เราเปลียนแปลงนี้ ต้อง ปิดเปิด iterm2 ใหม่หรือรันคำสั่งนี้ เพื่อให้มัน reflect

`source ~/.zshrc`

มันจะให้เรา configure powerlevel10k ดังนั้นเราต้องเลือก configuration option ที่ต้องการ ถ้าไม่ทราบให้ทำตามนี้ไปก่อน (เราสามารถกลับมา configure ใหม่ได้ `p10k configure`)

Configuration Menu

- Install Meslo Nerd Font?  --> choice [ynq]: y เพื่อไป download font มาให้
ให้เราปิด iterm2 เพื่อใช้งาน font นี้ (กด command + Q ) ที่ keyboard หรือใช้ mouse สั่ง quit จาก dock area (tasks bar) ด้านล่าง 
- แนะนำให้ใช้ Font นี้กับ VSCode ด้วย ทำได้โดยการแก้ไขไฟล์ settings.json ใน vscode folder (Users>[yourname]>Library> Applicaiton Support> Code > User > settings.json

บรรทัดที่ 3

```vscode
{
    "files.autoSave": "onFocusChange",
    "terminal.integrated.fontSize": 16,
    "terminal.integrated.fontFamily": "MesloLGS NF",
```
กลับมาที่หน้า p10 configure
- Does this look like a diamond (rotated square)? --> choice [ynq]: y 
- Does this look like a lock? --> choice [ynrq]: y 
- Do all these iconds fit between the crosses? --> choice [ynrq]: y
- Prompt style --> choice [1234rq]: 3 (Rainbow)
- Character Set --> choice [12rq]: 1 (Unicode)
- Show current time?  --> choice [n12rq]: 1 (12-hour format)
- Prompt Separators --> choice [1234rq]: 1 (Angled)
- Prompt Heads --> choice [1234rq]: 1 (Sharp)
- Prompt Tails --> choice [1234rq]: 1 (Flat)
- Prompt Height --> choice [12rq]: 2 (Two lines)
- Prompt Connection --> choice [123rq]: 2 (Dotted)
- Prompt Frame --> choice [1234rq]: 4 (Full)
- Connection & Frame Color --> choice [1234rq]: 1 (Lightest)
- Prompt Spacing --> choice [12rq]: 1 (Compact)
- Icons --> choice [12rq]: 2 (Many icons)
- Prompt Flow --> choice [12rq]: 1 (Concise)
- Enable Transient Prompt? --> choice [ynrq]: n
- Instant Prompt Mode --> choice [123rq]: 1 (recommended)
- Powerlevel10k config file already exists. Overwrite ~/.p10k.azh?   --> choice [yrq]: y

เสร็จแล้วจะเห็นว่า prompt เปลียนไปตามที่เรา configure ไว้ (แนะนำให้ไปเปลี่ยนที่ Text iTerm2 ของ Mac ด้วย ไปที่ User Profile, Text แทป Font size 16-20 พอ)

## เปลี่ยน  iTerm2 Colors to Custom Theme
1. Open iTerm2
2. Download my color profile by running the following command (will be added to Downloads folder):
   
`curl https://raw.githubusercontent.com/josean-dev/dev-environment-files/main/coolnight.itermcolors --output ~/Downloads/coolnight.itermcolors`

4. Open iTerm2 preferences
5. Go to Profiles > Colors
6. Import the downloaded color profile (coolnight)
7. Select the color profile (coolnight)

สามารถหา themes อื่นได้ที่ [Iterm2 Color Schemes](https://iterm2colorschemes.com/) สามารถ download แล้ามา add เพิ่ม
เวลาที่เปิด iterm2 จะเห็นว่ามันมืดนิดๆ (night)


## Add Plugin

`vim ~/.zshrc`

อยู่ประมาณบรรทัดที่ 80

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

ส่ัง reload ไฟล์นี้เพื่อให้มีผล (syntax highlight ทำให้คำส่ังมีสี, web-search ส่ังเปิด webbrowser เช่นพิมพ์ว่า `google zsh` มันจะค้นหาใน chrome ให้เรา

`source ~/.zshrc`

ถ้าเราพิมพ์ git มันจะมี auto suggestion มาให้เพื่อประหยัดเวลาพิมพ์ ถ้าต้องการกด arrow up 🔼ถ้าไมเอา กด arrow down 🔽 บนคีย์บอร์ด


## Setup SSH-Key

ใช้ ssh-key มีประโยชน์ เพื่อช่วยให้ไม่ต้อง login เช่น Linux server, Windows server, GitHub ทำให้เราสามารถ clone หรือ uplode file ไปที่ remote repository โดยไม่ต้อง provide credentails (username และ password) เราต้องไป ที่ SSH Keys
```bash
# Generate new SSH Key
ssh-keygen -t rsa -b 4096 -C "EMAIL"

# Start ssh agent
eval "$(ssh-agent -s)"

# Copy the key to a server (Optional ไม่ต้องทำถ้าไม่มี server ให้ลอง)
ssh-copy-id username@remote_host
หรือ
cat ~/.ssh/id_rsa.pub | ssh username@remote_host "mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys \
&& chmod -R go= ~/.ssh && cat >> ~/.ssh/authorized_keys"


# Add new SSH key to Github or Other Providers (public key)
cat ~/.ssh/id_rsa.pub
pbcopy < ~/.ssh/id_rsa.pub

# Fixing permission keys
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

# Terminal Shortcut
```
You can use Ctrl+U to clear up to the beginning.
You can use Ctrl+W to delete just a word.
You can also use Ctrl+C to cancel.
```

# Install Terraform

ติดตั้งโดยใช้ Homebrew Mac

1. เริ่มด้วยการ install the HashiCorp tap, a repository of all our Homebrew packages

`brew tap hashicorp/tap`

2. Install Terraform ด้วย hashicorp/tap/terraform

`brew install hashicorp/tap/terraform`

3. ให้ update to the latest version of Terraform, first update Homebrew

`brew update`

4. รันคำสั่งข้างล่างเพื่อ upgrade เป็น latest Terraform version

`brew upgrade hashicorp/tap/terraform`

# Install the Azure CLI tool

```
brew update && brew install azure-cli
az login
az account set --subscription "6ecdc821-xxxx-xxxx-xxxx-xxxxxxxxx"
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<SUBSCRIPTION_ID>"
az account list-locations -o table

mkdir learn-terraform-azure
cd learn-terraform-azure

```

สร้างไฟล์ main.tf แล้ว copy ข้อมูลข้างล่างมาใส่ในไฟล์นี้

```
# Configure the Azure provider
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 3.0.2"
    }
  }

  required_version = ">= 1.1.0"
}

provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "rg" {
  name     = "myTFResourceGroup"
  location = "southeastasia"
}
```

### Initialize your Terraform configuration
```
terraform init
terraform fmt
terraform validate
```
### Apply your Terraform Configuration
```
terraform apply
terraform show
terraform state list
terraform state
```
You're Done!
😙 👏
