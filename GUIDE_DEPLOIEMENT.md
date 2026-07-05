# Guide de déploiement — Site RHY (Guadalupe Sánchez)

Objectif : mettre le site en ligne **gratuitement**, avec un **nom de domaine perso**, et un **espace admin** où Guadalupe édite ses infos/photos/vidéos sans toucher au code.

Architecture : site statique (`index.html`) → hébergé sur **Netlify** → connecté à **GitHub** → **Sveltia CMS** pour l'édition. À chaque modification, Netlify redéploie tout seul.

---

## Étape 1 — Pousser le code sur GitHub

Le dépôt local est déjà prêt (premier commit fait). Depuis ton terminal :

```bash
cd ~/Documents/Rhyllow
git branch -M main
# Option A — avec GitHub CLI :
gh repo create rhyllow-site --public --source=. --remote=origin --push
# Option B — à la main : crée un dépôt vide "rhyllow-site" sur github.com, puis :
git remote add origin https://github.com/TON-USER/rhyllow-site.git
git push -u origin main
```

➡️ Note le chemin exact du dépôt, ex. `guada/rhyllow-site` (format `OWNER/REPO`).

---

## Étape 2 — Déployer sur Netlify

1. Va sur **app.netlify.com** → connecte-toi **avec GitHub** (gratuit).
2. **Add new site → Import an existing project → GitHub → rhyllow-site**.
3. Réglages de build : **laisse tout vide** (site statique).
   - Build command : *(vide)*
   - Publish directory : `.` (la racine)
4. **Deploy**. En ~30 s le site est en ligne sur une adresse type `rhyllow-site.netlify.app`.

À partir de là, **chaque `git push` (ou chaque publication via l'admin) redéploie automatiquement.**

---

## Étape 3 — Nom de domaine personnalisé

L'hébergement + le HTTPS sont gratuits ; seul **le nom de domaine** s'achète (~10–15 €/an chez un registrar : Namecheap, OVH, Porkbun…).

1. Achète le domaine voulu (ex. `rhyllow.com` ou `rhyllow.dance`).
2. Dans Netlify : **Site settings → Domain management → Add a domain** → saisis ton domaine.
3. Netlify te donne soit des **serveurs DNS** (à mettre chez le registrar), soit des **enregistrements** (A / CNAME). Applique-les côté registrar.
4. Le certificat HTTPS (Let's Encrypt) s'active tout seul en quelques minutes.

> En attendant l'achat, l'adresse `*.netlify.app` fonctionne déjà parfaitement pour envoyer aux scouts.

---

## Étape 4 — Activer l'espace admin (Sveltia CMS)

### 4.1 Renseigner le dépôt
Dans `admin/config.yml`, remplace la ligne :
```yaml
repo: OWNER/REPO        # → ex : repo: guada/rhyllow-site
```
(puis `git push` — ou je le fais pour toi dès que tu me donnes le nom exact.)

### 4.2 Connexion — méthode simple (recommandée pour une seule éditrice)
Sveltia permet la connexion **par token**, sans app OAuth ni serveur :

1. Guadalupe va sur GitHub → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate**.
2. **Repository access** : *Only select repositories* → `rhyllow-site`.
3. **Permissions → Repository → Contents : Read and write**. Génère le token, copie-le.
4. Elle ouvre **`ton-domaine.com/admin`** → bouton **« Sign in with Token »** → colle le token. Voilà.

> Le token est comme un mot de passe : à ne pas partager. On peut lui mettre une date d'expiration et le régénérer.

### 4.3 Alternative — connexion « Login with GitHub » (plus fluide, un peu plus de setup)
Si tu préfères un vrai bouton « Login with GitHub » : on configure le **fournisseur OAuth GitHub dans Netlify** (Site settings → Access control → OAuth → Install provider GitHub, avec une OAuth App GitHub). Dis-le-moi et je te guide pas à pas.

---

## Étape 5 — Comment Guadalupe édite ensuite

1. Elle va sur `ton-domaine.com/admin` et se connecte.
2. Elle édite : **Infos & coordonnées** (email, Instagram, bio…), **Galerie** (ajoute/retire photos & vidéos), **Projets** (pages « See more »).
3. Elle clique **Publish** → Sveltia commit sur GitHub → Netlify redéploie → le site est à jour en ~1 min.

---

## ⚠️ Important — une dernière étape technique (Phase 2)

Aujourd'hui, les textes et médias de `index.html` sont **écrits dans le code** (rapide, robuste). L'admin sait **stocker** les contenus, mais pour que les modifications faites dans l'admin **s'affichent automatiquement** sur le site, il faut **brancher `index.html` sur les fichiers de contenu** (le site lit `content/*.json` au lieu d'avoir les données en dur).

C'est une évolution que je peux faire quand tu veux : le site devient alors **100 % éditable** par Guadalupe sans une ligne de code. Dis-moi « on fait la Phase 2 » et je m'en occupe.

---

### Récap coûts
| Élément | Coût |
|---|---|
| Hébergement Netlify | Gratuit |
| HTTPS / certificat | Gratuit |
| Sveltia CMS (admin) | Gratuit |
| Nom de domaine | ~10–15 €/an (seul poste payant) |
