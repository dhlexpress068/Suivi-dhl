
# Suivi DHL – Application Web

Ce projet est un mini-système de suivi d'expédition DHL connecté à Supabase.

## 📁 Contenu des pages

### 1. `index.html`
- Page d'accueil avec champ de recherche
- Redirige vers `suivi.html?code=...`

### 2. `expedition.html`
- Formulaire pour créer une nouvelle expédition
- Upload d'images vers Supabase (bucket `colis`)
- Enregistrement dans la table `expeditions`
- Affiche un message ✅ de confirmation

### 3. `suivi.html`
- Récupère une expédition via le code dans l'URL
- Affiche toutes les informations + photos associées
- Galerie photo intégrée avec flexbox

### 4. `admin.html`
- Liste et édition des expéditions
- Filtrage par code de suivi
- Enregistrement des modifications
- Accès protégé par `prompt("91158846")`

## 🔗 Supabase
- Base de données : `expeditions`
- Bucket de stockage : `colis`
- Clé publique (anon) : intégrée dans les fichiers
- URL de base : `https://lyzovuebqyomvffqekca.supabase.co`

## 🚀 Déploiement GitHub Pages
1. Aller sur [https://github.com](https://github.com)
2. Créer un dépôt public
3. Uploader tous les fichiers HTML + README + `supabase.min.js`
4. Activer GitHub Pages via `Settings > Pages`
5. Choisir la branche `main` + dossier `/root`

## ✅ Recommandations
- Toujours utiliser HTTPS
- Tester depuis un hébergement (GitHub Pages, Netlify, etc.)
- Ne pas partager la clé Supabase si vous passez en mode sécurisé

---
© DHL Express — Suivi logistique personnalisé.
