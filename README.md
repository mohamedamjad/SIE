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

- Nom : IRC
- Port : 6667
- Référence du CVE : 2010-2075
- Description de la vulnérabilité : Il y a un backdoor dans le code. Elle est déclenchée par l'envoi des lettres "AB" suivis d'un système de commande du serveur sur n'importe quel port d'écoute.
- Exploit :
  - https://www.exploit-db.com/exploits/13853/
  - Metasploit possède un module nommé __< exploit/unix/irc/unreal_ircd_3281_backdoor >__ pour exploiter cette vulnérabilité, il ouvre un shell interactif.
- Correction :
  - Mettre à jour le daemon UnrealIRCd
  - Limiter l'accès à quelques addresses IP
  - Configuration :
    - allow block
  - Problème rencontré :
    - Impossible de mettre à jour le daemon grâce à la commande __apt-get__ à partir du wi-fi de l'école, ni d'un point de connexion d'un smartphone, le problème semble venir de la machine metasploitable sur laquelle on travail.
  - Solution essayé :
    - Vérification des droits et autorisations dans l'iptable
    - Téléchargement des sources de la nouvelle version de __UnrealIRCd__ sur la machine __Kali-Linux__ et copie sur la machine __Metasploitable__ grâce à la commande __scp__

### Deuxième vulnérabilité

- Nom : VSFTPD
- Port : 21
- Référénce du CVE : Inconnue
- Description de la vulnérabilité : Il y a un backdoor dans les archives de VSFTPD.
- Exploit :
  - Metasploit possède un module nommé __< exploit/unix/ftp/vsftpd_234_backdoor >__ pour exploiter cette vulnérabilité,
- Correction :
  - Retrait complet de telnet car la communication par telnet n'est pas chiffré et est facilement interceptée par des outils tel que __wireshark__.
  - Configuration :
    - anonymous_enable = NO
    - local_enable = YES
    - userlist_enable = YES

### Troisième vulnérabilité

- Nom : Apache HTTPD
- Référénce du CVE : 2012-1823
- Description de la vulnérabilité : Il manque un caractère "=" lors de la gestion des requêtes, ce qui permet aux attaquants d'exécuter du code en écrivant des commandes dans la chaine de caractère.
- Exploit :
  - Metasploit possède un module nommé __< exploit/multi/http/php_cgi_arg_injection >__ pour exploiter cette vulnérabilité
- Correction :
  - Mettre à jour PHP à la version 5.4.2

### Notes:
MAMATH: 19
AVRIL: 19
