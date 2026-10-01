<p align="center">
  <img src="/doc/images/example.png" alt="Exemple d'affichage" width="400"/>
</p>

# 🏉 **Rugby TV Game Card** 📺
[![PayPal](https://img.shields.io/badge/paypal-me-blue.svg?style=for-the-badge&color=purple&logo=paypal&logoColor=ccc&link=https%3A%2F%2Fpaypal.me%2hlaissus/5)](https://paypal.me/hlaissus/5)
[![GitHub Release]( https://img.shields.io/github/v/release/developpeurbox/hass-rugby-tv?style=for-the-badge&color=blue)](https://github.com/developpeurbox/hass-rugby-tv-game-card/releases)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge&color=blue)](https://github.com/hacs/integration)
[![Community Forum]( https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge&color=pink)](https://forum.hacf.fr/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)](https://github.com/developpeurbox/hass-rugby-tv-game-card/blob/main/LICENSE)

[![HACS Action](https://github.com/developpeurbox/ha-rugby-tv-game-card/actions/workflows/hacs.yml/badge.svg?style=for-the-badge)](https://github.com/developpeurbox/ha-rugby-tv-game-card/actions/workflows/hacs.yml)  

**Carte Lovelace personnalisée pour afficher les matchs Rugby TV** avec les logos des équipes, la ou les chaînes TV et l'heure du coup d'envoi.

🔗 **Pour la création des capteurs (sensors)**, consultez [ce dépôt](https://github.com/developpeurbox/hass-rugby-tv).

---

## 📦 Installation

> [!TIP]
> ### Installation Rapide via HACS
> Cliquez sur le bouton ci-dessous pour ajouter automatiquement le dépôt dans HACS :
>
> [![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=developpeurbox&repository=ha-rubgy-tv-game-card&category=dashboard)

### 🏗️ Méthode 1 : HACS (Recommandée)

   1. Ouvrez **HACS** dans Home Assistant
   2. Allez dans **Intégrations**
   3. Cliquez sur les **3 points** en haut à droite → **Dépôts personnalisés**
   4. Ajouter: [https://github.com/developpeurbox/hass-footao.git](https://github.com/developpeurbox/ha-rubgy-tv-game-card)
   5. Catégorie **Tableau de bord**
   6. Cherchez "**Rubgy TV Card**" et cliquez sur **Télécharger**


### 🏗️ Méthode 2 : Manuelle
  1. Téléchargez le fichier depuis [les releases](https://github.com/developpeurbox/ha-rubgy-tv-game-card/releases).
  2. Placez-le dans le dossier `/config/www/`.


## 🎨 Carte `rugby-tv-game-card`

Ajoutez simplement ce code dans votre configuration:

```yaml
type: custom:rugby-tv-game-card
entity: sensor.rugby_toulouse
footer_bg: "rgba(0,0,0,0.6)"
footer_color: "#e63946"
```

Pour afficher tous vos matchs :

```yaml
type: custom:auto-entities
card:
  type: entities
filter:
  include:
    - options:
        type: custom:rugby-tv-game-card
      entity_id: sensor.rugby_*
      sort:
        method: attribute
        attribute: datetime
```
<p align="center">
  <img src="/doc/images/all.png" alt="Tous les matchs" width="400"/>
</p>


### 🎨 Personnalisation

Vous pouvez désormais personnaliser l'apparence du pied de page (*footer*) directement via les options de la carte :

* **Arrière-plan :** Modifiez `footer_bg` (accepte les formats **HEX**, **RGB** ou **RGBA**).
* **Couleur du texte :** Ajustez `footer_color` pour assurer une visibilité optimale selon votre fond

---
## 📭 **Aucun match prévu**

Lorsque aucun match n'est trouvé pour l'équipe configurée (match passé ou calendrier vide), la carte affiche automatiquement un état simplifié : le logo de l'équipe, son nom, et un message d'information.
<p align="center">
  <img src="/doc/images/no_game.png" alt="Affichage sans match prév" width="400"/>
</p>

> **Aucun match prévu prochainement** s'affiche à la place des informations de diffusion habituelles. Dès qu'un prochain match est disponible dans le capteur, la carte reprend son affichage normal automatiquement.

---
## 💬 **Communauté & Support**
🗣️ **Forum Home Assistant** : [Discuter ici](https://forum.hacf.fr/t/carte-lovelace-integration-rugby-tv-le-programme-tv-arrive-dans-home-assistant/84193)

---
