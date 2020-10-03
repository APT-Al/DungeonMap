## Deployment
- Strategic web compromise(watering-hole attacks) : https://www.youtube.com/watch?v=RNWiqj_lkcs
- Drive-by download : Occurs when a system automatically downloads a piece of malware
- Phishing emails
- Exploiting vulnerabilities

### Prevention
- virtual sandbox
- Bare-metal sandbox


## Installation
One method of installation would actually use the download dropper methodology, where the first file is a small piece of code designed to evade detection and communicate with extortionist’s command-and-control channels. The executable would then receive commands to download the ransomware itself for infection on the compromised system. Once it has landed on the system, the ransomware application will install itself on the system.

- Change settings to run itself when the computer opens
- Disable the firewall/antivirus
- Delete logs / Disable recovery enviroments


## C&C
In a ransomware attack, once the malicious code is deployed and installed, it will begin to reach out to its command servers, looking for instructions.

Command-and-control channels vary with the different variants and families of malware. In some cases, these can be as simple as web-based communications leveraging an unencrypted HTTP protocol to complicated systems that leverage embedded TOR services to connect. The more complex systems like TOR make it even more difficult to trace the exact location of the criminals participating in the extortion, and indeed some of the ransomware variants actually install TOR clients on end-points to ensure they have secure communications.


## Destruction
The ransomware will encrypt all files it's determined on the victim device.

### Symmetric Key Encryption
- fewer system resources as a result reduce detection
- A major disadvantage of symmetric key encryption is that is can be defeated. It is possible for a user to pull the key from active memory and use this to decrypt the files on the system while it is offline.

### Asymmetric Key Encryption
- The public key is used on the infected system to encrypt the files, and the private key is used to decrypt the files.

-In ransomware that leverages an embedded public key, the methodology is fairly straightforward and can be initiated whether the computer is online or not. The disadvantage of this technique is that a new public key must be genereated for each attack.


Encrypt all files with individual AES key(Symmetric) then encrypt all AES keys with server public RSA key(Asymmetric). ransomware will produce a special AES key for each file.



## Extortion
The victims are shown a screen that tells them how they have been compromised. Extortionists use any number of methods to enforce payment.

System or Browser Locking

- you will get 50% discount if you pay on the day of infection
- each passing day, buying the cost of storing decryptor key become more expensive
- after XxX day, the decryptor key will be deleted

it depends on your imagination



# ATTACK CHAIN
1. The ransomware must execute and unpack itself and then collect system information.
2. The ransomware has to change registry settings to maintain persistence.
3. More advanced ransomware disables system restore and deletes everything in the Volume Shadow Copy (VSC).
4. Most, but not all, ransomware has to call out to command-and-control infrastructure to get a public key that will be used to encrypt the files.
5. The ransomware now has to enumerate the files.
6. It then begins to read and encrypt the files.
7. If each encrypted file is written to a new file, the original files must be deleted.
8. Finally, the encryption key is removed from the local machine and sent back to the controller.


## Open Source Ransomware
- https://github.com/NYAN-x-CAT/Lime-RAT :: visualBasic :: .NET
- https://github.com/mauri870/ransomware :: go :: 
- https://github.com/tarcisio-marinho/GonnaCry :: py :: veryNice
    - Ransomware Impact on industry
        - https://medium.com/@tarcisioma/how-can-a-malware-encrypt-a-company-existence-c7ed584f66b3

    - How this ransomware encryption scheme works:
        - https://medium.com/@tarcisioma/ransomware-encryption-techniques-696531d07bb9

    - How this ransomware works:
        - https://0x00sec.org/t/how-ransomware-works-and-gonnacry-linux-ransomware/4594
        - https://medium.com/@tarcisioma/how-ransomware-works-and-gonnacry-linux-ransomware-17f77a549114

    - Mentions:
        - https://www.sentinelone.com/blog/sentinelone-detects-prevents-wsl-abuse/
        - https://hackingvision.com/2017/07/18/gonnacry-linux-ransomware/
        - https://www.youtube.com/watch?v=gSfa2L158Uw
- https://github.com/sithis993/Crypter :: py :: .NET
- https://github.com/wille/cry :: go
- https://github.com/leonv024/RAASNet :: py :: .NET :: Ransomware as as Service => C&C interface



## Blog Posts

- https://www.malwaretech.com/2016/12/open-source-ransomware.html









> WHERE AM I <br>
> continue from Chapter 3.