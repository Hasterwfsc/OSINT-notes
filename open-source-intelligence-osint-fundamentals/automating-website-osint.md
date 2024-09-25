# Automating Website OSINT

Usage&#x20;

```
./recon/sh tcm-sec.com
```

```bash
#!/bin/bash

domain=$1
RED="\033[1;31m" #this is for the red colour codde 
RESET="\033[0m" #reset back to default colour 

info_path=$domain/info
subdomain_path=$domain/subdomains
screenshot_path=$domain/screenshots

if [ ! -d "$domain" ];then #if directory does not exists make a directory 
    mkdir $domain
fi

if [ ! -d "$info_path" ];then #if info path no exists make that directory 
    mkdir $info_path
fi

if [ ! -d "$subdomain_path" ];then
    mkdir $subdomain_path
fi

if [ ! -d "$screenshot_path" ];then
    mkdir $screenshot_path
fi

echo -e "${RED} [+] Checkin' who it is...${RESET}"
whois $1 > $info_path/whois.txt #>> means appending to a file, > means overwriting a file 

echo -e "${RED} [+] Launching subfinder...${RESET}"
subfinder -d $domain > $subdomain_path/found.txt

echo -e "${RED} [+] Running assetfinder...${RESET}"
assetfinder $domain | grep $domain >> $subdomain_path/found.txt #add on to the subdomain list

#echo -e "${RED} [+] Running Amass. This could take a while...${RESET}"
#amass enum -d $domain >> $subdomain_path/found.txt

echo -e "${RED} [+] Checking what's alive...${RESET}"
cat $subdomain_path/found.txt | grep $domain | sort -u | httprobe -prefer-https | grep https | sed 's/https\?:\/\///' | tee -a $subdomain_path/alive.txt
#tea will output command

echo -e "${RED} [+] Taking dem screenshotz...${RESET}"
gowitness file -f $subdomain_path/alive.txt -P $screenshot_path/ --no-http #-P is the screenshot path
```





## Photon

```
photon -u https://tcm-sec.com
```

<figure><img src="../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>
