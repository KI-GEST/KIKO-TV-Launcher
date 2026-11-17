# KIKO TV Launcher

Launcher Android TV en interface **arabe RTL** avec IPTV, Coran, Adhan et invocations, météo et horaires de prière. Cible : Mi TV Stick / Android TV (API 28+, écran paysage verrouillé).

Version : **1.2** (versionCode 3) · Package : `com.kiko.tvlauncher`

> **Installation sur téléphone :** depuis la v1.1, l'APK s'installe aussi sur un téléphone Android 9+ (la fonctionnalité Android TV `leanback` est optionnelle). L'interface reste optimisée pour Android TV. Depuis la v1.2, les boutons lecture/pause et retour du lecteur sont cliquables au toucher.

## Fonctionnalités

- **Accueil** : horloge, date grégorienne et hijri, météo (Sfax par défaut), horaires de prière, message de pied.
- **IPTV** : catalogue Direct / Films / Séries / Favoris en deux panneaux (liste à gauche, aperçu VLC à droite). Sources **M3U** et **Xtream Codes**. La source de démonstration importée au premier lancement est la liste publique **iptv-org** (`https://iptv-org.github.io/iptv/index.m3u`), avec repli hors ligne sur une petite playlist locale. Bouton d'ajout rapide iptv-org dans les sources.
- **Lecteur VLC intégré** (`libvlc-all:3.6.5`) pour HLS/M3U8, avec repli automatique ExoPlayer (Media3).
- **Coran** : 114 sourates, texte Uthmani + traduction française, écoute verset par verset (Alafasy) avec barre lecture / pause / stop / muet.
- **Adhan et invocations** : 3 voix d'adhan embarquées et 21 invocations (arabe + français).
- **Horaires de prière** : calcul local via adhan-java, méthode **Muslim World League (MWL)** par défaut (identique à Muslim Pro pour la Tunisie). Réglages : ville, méthode (11), madhab (Shafi/Hanafi), ajustement de −60 à +60 min par prière. Référence vérifiée (Sfax, 17 nov. 2026) : Fajr 05:25, Dhuhr 12:02, Asr 14:50, Maghrib 17:11, Isha 18:34.
- **Réglages défilants** : sources IPTV, fond d'écran (+ import personnalisé), langue (ar / fr / en), ville, prière, adhan.
- **Chiffres latins 0-9** partout (pas de chiffres arabo-indiens).

## Installation

Téléchargez l'APK depuis la section **Releases** (dernière version : **v1.2**), puis installez-le :

```powershell
adb install -r app-debug.apk
```

Si vous installez depuis le gestionnaire de fichiers du téléphone, autorisez l'installation d'applications de sources inconnues. Le fichier téléchargé s'appelle `app-debug.apk` (les releases sont immuables, donc le nom d'origine est conservé).

> L'APK de debug est volumineux (~285 Mo) car les bibliothèques natives VLC sont fournies pour `arm64-v8a`, `armeabi-v7a`, `x86` et `x86_64`.

## Notes

- La météo (Open-Meteo) et la récitation coranique nécessitent Internet ; les voix d'adhan et le texte du Coran sont hors ligne.
- Les contenus IPTV sont fournis par l'utilisateur ; l'application est uniquement un lecteur.
- Licences : Coran arabe et traduction Hamidullah (quran.com), voix d'adhan CC BY-SA / CC0, fonds d'écran Wikimedia Commons, police Tajawal (OFL).
