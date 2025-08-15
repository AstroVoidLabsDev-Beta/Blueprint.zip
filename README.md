# Blueprint + Pterodactyl Panel

> One-command setup for a Pterodactyl working directory with Node.js 20, Yarn, utilities, and the latest Blueprint Framework release.

![Banner](banner.png)

## What this does
- Installs base packages, Node.js 20 (NodeSource), and Yarn  
- Preps `/var/www/pterodactyl` and runs `yarn` when `package.json` is present  
- Downloads the latest **Blueprint Framework** release and unpacks it  
- Touches `.blueprintrc`, makes `blueprint.sh` executable, and runs it  
- Safe re-runs: idempotent steps and clear logging

## Quick start
```1) sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | tee /etc/apt/sources.list.d/nodesource.list
apt-get update
apt-get install -y nodejs

``` 2) npm i -g yarn

``` 3) cd /var/www/pterodactyl
yarn

## Download the latest release
```wget "$(curl -s https://api.github.com/repos/BlueprintFramework/framework/releases/latest | grep 'browser_download_url' | cut -d '"' -f 4)" -O release.zip

## Extract release
Unarchive the release you downloaded in the previous step in your Pterodactyl folder.
``` mv release.zip /var/www/pterodactyl/release.zip
cd /var/www/pterodactyl
unzip release.zip

## Configuration
This step allows Blueprint to function and know where itself and Pterodactyl are located and which permissions to use. Create a file called .blueprintrc inside of your Pterodactyl directory to begin.
``` touch /var/www/pterodactyl/.blueprintrc  

# Run the installer (requires sudo/root)
chmod +x installer.sh
sudo ./installer.sh
