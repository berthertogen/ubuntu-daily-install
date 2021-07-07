# Choose correct NVIDIA driver from Additional drivers screen

# Install curl

sudo apt update && sudo apt upgrade && sudo apt install curl && sudo apt update && sudo apt upgrade

#-----------------------------------------------------------------

# Gnome shell

sudo apt-get install chrome-gnome-shell

#-----------------------------------------------------------------

# Terminator

sudo add-apt-repository ppa:gnome-terminator
sudo apt-get update
sudo apt-get install terminator
sudo rm /etc/apt/sources.list.d/gnome-terminator-ubuntu-ppa-groovy.list 

#-----------------------------------------------------------------

# Dotnet

wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update;   sudo apt-get install -y apt-transport-https &&   sudo apt-get update &&   sudo apt-get install -y dotnet-sdk-5.0

#-----------------------------------------------------------------

# Git

sudo apt install git-all

#-----------------------------------------------------------------

# VSCode

wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders

sudo sh -c "echo 'fs.inotify.max_user_watches=524288' >> /etc/sysctl.conf"
sudo sysctl -p

#-----------------------------------------------------------------

# .npmrc

sudo tee -a ~/.npmrc > /dev/null <<EOT

prefix=/home/bert/.npm-global
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/registry/:username=onsict
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/registry/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/registry/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/:username=onsict
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/_packaging/Zoo-Ons/npm/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/registry/:username=onsict
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/registry/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/registry/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/:username=onsict
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/_packaging/Maatwerk/npm/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/registry/:username=onsict
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/registry/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/registry/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/:username=onsict
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/710209bc-d041-4e20-a48b-ff262e053645/_packaging/shared-components/npm/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/registry/:username=onsict
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/registry/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/registry/:email=npm requires email to be set but doesn't use the value
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/:username=onsict
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/:_password=***MYPAY***
//pkgs.dev.azure.com/onsict/Shared%20Components/_packaging/shared-components/npm/:email=npm requires email to be set but doesn't use the value
always-auth=true

# node -e "require('readline') .createInterface({input:process.stdin,output:process.stdout,historySize:0}) .question('PAT> ',p => { b64=Buffer.from(p.trim()).toString('base64');console.log(b64);process.exit(); })"
# raw token ***MYPAY***

EOT

#-----------------------------------------------------------------

# pass

sudo apt-get install pass
pass init bert@hertogen.net

#-----------------------------------------------------------------

# git credential manager correct

wget "https://github.com/microsoft/Git-Credential-Manager-Core/releases/download/v2.0.394-beta/gcmcore-linux_amd64.2.0.394.50751.deb" -O ~/Downloads/gcmcore-linux.deb
sudo dpkg -i ~/Downloads/gcmcore-linux.deb
git config --global credential.credentialStore gpg
gpg --gen-key
git-credential-manager-core configure

#-----------------------------------------------------------------

# Powershell

# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh

#-----------------------------------------------------------------

# Teams

wget "https://go.microsoft.com/fwlink/p/?LinkID=2112886&clcid=0x409&culture=en-us&country=US" -O ~/Downloads/teams.deb
sudo dpkg -i ~/Downloads/teams.deb
