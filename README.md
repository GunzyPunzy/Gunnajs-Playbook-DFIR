# Gunnajs-Playbook-DFIR

How to investigate like a Gunnaj

![alt text](https://github.com/GunzyPunzy/Gunnajs-Playbook-IR/blob/main/anfader-forensics.png)

# Toolbox
<details>
  <summary> Utils </summary> 

### Registry Explorer
https://ericzimmerman.github.io/#!index.md

### ShellBag Explorer
https://ericzimmerman.github.io/#!index.md

### Forensicator
https://github.com/Johnng007/Live-Forensicator

</details>

# Hive Artifacts

<details>
    <summary> Hives </summary> 

  ### Registry paths
  <details>
    <summary> OS Version </summary> 
  
  ```
  SOFTWARE\Microsoft\Windows NT\CurrentVersion
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

  <details>
    <summary> Device Identification </summary> 

  ### Plugged Devices
  ```
  SYSTEM\CurrentControlSet\Enum\USBSTOR
  ```
  ```
  SYSTEM\CurrentControlSet\Enum\USB
  ```
  ### USB device Volume Name
  ```
  SOFTWARE\Microsoft\Windows Portable Devices\Devices
  ```
  </details>
  
</details>

# Ransomware 
<details>
  <summary> Ransomware sites </summary> 

 ### Ransomware URL's 
  <details>
    <summary> Ransomware Onion URL's </summary> 
  
  https://ransomwatch.telemetry.ltd/#/recentposts
  
  </details>
  
  <details>
    <summary> Recent Posts </summary> 
  
  https://www.ransomlook.io/groups
  
  </details>

  <details>
    <summary> Public Decryption keys </summary> 
  
  https://www.nomoreransom.org/en/index.html
  
  </details>

</details>


# A PowerShell script to create an HTML report on recent changes in Active Directory.
https://gist.github.com/jdhitsolutions/9255f0bf7fe0dc6d2dde868c18d5049f

# A PowerShell function and format file for getting Active Directory user management events from the security event logs on domain controllers.
https://gist.github.com/jdhitsolutions/a4e6291741ec95e3bfe53f15a380da47
