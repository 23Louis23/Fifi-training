# Fifi Training App

App de suivi pour le programme Push / Pull / Legs de Fifi. Elle utilise la **même base de données Supabase** que l'app de Jox (voir `Jox/jox-training-app/`) — pas besoin de recréer un compte ou un projet.

## Particularité par rapport à l'app de Jox

Le programme de Fifi n'a pas de semaines fixes : c'est une rotation Push → Pull → Legs qui se répète. Chaque séance enregistrée crée donc une nouvelle entrée **datée** dans l'historique (au lieu d'écraser une "semaine"), pour suivre sa progression de charge dans le temps. Les charges par défaut affichées à l'ouverture d'une séance sont celles de sa dernière séance de ce type.

## 1. Base de données

✅ Déjà faite — cette app utilise le même projet Supabase que Jox, avec en plus une colonne `athlete` qui sépare ses données de celles des autres athlètes.

Si ce n'est pas encore fait : exécute `Jox/jox-training-app/migration_multi_athlete.sql` une fois dans le SQL Editor de Supabase (Dashboard > SQL Editor > New query > coller > Run) pour ajouter cette colonne à la table existante.

## 2. Configurer l'appli

✅ Déjà fait — `index.html` contient l'URL et la clé Supabase (les mêmes que pour Jox), et un code d'accès (`1357` par défaut, modifiable en cherchant `APP_PIN` dans le fichier).

## 3. Déployer sur Vercel (gratuit) — sans rien installer

Même procédure que pour Jox :

1. Crée un nouveau repo GitHub (ex: `fifi-training-app`).
2. Upload les 2 fichiers (`index.html`, `README.md`) via "uploading an existing file" sur la page du repo.
3. Va sur [vercel.com/new](https://vercel.com/new), importe ce nouveau repo, déploie avec les réglages par défaut.
4. Récupère l'URL propre du projet (ex: `https://fifi-training-app.vercel.app`, pas l'URL avec un hash aléatoire) dans la section "Domains" du projet.

## 4. Utilisation

Envoie l'URL + le code `1357` à Fifi. Toi, tu ouvres la même URL sur ton ordinateur avec le même code pour suivre ses séances et sa progression.
