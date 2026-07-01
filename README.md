# Backup Automatique Bash

Script Bash pour sauvegarder automatiquement un dossier
avec horodatage, compression et rotation des anciennes sauvegardes.

## Fonctionnalités
- Sauvegarde compressée au format `.tar.gz` avec horodatage
- Création automatique du dossier de destination si inexistant
- Rotation automatique : conserve les 5 dernières sauvegardes
- Suppression des sauvegardes les plus anciennes au-delà du maximum
- Affichage clair dans le terminal avec indicateurs OK / ERREUR
- Enregistrement automatique dans un fichier de log `backup.log`

## Utilisation

# Rendre le script exécutable
chmod +x backup.sh

# Lancer la sauvegarde
./backup.sh

## Configuration
Les paramètres sont modifiables en haut du script :
DOSSIER_SOURCE="$HOME/documents"   # Dossier à sauvegarder
DOSSIER_BACKUP="$HOME/backups"     # Dossier de destination
NB_BACKUPS_MAX=5                   # Nombre de sauvegardes à conserver

## Exemple de sortie
================================================
       BACKUP AUTOMATIQUE
       2025-06-10 15:00:00
================================================

  Source  : /home/user/documents
  Dest.   : /home/user/backups
  Max     : 5 sauvegardes

  [✅ OK]      Sauvegarde créée : backup_2025-06-10_15-00-00.tar.gz (2.3M)
  [🗑️  ROTATION] Suppression de 1 ancienne sauvegarde

  SAUVEGARDES DISPONIBLES
  📦 backup_2025-06-10_15-00-00.tar.gz (2.3M)
  📦 backup_2025-06-09_14-00-00.tar.gz (2.1M)
  📦 backup_2025-06-08_13-00-00.tar.gz (2.0M)
  📦 backup_2025-06-07_12-00-00.tar.gz (1.9M)
  📦 backup_2025-06-06_11-00-00.tar.gz (1.8M)

## Contexte
Projet réalisé dans le cadre de mon apprentissage DevOps.
La sauvegarde avec rotation est une pratique standard en
administration système pour protéger les données tout en
maîtrisant l'espace disque utilisé.

## Technologies
- Bash
- Commandes Linux natives : tar, du, ls, mkdir, rm, date
