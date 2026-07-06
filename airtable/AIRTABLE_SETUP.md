# Prototype Airtable — RHY

Ce kit te permet de créer la base Airtable en 5 minutes, **déjà remplie avec tes 11 projets**. Le site actuel continue de tourner pendant ce temps — rien n'est cassé.

## Fichiers fournis
- `airtable_projets.csv` — les 11 projets (titres, textes EN/ES, catégories, années, et **liens** vers tes photos/vidéos actuelles).
- `airtable_infos_site.csv` — les coordonnées, la bio et les disciplines.

## Étape 1 — Créer le compte + la base
1. Va sur **airtable.com** → crée un compte gratuit.
2. Clique **Create → Base → Import data → CSV file**.
3. Importe **`airtable_projets.csv`** → ça crée une table « Projets » avec tes 11 lignes.
4. Refais **Add table → Import → CSV** avec **`airtable_infos_site.csv`** → table « Infos site ».

## Étape 2 — Régler les types de colonnes (Projets)
Airtable devine la plupart des types. Ajuste seulement :
- **category** → type *Single select* (options : stage, screen, studio).
- **color** → type *Checkbox*.
- **desc_en / desc_es / bio…** → type *Long text*.
- **card_media / hero_media / card_poster / hero_poster / gallery** → voir étape 3.

## Étape 3 — Les médias (le point important)
Deux options :

**A. Rester en liens (le plus simple pour démarrer).**
Laisse ces colonnes en texte : elles contiennent déjà les URLs de tes médias actuels. Le site sait les lire tels quels.

**B. Passer en vraies pièces jointes (recommandé à terme).**
Change ces colonnes en type **Attachment**. Ensuite, pour chaque projet, tu **glisses-déposes** la photo/vidéo directement dans la cellule. C'est **là que disparaît le problème d'upload** : Airtable héberge le fichier de façon fiable, aucune vidéo tronquée, aucun 404. Tu peux uploader depuis l'ordi **ou le téléphone** (appli Airtable).

> Astuce : commence en mode A pour voir le site marcher avec Airtable, puis bascule les médias en mode B tranquillement.

## Étape 4 — Me redonner l'accès en lecture
Une fois la base prête, il me faut deux infos pour brancher le site :
1. L'**ID de la base** (dans l'URL Airtable, commence par `app…`).
2. Un **token de lecture** Airtable (Account → Builder hub → Personal access tokens → scope *data.records:read* sur cette base).

Tu me les donnes **dans l'admin/en privé, pas ici**, et je câble la synchro : Airtable → le site se met à jour tout seul. Les visiteurs liront une copie statique (donc **zéro appel API** compté, le plan gratuit suffit).

## Ce que ça change pour Guadalupe
- Elle édite un **tableau familier** (ou l'appli mobile), glisse ses médias, coche « couleur » si besoin.
- **Plus de GitHub, plus de token GitHub, plus d'uploads qui échouent.**
- Le site reste **gratuit**.
