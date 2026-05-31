================================================================================
                    WATTx Testnet v0.1.0 — Node Distribution
================================================================================

WATTx is a Proof-of-Stake blockchain with 1-second block times and tiered
trust scoring for validators.

BINARIES INCLUDED (Linux x86-64):
----------------------------------
  wattx-qt        - GUI Wallet (recommended for most users)
  wattxd          - Daemon (headless server)
  wattx-cli       - Command-line interface
  librandomx.so   - Required shared library (must be in same directory)

Mac and Windows builds: see Releases on GitHub for native packages.
Android/iOS: see WATTxWallet app (Google Play / App Store).

QUICK START (Linux GUI):
------------------------
  chmod +x launch-wattx-qt.sh
  ./launch-wattx-qt.sh -testnet

QUICK START (Linux Daemon / Seednode):
---------------------------------------
1. Create config directory:
     mkdir -p ~/.wattx-testnet

2. Copy wattx.conf.example to ~/.wattx-testnet/wattx.conf and edit as needed.

3. Start daemon:
     LD_LIBRARY_PATH=$(pwd) ./wattxd -testnet -datadir=$HOME/.wattx-testnet -daemon

4. Check status:
     LD_LIBRARY_PATH=$(pwd) ./wattx-cli -testnet -datadir=$HOME/.wattx-testnet getblockchaininfo
     LD_LIBRARY_PATH=$(pwd) ./wattx-cli -testnet -datadir=$HOME/.wattx-testnet getstakinginfo

macOS QUICK START:
------------------
1. Create config directory:
     mkdir -p ~/Library/Application\ Support/WATTx/testnet3

2. Copy wattx.conf.example to that directory and rename to wattx.conf

3. Run the app bundle (see Releases for .dmg)

Windows QUICK START:
--------------------
1. Create config directory: %APPDATA%\WATTx\testnet3

2. Copy wattx.conf.example to that directory and rename to wattx.conf

3. Run wattx-qt.exe from the installer (see Releases for .exe)

CONNECTING TO THE TESTNET:
---------------------------
Nodes automatically bootstrap from the seednode at first launch:
  Seednode: 76.131.208.215:13888

You can also add it manually in wattx.conf:
  addnode=76.131.208.215:13888

Or via CLI:
  wattx-cli -testnet addnode 76.131.208.215:13888 add

TESTNET PORTS:
--------------
  P2P:  13888
  RPC:  13890

NETWORK PARAMETERS (Testnet):
------------------------------
  Block Time:        1 second
  Block Reward:      0.08333333 WATTx
  Bootstrap Reward:  20,000 WATTx (first 500 blocks only — for faucet)
  PoW Phase:         Blocks 0–1000
  PoS Phase:         Block 1001+
  Coinbase Maturity: 500 blocks (~8 minutes)
  Min Validator:     0 WATTx (no minimum on testnet)
  Testnet bech32:    tw1...

STAKING:
--------
- No minimum stake on testnet
- Coins mature after 500 confirmations (~8 min)
- Unlock wallet for staking:
    wattx-cli -testnet walletpassphrase "your_passphrase" 9999999 true

TRUST TIER SYSTEM:
------------------
  Bronze  (95%+ uptime):    1.0x rewards
  Silver  (97%+ uptime):    1.25x rewards
  Gold    (99%+ uptime):    1.5x rewards
  Platinum (99.9%+ uptime): 2.0x rewards

SUPPORT:
--------
  GitHub:  https://github.com/nucash-mining/WATTxchain
  Web:     https://wattxchange.app

================================================================================
WATTx Core v0.1.0-testnet | Based on QTUM / Bitcoin Core | MIT License
================================================================================
