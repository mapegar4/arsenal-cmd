# WEB

% web

## extract links from an url
#plateform/linux #target/remote #cat/RECON 
```
curl -k -s -L <url> | grep -o 'http://[^"]*' | cut -d "/" -f 3 | sort -u
```
