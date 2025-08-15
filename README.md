# Blueprint + Pterodactyl Panel

> One-command setup for a Pterodactyl working directory with Node.js 20, Yarn, utilities, and the latest Blueprint Framework release.

![Banner](banner.png)

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

### 2) Install Yarn Globally
```bash
npm i -g yarn

### 3) Navigate to your Pterodactyl (usually /var/www/pterodactyl) and run the following command to initialize dependencies:
```bash
cd /var/www/pterodactyl
yarn
