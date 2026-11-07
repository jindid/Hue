# Hue Music Sync 🎶💡

Une petite application web (installable sur Android) qui fait bouger tes lumières **Philips Hue** au rythme de la musique : **YouTube Music**, Deezer, la radio… tout ce qui sort d'une enceinte.

L'application Hue ne propose la synchro musicale qu'avec Spotify. Celle-ci écoute le son, détecte les **basses**, les **médiums**, les **aigus** et les **beats**, puis envoie les couleurs au pont Hue directement sur ton Wi-Fi. Rien ne passe par Internet.

## Fonctionnalités
- **4 effets** : Pulsation, Spectre (basses, médiums, aigus répartis sur les lampes), Flash, Vague
- **6 palettes** : Néon, Coucher de soleil, Océan, Feu, Forêt, Arc-en-ciel
- Réglages : sensibilité, luminosité min et max, vitesse, débit, fluidité
- Choix de la pièce ou de la zone et des lampes
- Estimation du BPM, aperçu des ampoules à l'écran, **mode démo** sans pont
- Remet les lampes comme avant quand on arrête
- Sources : **micro** (Android et PC) ou **son d'un onglet** (Chrome ou Edge sur PC : capte YouTube Music sans micro)

## Mise en ligne (une seule fois)
1. Sur GitHub : **Settings → Pages → Build and deployment → Source : GitHub Actions**.
2. Le workflow `.github/workflows/pages.yml` publie l'appli à chaque push. L'adresse sera du type `https://<ton-pseudo>.github.io/Hue/`.
   (Sur un compte gratuit, GitHub Pages demande un dépôt **public**.)

## Utilisation sur Android
1. Ouvre l'adresse de l'appli dans **Chrome**, sur le même Wi-Fi que le pont. Tu peux faire « Ajouter à l'écran d'accueil ».
2. Appuie sur **Rechercher** pour trouver l'IP du pont, ou saisis-la (appli Hue → Paramètres → Ponts Hue → ⓘ).
3. **Une seule fois :** ouvre le lien `https://IP-du-pont` et accepte le certificat (« Paramètres avancés » → « Continuer »). Le pont utilise un certificat que Chrome ne connaît pas.
4. Appuie sur le **bouton rond du pont**, puis sur **Connecter**. Si Chrome demande l'accès au réseau local, accepte.
5. Choisis tes lampes, un effet et une palette, puis **▶ Lancer la synchro**. Lance ta musique dans YouTube Music.

### Conseils
- Avec le micro, le mieux est de diffuser la musique sur une enceinte (Bluetooth, Chromecast…) et de poser le téléphone à côté.
- Garde l'écran allumé : l'appli essaie d'empêcher la mise en veille.
- 2 à 6 lampes couleur, c'est l'idéal. Le pont Hue n'accepte qu'environ 10 à 20 ordres par seconde au total. Le réglage se trouve dans les réglages avancés.
- Si ça réagit trop ou pas assez, ajuste la **sensibilité**.

## Tester en local
```bash
python3 -m http.server 8000
# puis ouvrir http://localhost:8000 (le micro fonctionne sur localhost)
```
