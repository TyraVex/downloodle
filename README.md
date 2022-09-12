## Introduction
<br>
Hello !<br>
<br>
This script is able to scrape the Centrale Lille Moddle website<br>
All it needs is a valid 'ModdleSession' Cookie from an legitimate Moddle account<br>
And even if a user have authorized access, all the files aren't available to download (An IG2I studient can't download some ITEEM files for example)<br>
<br>
By default, this script will download 'IG2I (Sous statut Etudiant)' files. To modify this setting, you need to edit this line :<br>
`if [[ "${optionNames[i+1]}" =~ "${optionNames[i]} / " || ! "${optionNames[i]}" =~ 'IG2I (Sous statut Etudiant)' ]]; then continue; fi`<br>
<br>
## To fix :
<br>
  1 - Replace '%20' and '&amp;' with ' ' and 'et'<br>
  2 - Fix '.zip?forcedownload=1' and '.tar.gz?forcedownload=1' with '.zip' and '.tar.gz'<br>
  3 - Support double point extentions and files without extentions<br>
  4 - Fix regex for download link<br>
<br>
## To do :
<br>
  1 - Multithreading<br>
  2 - Better download UI<br>
  3 - Auto decompress<br>
  4 - School selection<br>
<br>
## Error log (for devs)

```
  Caused by issue 1 :
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Initiation aux systèmes d'exploitation Linux/notes paquets.php/12854/mod_resource/content/0/notes%20paquets: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12854/mod_resource/content/0/notes%20paquets

  Caused by issue 2 :
  > Downloading Fichiers du TP2
  https://moodle2223.centralelille.fr/pluginfile.php/11920/mod_resource/content/0/tp2.zip?forcedownload=1
  And many more...

  Caused by issue 3 :
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Initiation aux systèmes d'exploitation Linux/Exercice 1 : mot1.php/12901/mod_resource/content/1/mot1: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12901/mod_resource/content/1/mot1
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Initiation aux systèmes d'exploitation Linux/Exercice 1 : mot2.php/12902/mod_resource/content/1/mot2: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12902/mod_resource/content/1/mot2
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Initiation aux systèmes d'exploitation Linux/Exercice 1 : reste.php/12903/mod_resource/content/1/reste: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12903/mod_resource/content/1/reste
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Initiation aux systèmes d'exploitation Linux/le fichier codage.php/12904/mod_resource/content/1/codage: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12904/mod_resource/content/1/codage
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Introduction à la programmation structurée/EX1 : le fichier fic est ici.php/13117/mod_resource/content/1/fic: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/13117/mod_resource/content/1/fic
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Introduction à la programmation structurée/EX2 : le fichier planningLE1 est ici.php/13118/mod_resource/content/1/planningLE1: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/13118/mod_resource/content/1/planningLE1
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Introduction à la programmation structurée/EX2 : le fichier planningLE1 est ici.php/13118/mod_resource/content/1/planningLE1: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/13118/mod_resource/content/1/planningLE1
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Introduction à la programmation structurée/EX3 : le fichier texte  62.php/13121/mod_resource/content/1/62: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/13121/mod_resource/content/1/62
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 1/Génie Informatique 1/Introduction à la programmation structurée/le fichier fic est ici.php/13127/mod_resource/content/1/fic: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/13127/mod_resource/content/1/fic
  ./downloodle: line 135: IG2I/IG2I (Sous statut Etudiant)/LE1 (Semestres 1 et 2)/LE1-Semestre 2/Génie Informatique 2/Structures de données statiques et algorithmique/floats : le fichier à lire par votre programme.php/12365/mod_resource/content/1/floats: No such file or directory
  https://moodle2223.centralelille.fr/pluginfile.php/12365/mod_resource/content/1/floats

  Caused by issue 4 :
  > Downloading intro
  https://moodle2223.centralelille.fr/pluginfile.php/11908/mod_resource/content/1/intro.mp4
  https://moodle2223.centralelille.fr/pluginfile.php/11908/mod_resource/content/1/intro.mp4', '', 'width=620,height=450,toolbar=no,location=no,menubar=no,copyhistory=no,status=no,directories=no,scrollbars=yes,resizable=yes'); return false;
  > Downloading culture
  https://moodle2223.centralelille.fr/pluginfile.php/11909/mod_resource/content/1/culture.mp4
  https://moodle2223.centralelille.fr/pluginfile.php/11909/mod_resource/content/1/culture.mp4', '', 'width=620,height=450,toolbar=no,location=no,menubar=no,copyhistory=no,status=no,directories=no,scrollbars=yes,resizable=yes'); return false;
  > Downloading intro frontend
  https://moodle2223.centralelille.fr/pluginfile.php/11910/mod_resource/content/1/intro_frontend.mp4
  https://moodle2223.centralelille.fr/pluginfile.php/11910/mod_resource/content/1/intro_frontend.mp4', '', 'width=620,height=450,toolbar=no,location=no,menubar=no,copyhistory=no,status=no,directories=no,scrollbars=yes,resizable=yes'); return false;
  > Downloading conclusion
  https://moodle2223.centralelille.fr/pluginfile.php/11915/mod_resource/content/1/conclusion.mp4
  https://moodle2223.centralelille.fr/pluginfile.php/11915/mod_resource/content/1/conclusion.mp4', '', 'width=620,height=450,toolbar=no,location=no,menubar=no,copyhistory=no,status=no,directories=no,scrollbars=yes,resizable=yes'); return false;
```

