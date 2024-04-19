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

</details>

# Create forensic image
<details>
  <summary> FTK Imager </summary> 
 
  1. Create disk image
  2. Physical Drive
  3. Raw (dd)
  4. Image Fragment Size = 0

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
   
  </details>

  <details>
    <summary> Memory analysis </summary> 
  
  ### Volatility
   
  </details>


# A PowerShell script to create an HTML report on recent changes in Active Directory.
https://gist.github.com/jdhitsolutions/9255f0bf7fe0dc6d2dde868c18d5049f

# A PowerShell function and format file for getting Active Directory user management events from the security event logs on domain controllers.
https://gist.github.com/jdhitsolutions/a4e6291741ec95e3bfe53f15a380da47
