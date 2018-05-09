## Overview
If you are any good at making logos or websites, please be sure to submit [Bounty](Bounties.md) entires soon! __We will be closing bounty submissions once we initiate Pre-Launch!__

We plan on beginning our __Pre Launch Checklist__ at __[5:00 PM PST on Tuesday, May 8, 2018]__. We will start disconnecting most of our infrastructure from Testnet in preperation for Mainnet launch.

We plan on beginning our __Launch Checklist__ at __[7:00 AM PST on Saturday, May 12, 2018]__. Many things can go wrong when trying to launch a new service, so we are unable to give an exact launch time. If you are eager to participate at the very beginning of our launch, please make sure you are in our Discord server, and are listening for our announcements. 

## Pre Launch Checklist - [5:00 PM PST, Tuesday, May 8, 2018]
* [x] __Announce in Discord:__ Pre-Launch checklist has begun
* [x] Stop Pool - Disconnect from Testnet, remove Testnet warning
* [x] Stop Explorer - Disconnect from Testnet
* [x] Stop Web Wallet - Disconnect from Testnet
* [x] Stop Netstats - Disconnect from Testnet
* [x] Disable dev & Testnet node from sending netstats
* [x] Setup Mainnet Bootnode hosts (US, EU, Asia, ...)
* [x] __Gath:__ Update MainNetGenesisHash
* [x] __Gath:__ Update MainnetBootnodes with bootnode enode://
* [x] __Gath:__ Update Version to 1.0.3
* [x] __Gath:__ Compile for Linux, Mac, Windows
* [ ] __Gath:__ Compress binaries and prep for release
* [ ] Get Pool ready for Mainnet
* [ ] Get Explorer ready for Mainnet
* [ ] Get Web Wallet ready for Mainnet
* [x] Get Netstats ready for Mainnet
* [ ] Get Grafana/Graphite/Prometheus ready for Mainnet
* [ ] Launch Website!
* [ ] __If time permits:__ Perform a dev only mock launch.

## Launch Checklist - [7:00 AM PST, Saturday, May 12, 2018]
* [ ] __Announce in Discord:__ Launch checklist has begun
* [ ] Init genesis block on bootnodes
* [ ] Bootnodes online - verify they see each other
* [ ] Setup pingdom to monitor bootnodes
* [ ] Netstats Online (all bootnodes reporting for duty)
* [ ] Prepare Pool 
* [ ] __Announce in Discord:__ WE WILL BE STARTING SOON... and wait... for dramatic... tension :)
* [ ] Unlock Gath download links
* [ ] Enable Pool Miner Proxies
* [ ] __Announce in Discord:__ Links to download Gath (GitHub binaries will be released post launch)
* [ ] __Announce in Discord:__ Pool is open
* [ ] Drink a Beer
* [ ] Explorer Online
* [ ] Web Wallet Online
* [ ] Grafana Online
* [ ] Verify Prometheus is scraping all Mainnet hosts
* [ ] Verify we are getting graphite metrics
* [ ] Monitor Stabilty

## Post Launch Checklist
* [ ] Test, Verify, and Release: Standalone Desktop Wallet (win, mac, linux)
* [ ] Releases Binaries on GitHub, Open Source GitHub
