![threat model](https://raw.githubusercontent.com/birb-digital/wrongthink/master/threat%20model.png)

# collected data
while you are using wrongthink.me, wrongthink must store certain pieces of data for it to work. this includes:

* your ip address
* your username
* peerjs signaling data

this data is deleted 60 seconds after you log off the service and is not logged. in certain situations (debugging), wrongthink may log when your username connects and disconnects from the server.

wrongthink.me's web server does not have any access logs.

in the future, wrongthink.me will have a TURN server to relay data between two clients who cannot directly connect. the encrypted link is still maintained between both clients and wrongthink cannot see the traffic.

notes:
* logging off is defined as closing the tab

# warranty
no warranty is provided with this software. the security of your communications is not guaranteed.

the security of your communications is determined by many factors, including but not limited to:
* the browser and extensions you are running (and tabs you have open if your computer is vulnerable to Spectre or Meltdown)
* the software on your computer (especially if your computer is vulnerable to Spectre or Meltdown)
* your operating system (are you sure your OS isn't bugged?)
* hardware (hardware can be bugged)
* physical surveillance
* network surveillance (passive attacks, active attacks, etc.)
* the software itself (are there any vulnerabilities?)
* YOU (are you taking the right security precautions? are you using the built in security features?)
* time (an adversary may not be able to decrypt your conversations now, but they could be decrypted when quantum computers are feasible)

it's hard to get it right, and communications will not be safe forever. we believe that your communications should be secure for at least 5 years or until quantum computers are more advanced. however, security is not guaranteed. you are using this software at your own risk. if you are confident that all of these factors are in your favor, then go ahead and use it. otherwise, don't. cryptography will not help if you or your computer are compromised.

# security policy

vulnerabilities in previous versions of wrongthink are low priority and can be reported via an issue on the github repo. vulnerabilities or flaws in the current version of wrongthink are high priority and should be sent **only** to parabirb@protonmail.ch.

## what is a threat and what isn't a threat

we will take anything on crypto or html sanitization flaws.

## commit signatures

all legitimate commits will be signed with a PGP key (parabirb's has fingerprint 07F988C86662F3821CEC1E39BFB779869FEE99D2. the key itself is provided [here](https://keys.openpgp.org/vks/v1/by-fingerprint/07F988C86662F3821CEC1E39BFB779869FEE99D2))
