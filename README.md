# KIKO TV Launcher

Launcher Android TV en interface **arabe RTL** avec IPTV, Coran, Adhan et invocations, météo et horaires de prière. Cible : Mi TV Stick / Android TV (API 28+, écran paysage verrouillé).

Version : **1.0** (versionCode 1) · Package : `com.kiko.tvlauncher`

## Fonctionnalités

- **Accueil** : horloge, date grégorienne et hijri, météo (Sfax par défaut), horaires de prière, message de pied.
- **IPTV** : catalogue Direct / Films / Séries / Favoris en deux panneaux (liste à gauche, aperçu VLC à droite). Sources **M3U** et **Xtream Codes**, bouton d'ajout rapide iptv-org.
- **Lecteur VLC intégré** (`libvlc-all:3.6.5`) pour HLS/M3U8, avec repli automatique ExoPlayer (Media3).
- **Coran** : 114 sourates, texte Uthmani + traduction française, écoute verset par verset (Alafasy) avec barre lecture / pause / stop / muet.
- **Adhan et invocations** : 3 voix d'adhan embarquées et 21 invocations (arabe + français).
- **Horaires de prière** : calcul local via adhan-java, méthode **Muslim World League (MWL)** par défaut (identique à Muslim Pro pour la Tunisie). Réglages : ville, méthode (11), madhab (Shafi/Hanafi), ajustement de −60 à +60 min par prière. Référence vérifiée (Sfax, 17 nov. 2026) : Fajr 05:25, Dhuhr 12:02, Asr 14:50, Maghrib 17:11, Isha 18:34.
- **Réglages défilants** : sources IPTV, fond d'écran (+ import personnalisé), langue (ar / fr / en), ville, prière, adhan.
- **Chiffres latins 0-9** partout (pas de chiffres arabo-indiens).

## Installation

Téléchargez l'APK depuis la section **Releases**, puis installez-le sur votre appareil Android TV :

```powershell
adb install -r KIKO-TV-Launcher-v1.0.apk
```

> L'APK de debug est volumineux (~290 Mo) car les bibliothèques natives VLC sont fournies pour `arm64-v8a`, `armeabi-v7a`, `x86` et `x86_64`.

## Notes

- La météo (Open-Meteo) et la récitation coranique nécessitent Internet ; les voix d'adhan et le texte du Coran sont hors ligne.
- Les contenus IPTV sont fournis par l'utilisateur ; l'application est uniquement un lecteur.
- Licences : Coran arabe et traduction Hamidullah (quran.com), voix d'adhan CC BY-SA / CC0, fonds d'écran Wikimedia Commons, police Tajawal (OFL).
