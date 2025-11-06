# linWinPwn

#platform/linux #target/remote #cat/AD #tag/enum

## linWinPwn - Anonymous enumeration (null session)
```
linWinPwn -t <dc_ip>
```

## linWinPwn - Automatic enumeration with credentials
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --auto
```
## linWinPwn - Automatic enumeration null session
```
linWinPwn -t <dc_ip> -d <domain> -u '' -p '' --auto
```

## linWinPwn - NTLM hash authentication
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -H <lm_hash:nt_hash> --auto
```

## linWinPwn - Kerberos ticket authentication
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -K <path_to_krb5cc_ticket> --auto
```

## linWinPwn - AES Key authentication (Kerberos)
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -A <aes_key> --auto
```

## linWinPwn - Certificate authentication (PFX)
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -C <path_to_cert.pfx> --cert-pass <cert_password> --auto
```

## linWinPwn - Auto config with NTP sync and hosts entry
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --auto --auto-config
```

## linWinPwn - LDAPS enumeration (port 636)
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --ldaps --auto
```

## linWinPwn - Force Kerberos authentication
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --force-kerb --auto
```

## linWinPwn - Target all domain servers
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> -T All --auto
```

## linWinPwn - Target specific server
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> -T IP=<target_ip> --auto
```

## linWinPwn - Target servers from file
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> -T File=<targets_file> --auto
```

## linWinPwn - Custom interface specification
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> -I <interface> --auto
```

## linWinPwn - Custom wordlists for brute force
```
linWinPwn -t <dc_ip> -d <domain> -U <user_wordlist> -P <password_wordlist> --auto
```

## linWinPwn - Verbose output for debugging
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --verbose --auto
```

## linWinPwn - Custom output directory
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> -o <output_dir> --auto
```

## linWinPwn - Through proxychains (SSH tunnel from Windows)
```
proxychains ./linWinPwn_proxychains -t <dc_ip> -d <domain> -u <username> -p <password> --auto
```

## linWinPwn - LDAP with custom port
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --ldap-port <port> --auto
```

## linWinPwn - LDAP with channel binding/signing
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --ldap-bind-sign --auto
```

## linWinPwn - Custom DNS server
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --dns-ip <dns_server> --auto
```

## linWinPwn - Use TCP for DNS queries
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --dns-tcp --auto
```

## linWinPwn - Use IP addresses instead of hostnames
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --use-ip --auto
```

## linWinPwn - Specify DC domain manually
```
linWinPwn -t <dc_ip> -d <domain> -u <username> -p <password> --dc-domain <dc_domain> --auto
```
