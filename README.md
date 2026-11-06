# WarLike MISC — Music Instrument School

Une application web d'apprentissage instrumental pour l'écosystème WarLike.

## Version 0.3 — académie, laboratoire et coach instrumental

- **Piano** : 2 octaves jouables au clic, au toucher ou au clavier, timbres synthétiques Web Audio.
- **Guitare** : manche jouable en accordage standard E A D G B E, de la corde à vide à la 12e case.
- **6 leçons** : séquences de notes vérifiées sur l'instrument virtuel ; progression enregistrée en local.
- **Accordeur** : détection de hauteur monophonique par autocorrélation via microphone, indication en cents.
- **Métronome** : 40–220 BPM, mesures 2/4, 3/4, 4/4, accent sur le premier temps.
- **Interface responsive** : ordinateur et mobile, sans dépendance externe.

## Nouveau : laboratoire musical (`practice.html`)

- **Explorateur de gammes** : majeure, mineure naturelle et pentatonique mineure, 12 tonalités.
- **Explorateur d'accords** : majeur, mineur, dominante 7, majeur 7, mineur 7, écoute séquentielle ou simultanée.
- **Entraînement de l'oreille** : reconnaissance de notes naturelles ou chromatiques, score et précision en local.
- **Précision rythmique** : exercice avec clics à 60–140 BPM, touches ou écran tactile, mesure de l'erreur moyenne en millisecondes.
- Accès depuis le menu de `index.html` ; aucune bibliothèque externe requise.

## Nouveau : coach instrumental (`coach.html`)

- **7 exercices de notes** : premiers pas au piano, gamme et arpège, cordes de guitare, gamme de Mi mineur, basse et chromatisme.
- **Microphone** : analyse monophonique en local par différence normalisée de type YIN, estimation de note, cents et indication de justesse.
- **Clavier MIDI** : accès Web MIDI sur navigateur compatible, sélection du port et lecture des messages note-on.
- **Évaluation** : comparaison de la suite attendue, progression et erreurs, sauvegarde des exercices terminés sur l'appareil.
- **Démonstration** : les exercices peuvent être testés sans instrument avec un bouton de note virtuelle.
- **Confidentialité** : le flux audio n'est pas envoyé au serveur ; le navigateur demande les autorisations d'accès.

### Limites du coach

- La détection par microphone est expérimentale et monophonique ; le bruit et les harmoniques peuvent donner des notes erronées.
- L'écoute ne vérifie pas encore les accords complets, les attaques, les nuances, la posture, ni le tempo de chaque note.
- Un instrument MIDI doit être relié à un navigateur qui supporte Web MIDI.
- Le coach ne prétend pas remplacer un professeur : la notation reste limitée à la justesse et l'ordre des notes.
- Les notes basses, particulièrement la corde Mi1 de basse (41,2 Hz), ne sont pas couvertes par la plage actuelle du microphone ; utiliser MIDI pour cet exercice.

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
