# Gunnajs-Playbook-DFIR

How to investigate like a Gunnaj

![alt text](https://github.com/GunzyPunzy/Gunnajs-Playbook-IR/blob/main/anfader-forensics.png)

# Toolbox
<details>
  <summary> Utils </summary> 

### Autopsy
https://www.autopsy.com/

### Registry Explorer
https://ericzimmerman.github.io/#!index.md

### Prefetch Parser (PECmd.exe)
https://ericzimmerman.github.io/#!index.md

### Forensicator
https://github.com/Johnng007/Live-Forensicator

### Volatilty 
https://github.com/volatilityfoundation/volatility3

<details>
  <summary> Installation </summary> 

``` 
git clone https://github.com/volatilityfoundation/volatility3.git
cd volatility3
python3 setup.py install
python3 vol.py —h
```

</details>

### WinPmem
https://github.com/Velocidex/WinPmem

</details>

# Create forensic image
<details>
  <summary> FTK Imager </summary> 
 
  1. Create disk image
  2. Physical Drive
  3. Raw (dd)
  4. Image Fragment Size = 0

</details>

# Create memory dump
<details>
  <summary> WinPmem </summary> 
 
```
winpmem_mini_x64.exe physmem.raw
``` 

</details>

<details>
  <summary> Forensicator </summary> 
 
```
.\Forensicator.ps1 -RAM RAM
```

</details>

<details>
  <summary> FTK Imager </summary> 
 
1. File
2. Capture Memory...

</details>

# Hive Artifacts

### Registry paths

<details>
  <summary> Locations  </summary> 

### SAM, SECURITY & SOFTWARE

```
C:\Windows\System32\config
```

### NTUSER

```
C:\Users\<User>
```

</details>
  
<details>
  <summary> Time Zone </summary> 
  
```
SYSTEM\CurrentControlSet\Control\TimeZoneInformation
```
</details>
  
<details>
  <summary> User Information </summary> 
  
```
SAM\Domains\Account\Users
```
</details>
  
<details>
  <summary> Recent Files </summary> 

```
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
```
</details> 

### Plugged Devices
<details>
  <summary> USB Devices </summary> 
  
  ```
  SYSTEM\CurrentControlSet\Enum\USBSTOR
  ```
  ```
  SYSTEM\CurrentControlSet\Enum\USB
  ```
</details>
<details>
  <summary> USB device Volume Name </summary> 
  
  ```
  SOFTWARE\Microsoft\Windows Portable Devices\Devices
  ```
  </details>
</details>

# Application run times

<details>
    <summary> Windows Prefetch files </summary> 
    
  ### Last run times of applications & the number of times the application was run
  #### Prefetch files are located in the *C:\Windows\Prefetch* directory
  #### Parse Prefetch file
  ```
  PECmd.exe -f <path-to-Prefetch-files> --csv <path-to-save-csv>
  ```
  #### Parse Prefetch directory
  ```
  PECmd.exe -d <path-to-Prefetch-files> --csv <path-to-save-csv>
  ```
  
</details>


# Ransomware 
<details>
  <summary> Ransomware sites </summary> 

  ### Ransomware Onion URL's 
 
  https://www.ransomlook.io/groups
   
  ### Recent Posts
  
  https://ransomwatch.telemetry.ltd/#/recentposts
  
  ### Public Decryption keys 
  
  https://www.nomoreransom.org/en/index.html
  
</details>

# Malware analysis
  <details>
    <summary> Sites for malware analysis </summary> 
  
  https://www.virustotal.com/gui/home/upload

  https://any.run/

  https://hybrid-analysis.com/
   
  </details>

  <details>
    <summary> Memory analysis </summary> 
  
  ### Volatility
<details>
  <summary> Memory analysis </summary> 

#### Get imageinfo
```
python3 vol.py -f <file> windows.info
```
#### Get processes tree (not hidden)
```
python3 vol.py -f <file> windows.pstree # Get processes tree (not hidden)
```
#### Get process list (EPROCESS)
```
python3 vol.py -f <file> windows.pslist
```
#### Get hidden process list (malware)
```
python3 vol.py -f <file> windows.psscan
```
#### Display process command-line arguments
```
python3 vol.py -f <file> file.dmp windows.cmdline
```
#### List dlls
```
python3 vol.py -f <file> file.dmp windows.dlllist [--pid <pid>]
```
### Dump the .exe and dlls of the process in the current directory process
``` 
python3 vol.py -f <file> windows.dumpfiles --pid <pid> 
```
### Network scan
```
python3 vol.py -f <file>p windows.netscan
```
#### Find hidden and injected
```
python3 vol.py -f <file> windows.malfind
```
#### Yarascan
```
python3 vol.py -f <file> windows.yarascan --yara-file /tmp/malware_rules.yar
```
#### Scan for mutexes
```
python3 vol.py -f <file> windows.mutantscan
```

 </details>
</details>


# A PowerShell script to create an HTML report on recent changes in Active Directory.
https://gist.github.com/jdhitsolutions/9255f0bf7fe0dc6d2dde868c18d5049f

# A PowerShell function and format file for getting Active Directory user management events from the security event logs on domain controllers.
https://gist.github.com/jdhitsolutions/a4e6291741ec95e3bfe53f15a380da47
