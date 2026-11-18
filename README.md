# KIKO TV Launcher

Launcher **Android TV en interface arabe RTL** avec IPTV/VLC, Coran, Adhan, horaires de prière, météo et fonds d’écran. Le lanceur cible le **Xiaomi Mi TV Stick 1re génération** (`MiTV-AESP0` / `MDZ-24-AA`, Android TV 9) et fonctionne aussi sur smartphone Android 9+ en paysage.

**Version actuelle : v2.3** (versionCode 15) · Package : `com.kiko.tvlauncher`

## Installation

1. Téléchargez **`KIKO-TV.apk`** depuis la section [Releases](https://github.com/KI-GEST/KIKO-TV-Launcher/releases) (dernière version : **v2.3**).
2. Installez-le sur l’appareil :

```powershell
adb install -r KIKO-TV.apk
```

Si vous installez depuis le gestionnaire de fichiers de la TV ou du téléphone, autorisez l’installation depuis des sources inconnues. L’APK publié est la variante **ARM 32 bits (`armeabi-v7a`)**, signée avec la même clé debug que les versions précédentes : la mise à jour depuis l’application fonctionne donc sans désinstallation.

> L’application vérifie elle-même `releases/latest` au lancement et télécharge l’APK en interne, avec barre de progression et installation automatique. Seules les versions **v2.1**, **v2.2** et **v2.3** sont conservées sur GitHub.

## Fonctionnalités

- **Accueil** : horloge et date configurables (24 h / 12 h, secondes, date grégorienne, hijri ou les deux), météo (Sfax par défaut), horaires de prière, message de pied et tuiles d’accès rapide. Sur Android TV, la barre latérale est conservée ; la section « derniers ajouts » a été supprimée. Sur smartphone, une barre de navigation basse remplace la barre latérale et les barres système sont masquées. L’orientation est verrouillée en paysage.
- **IPTV** : catalogue Direct / Films / Séries / Favoris. Sources **M3U** et **Xtream Codes**. La liste publique **iptv-org** (`https://iptv-org.github.io/iptv/index.m3u`) est ajoutée automatiquement au premier lancement et lors des mises à jour, avec un bouton d’ajout rapide dans Réglages → مصادر IPTV.
- **Lecteur** : **VLC intégré** (`libvlc-all`) pour HLS/M3U8, avec repli automatique **ExoPlayer / Media3**.
- **Coran** : 114 sourates, texte Uthmani et traduction française, lecture verset par verset ou sourate entière, contrôles lecture / pause / stop / muet. Le bandeau jaune suit le verset en cours, y compris avec le réciteur Yasser Al-Dousri.
- **Adhan et invocations** : trois voix d’adhan embarquées ; le réciteur choisi est mémorisé et utilisé automatiquement quand l’alarme de prière sonne. 21 invocations en arabe et en français.
- **Horaires de prière** : calcul local via `adhan-java`, méthode **Tunisie (18°/18° + 5 min au Maghreb, convention Yabiladi)** par défaut. Réglages : ville, méthode (12), madhab (Shafi / Hanafi) et ajustement de −60 à +60 minutes par prière.
- **Réglages** : sources IPTV, fond d’écran (+ import personnalisé), langue (ar / fr / en), ville, prière, voix de l’adhan, date/heure, vérification des mises à jour et effacement des données.
- **Interface** : chiffres latins `0-9` partout, mise en page responsive TV / téléphone, thème marine et or, logo personnalisé.
- **Mise à jour sûre** : l’APK téléchargé depuis `releases/latest` n’est installé que si son empreinte **SHA-256** correspond à celle publiée dans les notes de release (vérification stricte).
- **Autorisations et veille** : demande guidée des alarmes exactes et des notifications, notification d’adhan avec actions Arrêter / Rappel dans 5 min, et économiseur d’écran KIKO sur Android TV.

## Notes

- La météo (Open-Meteo) et la récitation coranique nécessitent une connexion Internet ; les voix d’adhan et le texte du Coran sont embarqués.
- Les contenus IPTV sont fournis par l’utilisateur : l’application est uniquement un lecteur et ne fournit aucun contenu.
- Licences : Coran arabe et traduction Hamidullah (quran.com), voix d’adhan CC BY-SA / CC0, fonds d’écran Wikimedia Commons, police Tajawal (OFL).

## Hashtags

#KIKOTV #KIKOLauncher #AndroidTV #IPTV #VLC #Quran #Adhan #PrayerTimes #MiTVStick #XiaomiTVStick #AndroidTVLauncher #RTL #OpenSource #قرآن #أذان
