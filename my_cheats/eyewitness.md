# eyewitness

% eyewitness, screenshot, recon

## EyeWitness - Screenshot from URL list
```
eyewitness --web —no-clear —no-prompt -f <url_file> -d <output_dir>
```

## EyeWitness - Single URL screenshot
```
eyewitness --web --single <url> -d <output_dir>
```

## EyeWitness - From Nmap XML file
```
eyewitness --web -x <nmap_xml> -d <output_dir>
```

## EyeWitness - From Nessus file
```
eyewitness --web -x <nessus_file> -d <output_dir>
```

## EyeWitness - With custom timeout
```
eyewitness --web -f <url_file> -d <output_dir> --timeout <seconds>
```

## EyeWitness - Threaded scanning
```
eyewitness --web -f <url_file> -d <output_dir> --threads <num_threads>
```

## EyeWitness - With jitter and delay
```
eyewitness --web -f <url_file> -d <output_dir> --jitter <seconds> --delay <seconds>
```

## EyeWitness - Custom User-Agent
```
eyewitness --web -f <url_file> -d <output_dir> --user-agent "<user_agent>"
```

## EyeWitness - Through proxy
```
eyewitness --web -f <url_file> -d <output_dir> --proxy-ip <proxy_ip> --proxy-port <proxy_port>
```

## EyeWitness - SOCKS5 proxy
```
eyewitness --web -f <url_file> -d <output_dir> --proxy-ip <proxy_ip> --proxy-port <proxy_port> --proxy-type socks5
```

## EyeWitness - Skip DNS resolution
```
eyewitness --web -f <url_file> -d <output_dir> --no-dns
```

## EyeWitness - Resolve hostnames
```
eyewitness --web -f <url_file> -d <output_dir> --resolve
```

## EyeWitness - Custom HTTP ports
```
eyewitness --web -f <url_file> -d <output_dir> --add-http-ports <port1,port2>
```

## EyeWitness - Custom HTTPS ports
```
eyewitness --web -f <url_file> -d <output_dir> --add-https-ports <port1,port2>
```

## EyeWitness - Specific ports only
```
eyewitness --web -f <url_file> -d <output_dir> --only-ports <port1,port2>
```

## EyeWitness - Prepend protocols
```
eyewitness --web -f <url_file> -d <output_dir> --prepend-https
```

## EyeWitness - With custom cookies
```
eyewitness --web -f <url_file> -d <output_dir> --cookies "<key1>=<value1>,<key2>=<value2>"
```

## EyeWitness - Show Selenium browser
```
eyewitness --web -f <url_file> -d <output_dir> --show-selenium
```

## EyeWitness - Resume from database
```
eyewitness --web --resume <ew_db_path>
```

## EyeWitness - No prompt to open report
```
eyewitness --web -f <url_file> -d <output_dir> --no-prompt
```

## EyeWitness - Custom report pagination
```
eyewitness --web -f <url_file> -d <output_dir> --results <hosts_per_page>
```

## EyeWitness - Max retries on timeout
```
eyewitness --web -f <url_file> -d <output_dir> --max-retries <num_retries>
```

## EyeWitness - Common web discovery workflow
```
nmap -p 80,443,8080,8443 -oX <scan_results.xml> <target_range>
eyewitness --web -x <scan_results.xml> -d <output_dir> --threads 10
```

## EyeWitness - Large scale with performance tuning
```
eyewitness --web -f <url_file> -d <output_dir> --threads 20 --timeout 10 --jitter 1 --no-prompt
```

## EyeWitness - Stealthy scanning
```
eyewitness --web -f <url_file> -d <output_dir> --threads 5 --jitter 3 --delay 2 --timeout 15
```
