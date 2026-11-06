# WarLike MISC — Music Instrument School

Une application web d'apprentissage instrumental pour l'écosystème WarLike.

## Version 0.1 — prototype interactif

- **Piano** : 2 octaves jouables au clic, au toucher ou au clavier, timbres synthétiques Web Audio.
- **Guitare** : manche jouable en accordage standard E A D G B E, de la corde à vide à la 12e case.
- **6 leçons** : séquences de notes vérifiées sur l'instrument virtuel ; progression enregistrée en local.
- **Accordeur** : détection de hauteur monophonique par autocorrélation via microphone, indication en cents.
- **Métronome** : 40–220 BPM, mesures 2/4, 3/4, 4/4, accent sur le premier temps.
- **Interface responsive** : ordinateur et mobile, sans dépendance externe.

## Démarrer

Ouvrir `index.html` dans un navigateur moderne. Le piano, la guitare et le métronome fonctionnent en local. Pour le microphone, servir le projet en **HTTPS** ou sur `localhost`.

Exemple avec Python :

```bash
python -m http.server 8000
```

Puis ouvrir http://localhost:8000.

## Déploiement Cloudflare Pages

Connecter ce dépôt à Cloudflare Pages. Aucun build requis : choisir **aucune commande de build** et le répertoire de sortie **/** (racine du projet), ou utiliser un déploiement statique direct.

## Limites connues

- L'accordeur identifie une seule note à la fois, pas les accords complets.
- Les sons piano/guitare sont des oscillateurs de synthèse : ce ne sont pas encore des instruments échantillonnés réalistes.
- Les exercices utilisent les clics et touches sur l'instrument virtuel ; le microphone n'évalue pas encore la performance des leçons.
- Les données de progression restent dans le navigateur via `localStorage` et ne sont pas synchronisées entre appareils.
- Pas encore de connexion WarLike Hub / Studio, de serveur, ni d'export MIDI.

## Feuille de route

1. Sons d'instruments authentiques et gestion des enveloppes ADSR.
2. Exercices structurés par instrument, accords, partitions et tablatures.
3. Évaluation microphone/MIDI des exercices adaptés.
4. Comptes, sauvegarde cloud, statistiques et intégration Hub.
5. Connexion WarLike Studio (MIDI / projets).
6. Batterie, basse et parcours avancés.

## Licence

Aucune licence explicite ajoutée à ce stade. © WarLike — Tous droits réservés, sauf indication contraire.
