# Domain Generating Algorithm

A Domain Generating Algorithm (DGA) is a program or subroutine that provides malware with new domains on demand or on the fly.

## History
Kraken was the first malware family to use a DGA (in 2008) that we could find. Later that year, Conficker made DGA a lot more famous.

## What’s the use?
The DGA technique is in use because malware that depends on a fixed domain or IP address is quickly blocked, which then hinders operations. So, rather than bringing out a new version of the malware or setting everything up again at a new server, the malware switches to a new domain at regular intervals.

An example of DGA in practice is C&C servers for botnets and ransomware. If we were able to block these or take them down, we would cut the link between the victims and the threat actor. Bots would no longer be able to fetch new instructions and machines infected with ransomware would be unable to request encryption keys and send user data.

The constant changing of the domain for the C&C server is also sometimes called “Domain Fluxing” or “Fast Fluxing”, which actually is a reference to an older technique based on abusing the DNS load balancing system.

More details about how it works
To better understand how these algorithms work, let’s look at the requirements they have to fulfill:

- The routines have to generate domains that are predictable to both sides of the communication chain.
- The routines have to be as unpredictable for security researchers as possible.
- The domain registration fee has to be low, given the huge amounts of domains that will be used.
- The need for speed can be enormous.
- The registration process has to be anonymous or at least untraceable.

To achieve predictability, yet remain hard to research, the DGA routines use a few building blocks:
- Seed, the base element
- An element that changes with time
- Top Level Domains (TLDs)

The seed can be a phrase or a number. Practically anything that the threat actor can change at will (e.g. when they switch to a new version), and that can be used in an algorithm. The seed and the time-based element are combined in an algorithm to create the domain name and this “body” will be combined with one of the available TLDs.

Note that a time-based element need not be something like the date and time. It can be something else that varies with time, like for example the trending topic on Twitter in a certain country at the moment of the connection. Actually, something that is difficult to predict is preferred, as this makes it harder for researchers to register certain domains ahead of time and intercept traffic or do a takeover.

Another trick to throw off countermeasures is to not use all the domains that the algorithm produces, but only certain ones. This will drastically increase the number of domains necessary to register by researchers if they plan to intercept the traffic.

When it comes to TLDs, .xyz, .top, and .bid are very popular at the moment. This is due to the reasons mentioned earlier: low costs and quick availability, because the registrars allow automated and anonymous domain registrations.

## Summary
Domain Generating Algorithms are in use by cybercriminals to prevent their servers from being blacklisted or taken down. The algorithm produces random looking domain names. The idea is that two machines using the same algorithm will contact the same domain at a given time, so they will be able to exchange information or fetch instructions.

## Links
[Dissecting Domain Generation Algorithms](http://go.cybereason.com/rs/996-YZT-709/images/Cybereason-Lab-Analysis-Dissecting-DGAs-Eight-Real-World-DGA-Variants.pdf)

[Threat Spotlight: Dyre/Dyreza: An Analysis to Discover the DGA](http://blogs.cisco.com/security/talos/threat-spotlight-dyre)
