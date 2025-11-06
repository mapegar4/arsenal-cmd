# projectdiscovery

#platform/linux #target/remote #cat/RECON #tag/scan

## ProjectDiscovery - intern top/100 nuclei killchain
```
sudo /home/kali/.pdtm/go/bin/naabu -host <ip_range> -top-ports 1000 -silent -stats | httpx -silent -o <output_file> | nuclei -s low,medium,high,critical -o <output_file>
```
## ProjectDiscovery - targets file top/100 nuclei killchain
```
sudo /home/kali/.pdtm/go/bin/naabu -list <targets_file> -top-ports 1000 -o naabu.out -stats | httpx -o <output_file> | nuclei -s low,medium,high,critical -o <output_file>
```
## ProjectDiscovery - Nuclei Network/Host scanning 

```
nuclei -nh -tags network,tcp,udp -l <targets_file>
```

## ProjectDiscovery - AllPorts nuclei killchain
```
sudo /home/kali/.pdtm/go/bin/naabu -host <ip_range> -p - -stats | httpx -o <output_file> | nuclei -s low,medium,high,critical
```
## Projectdiscovery - DNS filter active subs
```
subfinder -d <domain> -o <output_file> | dnsx -l <targets_file> -o <output_file>
```
## Projectdiscovery - DNS extract sub A records
```
cat <targets_file> | dnsx -silent -a -resp-only > <output_file>

```
## Projectdiscovery - Subfinder gather all subs, dnsx, naabu, httpx and nuclei (External test) 
```
subfinder -d <domain> -o <output_file> | dnsx -l <targets_file> -o <output_file> | sudo /home/kali/.pdtm/go/bin/naabu -top-ports 10000 -stats | httpx -o <output_file> | nuclei -s low,medium,high,critical

```

#platform/linux #target/remote #cat/bugbounty #tag/webvuln

## BorkBounty - Fetch known URLs from AlienVault's Open Threat Exchange, the Wayback Machine, and Common Crawl, and feed them through burp
```
gau <input_domain> --subs --blacklist png,jpg,gif | httpx -silent -proxy http://127.0.0.1:8080/
```

## Worlist generation based on external infrastructure
```
echo <target> | subfinder -silent | httpx | hakrawler | haklistgen
```
