# Threat Hunting & Incident Investigation with Osquery

![osquerylogo](https://github.com/Kirtar22/ThreatHunting_with_Osquery/blob/main/osquery.png) ![](https://github.com/Kirtar22/ThreatHunting_with_Osquery/blob/main/wp.png)     ![dart](https://github.com/Kirtar22/ThreatHunting_with_Osquery/blob/main/OIP.bmp)



The objective of this repo is to share **100+ hunting queries (osquery)** that will help cyber threat analysts (hunter/investigator) in their hunting or investigation exercises. 
Broadly, I have covered **persistence, process interrogation, memory analysis, driver profiling, and other misc categories**. Persistence and Process Interrogations queries map to the multiple tactics & techniques/sub-techniques of MITRE ATT&CK framework. 

The following are the key highlights under each category. Please have a look at the repo(windows) for the details. 

## Persistence

- Registry Run Keys / StartUp Folder
- RunKeys (with hashvalue)
- Security Support Provider
- Service Creation / Modification (auto_start)
- look for suspicious dlls loaded by any service (with associated username & hash value of the dll) 
- WMI Event Consumers (commandline & script) 
- WMI Process interrogation
- Application Shimming
- Print Processors - Reg Keys
- look for suspicious print drivers
- Screensaver Backdoor
- Image File Execution Options Injection (IFEO)(debugger/GolbalFlag)
- PowerShell Process Interrogation
- Dynamic Data Exchange (DDE) 

## Process Interrogation

- Identify the parent & Grantparent processes for all OR a given process - look for any suspicious parent, child relationships 
- Identifying Suspicious Processes (processes) with usernames (users)
- Identifying the programs that are running from "TEMP" locations
- Identify the processes with open pipes (look for suspicious pipe and/or process) 
- Any processes spawning out of wow64 directory
- Identifying suspicious dlls loaded by any service with user_account associated with it (with hash value) 
- Identify if the binary is signed or not 
- PowerShell Process Interrogation (Parent / children of PowerShell) 
- WMI Process Interrogation (Parent / children of PowerShell)
- Identifying the excessive resources usage by a suspicious process - Excessive Memory Usage (In Bytes)
- Identifying the processes that makes the remote network connections and look for any suspicious connections

## Memory Analysis 

### Note:I have made an effort to create the queries equivalent to Volatility Plugins 

- pslist equivalent 
- pstree equivalent ( Parent & Child) 
- pstree equivalent ( Grandparent, Parent & Child) 
- dlllist equivalent ( with a specific pid ) 
- dlllist - load all the dlls
- getsids - equivalent 
- svcscan - equivalent 
- netscan - equivalent 
- Code Injection
- malfind (not exactly) equivalent 

## Driver Profiling 

- Group By and Order By device_name
- Drivers without manufacturer name with sign status
- Unsigned drivers
- Drivers with no service associated with sign status

## Miscellaneous

- File Profilig - Files with mtime<btime with hash values and sigcheck status in the critical directories
- Tracking User Changes
- look for any suspicious domain connection

## Linux 

Note: I will share "osquery.conf" file and queries related to Linux as I get some time to complete them. 
