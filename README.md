# Blueprint + Pterodactyl Panel

> One-command setup for a Pterodactyl working directory with Node.js 20, Yarn, utilities, and the latest Blueprint Framework release.

![Banner](https://blueprint.zip/.assets/brand/retro.png)

## What this does
- Installs base packages, Node.js 20 (NodeSource), and Yarn  
- Prepares `/var/www/pterodactyl` and runs `yarn` if `package.json` exists  
- Downloads the latest **Blueprint Framework** release and unpacks it  
- Creates `.blueprintrc`, makes `blueprint.sh` executable, and runs it  
- Safe to re-run — idempotent steps and clear logging

---

## Quick Start Guide

### 1) Install base packages and Node.js 20
```bash
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list
sudo apt-get update
sudo apt-get install -y nodejs
```

### 2) Install Yarn globally
```bash
npm i -g yarn
```

### 3) Prepare the Pterodactyl directory and install dependencies
```bash
cd /var/www/pterodactyl
yarn
```

### 4) Download the latest Blueprint release
```bash
wget "$(curl -s https://api.github.com/repos/BlueprintFramework/framework/releases/latest | grep 'browser_download_url' | cut -d '"' -f 4)" -O release.zip
```

### 5) Extract the release into the Pterodactyl folder
```bash
mv release.zip /var/www/pterodactyl/release.zip
cd /var/www/pterodactyl
unzip release.zip
```

### 6) Create the `.blueprintrc` configuration file
```bash
touch /var/www/pterodactyl/.blueprintrc
```

### 7) Run the installer (requires sudo/root)
```bash
chmod +x installer.sh
sudo ./installer.sh
```

---

## Notes
- Ensure you run all commands as **root** or with **sudo**  
- If `blueprint.sh` is included in the release, it will be executed automatically  
- Make sure `/var/www/pterodactyl` exists before starting  

---

## Credits
Maintained by **[ITZ_YTANSH / AstroVoidLabsDev]**  
Based on **Blueprint Framework** and **Pterodactyl Panel** installation steps.
    Subscribe On Youtube IITZ_YTANSH

