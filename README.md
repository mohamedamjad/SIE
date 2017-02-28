# Sécurité des informations et des échanges

## Groupe

- Mickael AVRIL
- Frederic MAMATH

## TP

- Trouvez 3 vulnérabilités dans la metasploitable
- Exploitez les
- Expliquez dans un petit rapport en quoi consiste les vulnérabilités
- Corrigez les vulnerabilités que vous avez exploiter
- Comment avez-vous fait ?

## Travail réalisé

### Première vulnérabilité

- Nom: UnrealIRCd IRC Daemon
- Référence du CVE : 2010-2075
- Description de la vulnérabilité : Il y a un backdoor dans le code. Elle est déclenchée par l'envoi des lettres "AB" suivis d'un système de commande du serveur sur n'importe quel port d'écoute.
- Exploit :
  - https://www.exploit-db.com/exploits/13853/
  - Metasploit possède un module nommé __< exploit/unix/irc/unreal_ircd_3281_backdoor >__ pour exploiter cette vulnérabilité, il ouvre un shell interactif.
- Correction :
  - Mettre à jour le daemon UnrealIRCd
  - Problème rencontré :
    - Impossible de mettre à jour le daemon grâce à la commande __apt-get__ à partir du wi-fi de l'école, ni d'un point de connexion d'un smartphone, le problème semble venir de la machine metasploitable sur laquelle on travail.
  - Solution essayé :
    - Vérification des droits et autorisations dans l'iptable
    - Téléchargement des sources de la nouvelle version de __UnrealIRCd__ sur la machine __Kali-Linux__ et copie sur la machine __Metasploitable__ grâce à la commande __scp__

### Deuxième vulnérabilité

- Nom :
- Référénce du CVE :
- Description de la vulnérabilité :
- Exploit :
- Correction :

### Troisième vulnérabilité

- Nom :
- Référénce du CVE :
- Description de la vulnérabilité :
- Exploit :
- Correction :
