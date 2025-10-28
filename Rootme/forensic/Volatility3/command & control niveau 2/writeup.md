ROOTME :

Analyse mémoire :
Command & Control niveau 2 :

Énoncé
Berthier, grâce à vous la machine a été identifiée, vous avez demandé un dump de la mémoire vive de la machine et vous aimeriez bien jeter un coup d’œil aux logs de l’antivirus. Malheureusement, vous n’avez pas pensé à noter le nom de cette machine. Heureusement ce n’est pas un problème, vous disposez du dump de memoire.
Le mot de passe de validation est le nom de la machine.
Le hash md5 du dump mémoire décompressé est e3a902d4d44e0f7bd9cb29865e0a15de

Voir cheat sheet hcktricks :
https://book.hacktricks.wiki/en/generic-methodologies-and-resources/basic-forensic-methodology/memory-dump-analysis/volatility-cheatsheet.html

Fichier ch2.tmp

Verifions integrité du fichier :



Notre objectif est d’extraire le nom de la machine avec volatility3 :
Le payload windows.info nous donne des infos de l’os commençons par investiguer dans ce cas-ci :









windows. Info nous informe :
Adresse base noyau : Kernel base 0x82801000
Indique si le système est 64 bits : Is64Bit False
Chemin vers base de l’espace utilisateur DTB 0x185000
Version windows NTBuildLab 7600.16385.x86fre.win7_rtm.09071 avec Major/Minor 15.7600
Mais pas d’infos sur le nom de la machine.
Essayons un autre payload banners.Banners va nous nous etere utilse pour connaître version windows de la machine.

Pas de bannières présentes dans la mémoire.
Revenons sur notres challenge, on a besoin du nom de la machine de l’utilisateur qui a été actif dans cette session, on essaiera un payload en rapport à cette domande windows.sessions qui permet d’afficher les sessions windows, leurs ID de session et le type de session(console, service etc.)








En étudiant cette capture de la requete, on comprend Session ID = 1 doit d’un utilisateur actf, Session type des différents processus, le PID, le nom des processus, la date et heur du dernier ‘logon’ et enfin du domaine soit le nom de la machine et utilisateur !






