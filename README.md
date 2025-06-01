
# 📦 Suivi de colis DHL - Application Web avec Supabase

Une application web simple et légère pour le **suivi de colis DHL**, avec :
- Ajout d’expéditions 📤
- Affichage des trajets 🛣️
- Mise à jour des données 🔁
- Connexion directe à **Supabase** (sans backend)

---

## 🌐 Technologies utilisées

- **HTML / CSS** (pas de framework, pur et léger)
- **JavaScript (ES6)**
- **[Supabase](https://supabase.com)** pour :
  - Base de données (`expeditions`)
  - Stockage des photos (bucket `colis`)

---

## 📁 Fichiers principaux

| Fichier             | Rôle |
|---------------------|------|
| `index.html`        | Page d’accueil + vérification de code |
| `suivi.html`        | Affiche les infos d’un colis |
| `expedition.html`   | Formulaire pour ajouter un colis |
| `admin.html`        | Tableau admin pour tout modifier |

---

## ✅ Fonctionnalités

- Recherche d’un colis par **code de suivi**
- Affichage des **étapes du trajet**
- Ajout d’un colis avec :
  - nom de l’expéditeur
  - destinataire
  - adresse
  - dates (envoi / arrivée)
  - **photos** (uploadées dans Supabase)
- 🔒 Accès admin avec mot de passe (`91158846`)
- ✅ Message vert affiché après enregistrement réussi

---

## 🧰 Configuration Supabase (déjà faite ✅)

Tu dois avoir dans Supabase :

### 1. Table : `expeditions`

| Colonne        | Type     |
|----------------|----------|
| `code`         | `text` (Primary Key) |
| `expediteur`   | `text` |
| `destinataire` | `text` |
| `adresse`      | `text` |
| `colis`        | `text` |
| `date_envoi`   | `timestamp` |
| `date_arrivee` | `timestamp` |
| `trajet`       | `text` |
| `photos`       | `text[]` |

### 2. Bucket `colis` (public) dans **Supabase Storage**

- Pour enregistrer les photos des expéditions
- Nom exact : `colis`

### 3. RLS activé + policies :

```sql
-- Lecture
CREATE POLICY acces_public_select
ON expeditions FOR SELECT TO public USING (true);

-- Insertion
CREATE POLICY acces_public_insert
ON expeditions FOR INSERT TO public WITH CHECK (true);

-- Mise à jour
CREATE POLICY acces_public_update
ON expeditions FOR UPDATE TO public USING (true);
```

---

## 🚀 Tester ou publier

### 🔄 Tester en local
1. Ouvre le fichier `index.html` dans ton navigateur
2. Teste les formulaires et fonctions Supabase

### 🌍 Tester en ligne rapidement
- Va sur [https://drop.netlify.com](https://drop.netlify.com)
- Glisse le dossier `.zip` contenant tous les fichiers
- Tu obtiens un lien en ligne immédiatement

---

## 🔐 Accès admin
Un mot de passe simple est demandé pour accéder à `admin.html` et `expedition.html` :
```
91158846
```

> 💡 Tu peux le modifier dans le code si besoin.

---

## 👨‍💻 Développé par :
Ton Nom / Ton Projet  
Version : 1.0  
Date : 2025
