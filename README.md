# evoX RSS News

![evoX RSS News Banner](assets/evox-rss_banner.jpg)

<p align="center">
  <img src="assets/evox-rss_logo.jpg" alt="evoX RSS Logo" width="120">
</p>

<p align="center">
  <b>Un agrégateur de flux RSS / Atom dédié à l'écosystème PS5, léger, réactif et sans dépendance serveur.</b>
</p>

<p align="center">
  <a href="https://nexgen999.github.io/evoX-RSS/">🌐 Accéder à la WebApp</a>
</p>

---

## 🚀 Présentation

**evoX RSS News** est un tableau de bord moderne conçu pour suivre en temps réel les dernières releases et mises à jour des projets majeurs de la scène PS5 (payloads, loaders, outils DNS, émulateurs, etc.). 

Développé en HTML/CSS/JS natif, l'application fonctionne entièrement côté client sans nécessiter d'installation ni de backend complexe.

---

## ⚡ Méthode de Récupération & Compatibilité

Pour contourner les contraintes d'API et garantir une disponibilité maximale, l'application utilise une approche hybride robuste :

* **Méthode utilisée** : Conversion des flux natifs GitHub Atom (/releases.atom) en JSON via le service intermédiaire public api.rss2json.com.
* **Pas de limite stricte d'API** : Contrairement à l'API REST de GitHub qui bloque les requêtes non authentifiées à 60 requêtes/heure (erreur HTTP 403), cette méthode permet d'interroger des dizaines de dépôts simultanément sans clé API.
* **Compatibilité des flux** :
  * **Excellente** : Tous les dépôts GitHub publics générant des Releases ou des Tags.
  * **Standard RSS/Atom** : Support des flux Atom traditionnels et flux RSS 2.0.

---

## 🛠️ Guide de Configuration

Toute la configuration des sources se trouve dans la constante CATEGORIES du fichier index.html.

### 1. Structure d'une Catégorie

Une catégorie regroupe plusieurs flux sous un même thème et possède son propre icône :

{ 
    name: "Nom de la Catégorie",
    icon8: "https://img.icons8.com/fluency/96/votre-icone.png",
    feeds: [
        // Liste des flux ici
    ] 
}

### 2. Ajouter un Nouveau Flux

Pour ajouter un projet GitHub à une catégorie existante, insérez un objet dans le tableau feeds :

{ name: "NomDuProjet", url: "https://github.com/Utilisateur/NomDuDepot" }

### 3. Ajouter une Nouvelle Catégorie

Ajoutez simplement un nouveau bloc dans le tableau CATEGORIES :

{ 
    name: "PS5 Tools",
    icon8: "https://img.icons8.com/fluency/96/wrench.png",
    feeds: [
        { name: "Outil-1", url: "https://github.com/auteur/outil-1" },
        { name: "Outil-2", url: "https://github.com/auteur/outil-2" }
    ] 
}

### 🎨 Gestion des Icônes

L'application utilise les icônes de la librairie Icons8 pour maintenir un visuel propre et uniforme.

* **Icônes de catégorie (icon8)** : Utilisez des liens d'images directs au format PNG ou SVG (idéalement en résolution 48x48 ou 96x96 px).
* **Icônes de plateforme (PLATFORM_ICONS8)** : L'affichage gère automatiquement les badges de plateforme selon l'origine du lien.

---

## 👥 Crédits & Contributeurs

* **nexgen999** — Développeur principal & Concepteur de l'écosystème (@nexgen999)

---

<p align="center">
  <i>evoX WebUI Manager · PS5 Edition</i>
</p>
