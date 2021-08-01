# Delegate Ubuntu Server "DUS"
The Delegates Ubuntu server calculation of the redistribution to voters of the delegate's incomes

<p align="center">
    <img src="/banner_infi.png" />
</p>

[![License: MIT](https://badgen.now.sh/badge/license/MIT/green)](https://opensource.org/licenses/MIT)

> Lead Maintainer: [Infinity developers](https://github.com/Plusid)

## What's for?

the DUS is designed to help delegates share their income with voters.
Beforehand, the delegate chooses these redistribution criteria on the mobile APP menu "Delegate Setting"
The wallet calculated according to the delegate's criteria

## What's beneficiary wallet?

In the redistribution criteria there is a beneficiary wallet.
This wallet is different from the delegate wallet:
If the delegate chooses who will redistribute 80% of his income.
The due will calculate that the beneficiary wallet will receive 20% of the delegate's income.

## Why some accounts is exclude from the distribution?

The delegate can choose to exclude voters with a low balance from the redistribution to limit the dilution of income generated by transaction fees
If the chosen delegate excludes the accounts which have a too low balance, the DUS excludes them from the redistribution.the votes count for the delegate but the DUS excludes them from the redistribution.

### Server Prerequisites

- minimum VPS recommended 
1 CPU 1GB 
25GB Disk
1000GB transfer

- ubuntu 20

### Setup

<details><summary>Install</summary>

Install Delegate Ubuntu Server 

1 - Use the installation script seup-server.sh that you can download from https://github.com/InfinitySoftwareLTD/delegate_ubuntu_server.git using :
```bash
#wget https://raw.githubusercontent.com/InfinitySoftwareLTD/delegate_ubuntu_server/main/setup-server.sh
```

```bash
Run the following commands as root :
# chmod 755 setup-server.sh
# ./setup-server.sh
```
Note : if you hit any error when running the setup-server.sh script make sure first that there is no newline added (^M) at the end of each line in the script, run the following command to remove them if any :
 ```bash
sed -e "s/\r//g" setup-server.sh > setup-server.sh.tmp
mv setup-server.sh.tmp setup-server.sh
```

2 - Register wallet

```bash
cd ~laravel/crypto
php artisan crypto:register
```

Choice your blockchain "infinity" or "hedge"
Enter your network: 

```bash
infinity
```
or
```bash
hedge
```

Entry your delegate phrase (wallet passphrase) as forger
Enter your wallet delegate:

```bash
"this is my secret passphrase"
```

3 - To monitor your application you can use the followings :
    
### check scheduler logs :
```bash
cd ~laravel/crypto 
tail -f storage/logs/schedule_job.log
```
  
### check show_logs :    
```bash
php artisan crypto:admin show_logs
```

</details>



## GitHub Development Bounty

-   Get involved with the development and start earning INFI : https://bounty.infinitysoftware.io

## Security

If you discover a security vulnerability within this package, please send an e-mail to security@infinitysoftware.io. All security vulnerabilities will be promptly addressed.

## License

[MIT](LICENSE) © [INFINITY Ecosystem](https://infinitysoftware.io)
