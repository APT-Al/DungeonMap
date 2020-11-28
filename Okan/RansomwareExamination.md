# save-the-queen-ransomware

1. Wrote the ransomware with the built-in winlogon.exe injection and file encryption functionality
2. Obfuscated the malicious code with ConfuserEx, wrapped the obfuscated code with Donut and obfuscated the result with base64 and Gzip
3. Obtained elevated privileges on the victim’s domain and used them to copy the encoded malware and the scheduled task to the domain’s SYSVOL share
4. Ran PowerShell code on devices in the domain to propagate the malware and log the progress of the attack in SYSVOL

# CERBER 
https://www.fireeye.com/blog/threat-research/2016/07/cerber-ransomware-attack.html

1. Target receives and opens a Word document.
2. Macro in document is invoked to run PowerShell in hidden mode.
3. Control is passed to PowerShell, which connects to a malicious site to download the ransomware.
4. On successful connection, the ransomware is written to the disk of the victim.
5. PowerShell executes the ransomware.
6. The malware configures multiple concurrent persistence mechanisms by creating command processor, screensaver, startup.run and runonce registry entries.
7. The executable uses native Windows utilities such as WMIC and/or VSSAdmin to delete backups and shadow copies.
8. Files are encrypted and messages are presented to the user requesting payment.


