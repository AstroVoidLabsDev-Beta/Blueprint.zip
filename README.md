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
```bash
# Clone the repo
git clone https://github.com/<your-user>/<your-repo>.git
cd <your-repo>

# Run the installer (requires sudo/root)
chmod +x installer.sh
sudo ./installer.sh
