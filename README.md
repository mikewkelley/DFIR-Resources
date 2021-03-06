## C 
**Chrome**  
Extensions Folder Path - C:\Users\[login_name]\AppData\Local\Google\Chrome\User Data\Default\Extensions

## D 
**Defender**  
[Live Response Commands](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/live-response)  

## F  
**Forensic Toolkits**  
[SIFT Workstation](https://digital-forensics.sans.org/community/downloads)  

**Forensics (Capture Dead)**  
%SystemDrive%/hiberfil.sys  

**Forensics (Virtual)**  
VMware - .vmem file  
Hyper-V - .bin file  
Parallels - .mem file  
VirtualBox - .sav file *This is only a partial memory file. You'll need to dump memory like a normal bare-metal system for this hypervisor  

**Forensics (Capture Live)**  
[FTK Imager](https://accessdata.com/products-services/forensic-toolkit-ftk/ftkimager#:~:text=FTK%C2%AE%20Imager%20is%20a,%C2%AE%20(FTK)%20is%20warranted.)  
[Redline](https://www.fireeye.com/services/freeware/redline.html)  
[DumpIt](https://zeltser.com/memory-acquisition-with-dumpit-for-dfir-2/)  
[Win32dd](https://digital-forensics.sans.org/summit-archives/2010/eu-digital-forensics-incident-response-summit-matthieu-suiche-blue-screen-of-death-is-dead.pdf)  



**Forensics (Analysis)**  
[Volatility](https://github.com/volatilityfoundation/volatility)  

**Forensics (Guides)**  
[SANS Windows Forensic Analysis Poster](https://www.sans.org/security-resources/posters/windows-forensic-analysis/170/download)  

## I
**IR Process**  
[Incident Handler's Handbook](https://www.sans.org/reading-room/whitepapers/incident/incident-handlers-handbook-33901)  

## M
**Malware Scanning**  
[densityscout ](http://cert.at/downloads/software/densityscout_en.html)  *- checks for obfuscation and packing*  

## P
**PDF**  
[PDF Stream Dumper](http://sandsprite.com/blogs/index.php?uid=7&pid=57)   
[Analyzing Suspicious PDF Files With PDF Stream Dumper](https://zeltser.com/pdf-stream-dumper-malicious-file-analysis/)  

**Playbooks**  
[Incident Response Methodologies](https://github.com/certsocietegenerale/IRM)  
[IR Workflow Gallery](https://www.incidentresponse.com/playbooks/)  
[PagerDuty IR Documentation](https://response.pagerduty.com/)  
[Microsoft IR Playbooks](https://docs.microsoft.com/en-us/security/compass/incident-response-playbooks)  


**Prefetch**  
[WinPrefetchView](https://www.nirsoft.net/utils/win_prefetch_view.html)  

**Program Execution**  
[Using AppCompactCache (Shimcache) to Find Evil](https://digital-forensics.sans.org/summit-archives/DFIR_Summit/Johnny-AppCompatCache-the-Ring-of-Malware-Brice-Daniels-and-Mary-Singh.pdf)  
[Using Prefetch to Find Evil](https://www.hackers-arise.com/post/2016/11/02/digital-forensics-part-6-analyzing-windows-pre-fetch-files-for-evidence)  

## R  
**Remote Desktop Protocol**  
[Tracking and Analyzing Remote Desktop Activity Logs in Windows](http://woshub.com/rdp-connection-logs-forensics-windows/)  

## S
**ShimCache**  
[AppCompatCacheParser](https://github.com/EricZimmerman/AppCompatCacheParser)  

## T
**Threat Hunting**  
[SANS Hunt Evil Poster](https://www.sans.org/security-resources/posters/hunt-evil/165/download)

## W
**Web Browser**  
[Web Browser Forensics](https://www.digitalforensics.com/blog/an-overview-of-web-browser-forensics/)

**Windows (Investigating)**  
systeminfo: information about the OS and the system  
query user: displays information about user sessions
net users: displays user account information  
net user <username>: user information (last logon, etc)  
wmic startup list full: autorun information  
net localgroup administrators: users with local admin priv  
schtasks /FO CSV /V > exportedjobs.csv  
Event ID 4624: Successful Login Sessions  
Event ID 4672: Special Privileges assigned to new login  
host file: local dns records (dns cache poisoning) C:\Windows\System32\drivers\etc\hosts  
check for webshell: C:\inetpub\wwwroot  




## V  
**Volatility**  
Determine Profile: volatility -f MEMORY_FILE.raw imageinfo  
Validate Profile: volatility -f MEMORY_FILE.raw --profile=PROFILE pslist  
pslist: list processes  
netscan: view active network connections  
psxview: intentially hidden processes (look for false)  
ldrmodules: If any of these are false, that module has likely been injected  
apihooks: view unexpected patches in the standard system DLLs (instances where Hooking module: unknown)  
malfind: searches for malicious executables (usually DLLs) and shellcode inside of each process (.dmp can be uploaded to VT)  
dlllist: list all of the DLLs in memory  
dlldump: if a suspect processe is identified dump the contents of DLL files to the local system (.dll can be uploaded to VT)  
