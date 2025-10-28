# Titre du challenge — <<Command & Control - niveau 2>>
- **Plateforme** : Root-Me   
- **Catégorie** : forensic   
- **Difficulté** : facile    
- **ID / Score** : <<15>>

---

## 🎯 Contexte
**Énoncé**
Berthier, grâce à vous la machine a été identifiée, vous avez demandé un dump de la mémoire vive de la machine et vous aimeriez bien jeter un coup d’œil aux logs de l’antivirus. Malheureusement, vous n’avez pas pensé à noter le nom de cette machine. Heureusement ce n’est pas un problème, vous disposez du dump de memoire.
Le mot de passe de validation est le nom de la machine.
Le hash md5 du dump mémoire décompressé est e3a902d4d44e0f7bd9cb29865e0a15de



# 🧠 Analyse mémoire avec Volatility 3 — Extraction du nom de la machine

> 🔗 **Cheat sheet utile** : [HackTricks – Volatility 3 Memory Forensics](https://book.hacktricks.wiki/en/generic-methodologies-and-resources/basic-forensic-methodology/memory-dump-analysis/volatility-cheatsheet.html)

---

## 🗂️ Fichier à analyser
**Nom du fichier :** `ch2.tmp`

Avant toute analyse, vérifions l’intégrité du fichier pour s’assurer qu’il n’a pas été corrompu ou altéré lors du transfert.

```bash
sha256sum ch2.tmp
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/67005eab-5dc5-4559-abed-f3c910555706" />

