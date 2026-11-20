# KIKO TV Launcher

Launcher **Android TV en interface arabe RTL** avec IPTV/VLC, Coran, Adhan vidéo, horaires de prière, météo et fonds d’écran. Le lanceur cible le **Xiaomi Mi TV Stick 1re génération** (`MiTV-AESP0` / `MDZ-24-AA`, Android TV 9) et fonctionne aussi sur smartphone Android 9+ en paysage.

**Version actuelle : v4.0** (versionCode 32) · Package : `com.kiko.tvlauncher`

## Installation

1. Téléchargez **`KIKO-TV.apk`** depuis la section [Releases](https://github.com/KI-GEST/KIKO-TV-Launcher/releases) (dernière version : **4.0**).
2. Installez-le sur l’appareil :

```powershell
adb install -r KIKO-TV.apk
```

Si vous installez depuis le gestionnaire de fichiers de la TV ou du téléphone, autorisez l’installation depuis des sources inconnues. L’APK publié est la variante **ARM 32 bits (`armeabi-v7a`)**, signée avec la même clé que les versions précédentes : la mise à jour depuis l’application fonctionne donc sans désinstallation.

> L’application vérifie elle-même `releases/latest` au lancement et télécharge l’APK en interne, avec barre de progression et installation automatique. Les versions **2.1** à **2.9**, **3.0**, **3.1**, **3.2**, **3.3**, **3.4**, **3.5**, **3.6**, **3.7**, **3.8**, **3.9** et **4.0** sont conservées sur GitHub. Chaque release est immuable.

## Fonctionnalités

- **Accueil** : horloge et date configurables (24 h / 12 h, secondes, date grégorienne, hijri ou les deux), météo (Sfax par défaut), horaires de prière, mot du jour centré, message de pied et tuiles d’accès rapide. La navigation est une **ligne de libellés en bas de l’écran** ; une flèche permet de **masquer/réafficher toute la barre de menu**. Les chaînes favorites ne sont plus affichées sur l’accueil : elles sont accessibles uniquement depuis **« المفضلة »**, et les chaînes en direct sont exclues de « Continuer à regarder ». Orientation verrouillée en paysage.
- **IPTV** : interface native Compose arabe RTL avec onglets Chaînes / Films / Séries, recherche, catégories, lecteur intégré et plein écran sans coupure du flux. Sources **M3U URL**, **Xtream Codes** et **import local `.m3u`/`.m3u8`**, gérées depuis l’écran IPTV (profil), avec ajout, modification (`تعديل`), activation et synchronisation. Accès au stockage TV / smartphone : autorisation « Tous les fichiers » (Android 11+), sélecteur système SAF et liste automatique des playlists locales. La section « المصادر » a été retirée des Réglages.
- **Lecteur** : **VLC intégré** (`libvlc-all`) pour HLS/M3U8, avec repli automatique **ExoPlayer / Media3**. Le mode plein écran est réellement bord à bord sur TV et smartphone : aucun overscan, liseré, coin arrondi, barre de navigation ou bande d’encoche autour de la vidéo.
- **Musique & Radio** : annuaire **Radio Browser** (données du domaine public) avec stations (`Toutes`), `Genres`, `Pays`, recherche, pagination et radio par défaut **Mosaïque FM** résolue dynamiquement. Repli hors ligne par playlists M3U **CC0** de `radio-playlists`. Onglet **Jamendo** avec clé `client_id` saisie dans les réglages (jamais embarquée) et licence gratuite usage non commercial affichée. La **couverture de la station s’affiche au moment de la lecture** lorsque le favicon (ou le `tvg-logo` M3U) est disponible, avec repli sur une icône sinon. Aucune URL de flux n’est codée en dur.
- **Navigation télécommande** : champs de saisie, cartes et lignes de chaînes, vignettes de l’accueil, bandeau Chaînes / Films / Séries, catégories et profil IPTV, sources, chaque menu et sous-menu des réglages, boutons et lignes de sources affichent une **bordure dorée de 2 dp** lorsqu’ils reçoivent le focus. La bordure est dessinée par-dessus les vignettes pour rester visible partout. Le premier champ d’un formulaire est focalisé automatiquement.
- **Coran** : 114 sourates, texte Uthmani et traduction française, lecture verset par verset ou sourate entière, contrôles lecture / pause / stop / muet. Le bandeau jaune suit le verset en cours, y compris avec le réciteur Yasser Al-Dousri.
- **Adhan vidéo** : à **chaque heure de prière**, la vidéo « Adhan (Azan) — The Call to Prayer » est affichée en **plein écran avec son audio**. Le diaporama et la lecture audio séparée ont été supprimés. La vidéo 480p (14 Mo) est embarquée et copiée dans le stockage interne au premier lancement : **aucun réseau n’est nécessaire** à l’heure de la prière. L’écran propose **Arrêter** et **Rappel dans 5 min**, accessibles à la télécommande ; le bouton Retour arrête également l’adhan. La notification de premier plan propose les mêmes actions. Un bouton **« معاينة فيديو الأذان »** dans الإعدادات → إعدادات مواقيت الصلاة permet de tester la vidéo manuellement avec le son.
- **Voix d’adhan** : quatre voix embarquées, dont `adhan_voice4.mp3` (Assabile). Le réciteur choisi est mémorisé et sert à l’**aperçu manuel** dans l’onglet Adhan ; l’alarme, elle, joue la vidéo. Un rappel est affiché dans les réglages pour éviter toute confusion.
- **Widget adhan (smartphone uniquement)** : le widget « أذان كيكو » affiche la prochaine prière, son heure et la ville. Le bouton **▶** lit la voix d’adhan choisie **avec le son** (notification Arrêter, arrêt automatique en fin de lecture) ; un appui ailleurs ouvre l’application. Le widget est désactivé sur Android TV / Leanback.
- **Invocations et roqia** : 21 invocations en arabe et en français, dont deux avec audio embarqué ; les autres utilisent le moteur vocal arabe de l’appareil. La **roqia charia** reprend la source Al Jazeera : 21 éléments (5 versets avec récitation audio, 4 passages coraniques et 12 invocations prophétiques) avec texte arabe/français, références et repli vocal arabe.
- **Horaires de prière** : calcul local via `adhan-java`, méthode **Tunisie (18°/18° + 5 min au Maghreb, convention Yabiladi)** par défaut. Réglages : ville, méthode (12), madhab (Shafi / Hanafi) et ajustement de −60 à +60 minutes par prière.
- **Réglages** : sources IPTV, fond d’écran (+ import personnalisé), langue (ar / fr / en), ville, prière, voix de l’adhan (aperçu), date/heure, vérification des mises à jour et effacement des données.
- **Interface** : chiffres latins `0-9` partout, mise en page responsive TV / téléphone, thème marine et or, logo personnalisé. Le **fond d’écran choisi s’applique à toutes les pages et à tous les menus**.
- **Mise à jour sûre** : l’APK téléchargé depuis `releases/latest` n’est installé que si son empreinte **SHA-256** correspond à celle publiée dans les notes de release ; si l’empreinte manque ou diffère, l’installation est refusée (fail-closed).
- **Autorisations et veille** : demande guidée des alarmes exactes et des notifications, notification d’adhan avec actions Arrêter / Rappel, démarrage de l’adhan protégé sur Android 9+ et API 34+, et économiseur d’écran KIKO sur Android TV.

## Notes

- La météo (Open-Meteo) et la récitation coranique nécessitent une connexion Internet ; le Coran, les voix d’adhan et la vidéo d’adhan sont embarqués.
- Les contenus IPTV sont fournis par l’utilisateur : l’application est uniquement un lecteur et ne fournit aucun contenu.
- **Vidéo d’adhan** : source YouTube `QkptMypnTh8` (https://www.youtube.com/watch?v=QkptMypnTh8). Droits d’auteur **non vérifiés** : à remplacer par une vidéo libre avant toute redistribution. La voix `adhan_voice4.mp3` provient d’Assabile, licence du site non vérifiée.
- Licences connues : Coran arabe et traduction Hamidullah (quran.com), voix d’adhan CC BY-SA / CC0, fonds d’écran Wikimedia Commons, police Tajawal (OFL). Les audios de duas et de roqia viennent de Wikimedia Commons (Qunut PeaceSeekers CC0 ; récitations Aaqib Azeez CC0 / CC BY-SA 4.0). Les huit fonds « أذان TV » proviennent du projet [Azan - TV](https://www.behance.net/gallery/30268059/Azan-TV) de Mohamed Elbably et Eslam Ghazy (CC BY-NC-ND 4.0, intégrés avec l’accord des auteurs).

## Hashtags

#KIKOTV #KIKOLauncher #AndroidTV #IPTV #VLC #Xtream #Quran #Adhan #PrayerTimes #MiTVStick #XiaomiTVStick #AndroidTVLauncher #RTL #OpenSource #قرآن #أذان
