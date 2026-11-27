# LANDO'S PLAYER — lot 1 (v1.0.0-dev)
*Music. Lyrics. Movies.* — package `com.lando.player`

## Compiler
**Android Studio (recommandé)** : File > Open > dossier `LandoPlayer`, attendre la synchro Gradle,
puis Build > Build APK(s). L'APK debug sort dans `app/build/outputs/apk/debug/`.

**Ligne de commande** (JDK 17 + SDK Android 34 installés) : `gradle assembleDebug`
(le wrapper `gradlew` sera généré par Android Studio ou via `gradle wrapper --gradle-version 8.7`).

**Sans PC** : poussez ce dossier sur un dépôt GitHub ; l'action `.github/workflows/build.yml`
compile et publie l'APK debug dans les "Artifacts" du run.

## Release signée
Créez `keystore.properties` à la racine (storeFile, storePassword, keyAlias, keyPassword)
puis `gradle assembleRelease`. Sans ce fichier, aucune release signée n'est produite.

## Installation
Copier l'APK sur le téléphone, autoriser les sources inconnues, installer.
Accepter la permission audio (et notifications sur Android 13+).

## Fonctions du lot 1 (implémentées, NON TESTÉES : jamais compilées)
Scan MediaStore, Room (titres, favoris, stats), lecture en arrière-plan + notification + écran verrouillé
(Media3), aléatoire, répétition, file modifiable, minuteur de sommeil, reprise de lecture, recherche,
tri, vues Titres/Albums/Artistes/Dossiers, favoris, historique, plus écoutés, ajoutés récemment,
mini-lecteur, lecteur complet, thème LANDO.

## Restant
Lot 2 : playlists manuelles/intelligentes, Lando Audio (égaliseur, bass boost), Lando Backup.
Lot 3 : Lando Lyrics (LRC, intégrées, sync, traduction), Lando Cinema (vidéo).
Architecture : packages `core / library / music / ui` dans un seul module Gradle
(découpage en modules séparés prévu plus tard).
