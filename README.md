<img width="128" height="128" alt="image" src="https://github.com/user-attachments/assets/37a05758-7bde-42e1-bed8-2c630d46383f" />
# **Pepinals.js – The Easy Way to Put Stuff on Pepecoin**  
**GitHub README.md**  
*Put pictures, text, or even your own coin on the Pepecoin blockchain — no coding degree needed!*  

[![Pepinals.js](https://img.shields.io/badge/Pepinals.js-v1.0.0-blue)](https://github.com/reallyshadydev/Pepinals)  
[![Pepecoin Core v1.1.0](https://img.shields.io/badge/Pepecoin%20Core-v1.1.0-green)](https://github.com/pepecoinppc/pepecoin/releases/tag/v1.1.0)  
[![Node.js](https://img.shields.io/badge/Node.js-v14%2B-orange)](https://nodejs.org)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
![Platform: Windows | macOS | Linux](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)  

---  

## What is Pepinals.js? (For Normal People)  

Imagine **Pepecoin** is like a giant notebook that anyone can write in — but once you write something, **you can’t erase it**.  

**Pepinals.js** is a simple tool that lets **you write anything** into that notebook:  
- A meme image  
- A message  
- Your own **PepeCoin token** (like making your own crypto coin!)  

It’s like **etching something into stone** — forever on the Pepecoin blockchain.  

You can:  
- **Inscribe** (put) a picture or text  
- **Create your own token** (like $PEPE, $FROG, etc.)  
- **Mint** (make) copies of your token  
- **See what you made** in a browser  

> **No coding needed** — just follow the steps below!  

---  

## What You Need (The Shopping List)  

| Thing | Why You Need It | How to Get It |  
|------|------------------|---------------|  
| **Pepecoin Core** | The "notebook" that stores everything | Download from [GitHub](https://github.com/pepecoinppc/pepecoin/releases/tag/v1.1.0) |  
| **Node.js** | Runs the Pepinals tool | [nodejs.org](https://nodejs.org) (click "LTS") |  
| **A computer** | Windows, Mac, or Linux | You already have this |  
| **Internet** | To send your inscription | Wi-Fi or cable |  
| **A little PPC** | To pay tiny fees (like postage) | Buy on an exchange or get from a friend |  

---  

## Safety First (Don’t Lose Your Stuff!)  

- **Only use a small amount of PPC** at first (like $1–$5 worth).  
- **Never share** these files:  
  - `.wallet.json` ← your money  
  - `.env` ← your node password  
- **Backup** `.wallet.json` to a USB or safe place.  
- **Don’t run this on a public computer**.  

> Think of it like a **hot wallet** — good for small stuff, not your life savings.  

---  

## Step 1: Install Pepecoin Core (The Notebook)  

This is the **Pepecoin app** that downloads the entire blockchain.  

### Download It  
1. Go to: [https://github.com/pepecoinppc/pepecoin/releases/tag/v1.1.0](https://github.com/pepecoinppc/pepecoin/releases/tag/v1.1.0)  
2. Pick your version:  
   - **Windows**: `pepecoin-1.1.0-win64-setup.exe`  
   - **Mac**: `pepecoin-1.1.0-osx.dmg`  
   - **Linux**: `pepecoin-1.1.0-x86_64-linux-gnu.tar.gz`  

### Install It  
- **Windows**: Double-click the `.exe` and follow the wizard.  
- **Mac**: Open `.dmg`, drag **Pepecoin Core** to **Applications**.  
- **Linux**: Extract and run `./pepecoin-qt` or `./pepecoind`.  

### Let It Sync  
- Open the app.  
- It will say **"Synchronizing with network"** — this takes **2 to 24 hours**.  
- Go get coffee. When it says **"0 blocks remaining"**, you’re ready.  

---  

## Step 2: Set Up Your Node Password  

We need to give Pepinals.js access to your Pepecoin app.  

1. **Find your Pepecoin folder**:  
   - **Windows**: Press `Win + R` → type `%APPDATA%\Pepecoin` → Enter  
   - **Mac**: Finder → Go → Go to Folder → `~/Library/Application Support/Pepecoin`  
   - **Linux**: `~/.pepecoin`  

2. **Create or edit** a file called `pepecoin.conf` (use Notepad or TextEdit).  

3. **Paste this** (change the username/password!):  

```ini
server=1  
txindex=1  
rpcuser=pepeuser  
rpcpassword=SuperSecretPassword123!  
rpcport=33875  
rpcallowip=127.0.0.1  
```  

4. **Save** and **restart** Pepecoin Core.  

> This lets Pepinals talk to your Pepecoin app safely.  

---  

## Step 3: Install Pepinals.js (The Pen)  

Now get the tool that writes in the notebook.  

### Open Terminal / Command Prompt  
- **Windows**: Search "cmd"  
- **Mac**: Search "Terminal"  
- **Linux**: Ctrl + Alt + T  

### Run These Commands  
```bash
git clone https://github.com/reallyshadydev/Pepinals.git  
cd Pepinals  
npm install  
cd bitcore-lib-pepe  
npm install  
cd ..  
```  

> If you don’t have `git`, just download the ZIP from GitHub and unzip it.  

---  

## Step 4: Set Up Your Pen (`.env` File)  

1. In the `Pepinals` folder, **create a file** called `.env`  
2. Paste this:  

```env
NODE_RPC_URL=http://127.0.0.1:33875  
NODE_RPC_USER=pepeuser  
NODE_RPC_PASS=SuperSecretPassword123!  
TESTNET=false  
FEE_PER_KB=18000000  
SERVER_PORT=3008  
```  

> Make sure the username/password match your `pepecoin.conf`!  

---  

## Step 5: Create Your Wallet (Your Bank Account)  

This is where your PPC lives for inscribing.  

```bash
node pepinals.js wallet new  
```  

→ It will show an address like: `PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n`  

**Send a little PPC to this address** (from an exchange or friend).  

Then run:  
```bash
node pepinals.js wallet sync  
```  

Check your money:  
```bash
node pepinals.js wallet balance  
```  

> **Pro Tip**: For a nicer wallet, try **Nintondo Wallet**! It's a browser extension for storing your Pepecoin, inscriptions, and tokens. Download from [Chrome Store](https://chromewebstore.google.com/detail/nintondo-wallet/akkmagafhjjjjclaejjomkeccmjhdkpa) or [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/nintondo-wallet/). It supports Pepecoin directly.  

---  

## Step 6: Inscribe Something! (Write in the Notebook)  

### Option 1: Inscribe a Picture or File  
Put your file (like `pepe.jpg`) in the `Pepinals` folder.  

```bash
node pepinals.js mint PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n pepe.jpg  
```  

→ It will say: `Inscription sent! TXID: abc123...`  

### Option 2: Inscribe Text  
```bash
node pepinals.js mint PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n "text/plain" 48656c6c6f2050657065  
```  

> `48656c6c6f2050657065` = "Hello Pepe" in hex  

---  

## Step 7: Make Your Own Token! (Like $PEPE)  

### Step 1: Deploy (Create) Your Token  
```bash
node pepinals.js prc-20 deploy PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n FROG 1000000 100  
```  

- `FROG` = your token name  
- `1000000` = total supply  
- `100` = max per mint  

### Step 2: Mint (Make) Some Tokens  
```bash
node pepinals.js prc-20 mint PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n FROG 100  
```  

### Step 3: Send Tokens  
```bash
node pepinals.js prc-20 transfer OtherAddressHere FROG 50  
```  

---  

## Step 8: Make Tons of Tokens (Bulk Mint)  

```bash
node pepinals.js bulk-mint PpB1ocks3ozcti7m5a3i2wViSuFAchLm3n FROG 1000000 100 5  
```  

→ Mints 100 tokens every 5 minutes until done. Press **Ctrl + C** to stop.  

---  

## Step 9: See Your Creation!  

```bash
node pepinals.js server  
```  

Open your browser:  
[http://localhost:3008](http://localhost:3008)  

Paste your **TXID** (from the mint command) to see your inscription!  

---  

## Step 10: Store and Trade Your Stuff (Wallet & Market)  

Once you've made your inscriptions or tokens:  

- **Wallet**: Use **Nintondo Wallet** to store your Pepecoin, Pepinals (inscriptions), and PRC-20 tokens safely. It's a free browser extension for Chrome or Firefox. Get it here: [nintondo.io](https://nintondo.io/). It lets you send, receive, and manage everything in one place.  

- **Market**: Buy, sell, or trade your inscriptions and tokens on **Nintondo Marketplace**. It's like eBay for Pepecoin stuff! Explore collections and tokens at [nintondo.io/market](https://nintondo.io/market). It supports Pepecoin, Bellscoin, and Dogecoin Ordinals.  

> **Why Nintondo?** It's built for Pepecoin users, with fast inscription support and secure features. Check it out to see your creations in action!  

---  

## Common Problems & Fixes  

| Problem | Fix |  
|-------|-----|  
| `Connection refused` | Is Pepecoin Core running? Check `.env` password |  
| `Insufficient priority` | Wait or increase `FEE_PER_KB=30000000` in `.env` |  
| `Wallet not syncing` | Run `node pepinals.js wallet sync` again |  
| `Too many transactions` | Use `wallet split 50` first |  
| Nothing shows in browser | Wait 10 mins, refresh, check TXID |  

---  

## All Commands (Cheat Sheet)  

```bash
# Wallet  
node pepinals.js wallet new  
node pepinals.js wallet sync  
node pepinals.js wallet balance  
node pepinals.js wallet split 50  
node pepinals.js wallet send <address> [amount]  

# Inscribe  
node pepinals.js mint <address> <file.jpg>  
node pepinals.js mint <address> "text/plain" <hex>  

# Tokens  
node pepinals.js prc-20 deploy <addr> TICKER 1000000 100  
node pepinals.js prc-20 mint <addr> TICKER 100  
node pepinals.js prc-20 transfer <addr> TICKER 50  

# Bulk  
node pepinals.js bulk-mint <addr> TICKER 1000000 100 5  

# View  
node pepinals.js server  
```  

---  

## Share Your Creation on X (Twitter)  

```text
Just inscribed my first meme on #Pepecoin with @PepinalsJS!   
Check it out: http://localhost:3008/tx/abc123...  

Made my own $FROG token too!   

#PPC #Crypto #Web3  

[Attach your picture]  
```  

---  

## You Did It!  

You just:  
- Ran a Pepecoin node  
- Created a wallet  
- Inscribed data forever  
- Made your own token  

**Welcome to the Pepecoin inscription gang!**  

---  

## Need Help?  

- **GitHub Issues**: [Open one here](https://github.com/reallyshadydev/Pepinals/issues)  
- **Reddit**: [r/pepecoin](https://reddit.com/r/pepecoin)  
- **Explorer**: [explorer.pepecoin.org](https://explorer.pepecoin.org)  

---  

**Last Updated: October 31, 2025**  
**Made with love for the Pepecoin community**
