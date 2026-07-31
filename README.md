# Pristivia — Site de Mariage (Priscile & Steve)

Site vitrine statique présentant le mariage de **Priscile & Steve**, célébré le **10 octobre 2026 à Douala, Cameroun**, avec un thème élégant « Bantou » (marron, kaki, ivoire, vert).

Construit en HTML / CSS / JavaScript pur, sans framework ni backend. Déployable sur n'importe quel hébergeur statique (GitHub Pages, Netlify, Vercel…).

## Fonctionnalités

- **Compte à rebours** en direct jusqu'au jour J
- **Présentation des familles** des mariés
- **Notre Histoire** avec carrousel de photos automatique
- **Dress Code** : palette de couleurs + galerie photos
- **Programme** de la journée (mairie & réception) avec liens Google Maps
- **Wishlist** : 3 fonds de contribution avec coordonnées MoMo / Orange Money dans une modale
- **RSVP** : formulaire de confirmation de présence, envoyé directement vers un Google Form
- **Musique d'ambiance** : lecture automatique au chargement (avec bouton de contrôle)
- Design **responsive**, animations AOS, menu mobile

## Structure du projet

```
.
├── index.html          # Site complet (mono-page)
├── assets/             # Images et musique
│   ├── pristiv*.png        # Photos du carrousel
│   ├── exemple*.jpeg       # Photos de la galerie
│   ├── wl*.jpeg            # Images des cartes wishlist
│   └── background-music.mp3
└── ref/                # Images de référence (design)
```

## Lancer en local

Aucune installation requise. Ouvrez simplement le fichier dans un navigateur :

```bash
open index.html
```

Ou servez le dossier avec un serveur statique :

```bash
python3 -m http.server 8000
```

## RSVP — Google Form

Le formulaire de réservation envoie les réponses à un Google Form via un POST `no-cors` vers l'endpoint `formResponse` (aucun backend requis).

Champs configurés dans `handleRSVP()` (`index.html`) :

| Champ du site    | Champ Google Form                |
|------------------|----------------------------------|
| Nom complet      | `entry.1164693840`               |
| Téléphone        | `entry.1301941973`               |
| Présence         | `entry.1130436840`               |

Pour utiliser un autre Google Form : remplacez l'ID du formulaire dans l'URL de `fetch()` et mettez à jour les identifiants `entry.*` (visibles dans la structure `FB_PUBLIC_LOAD_DATA_` de la page du formulaire).

## Personnalisation

Les couleurs et polices sont définies dans `tailwind.config` et le bloc `<style>` en tête de `index.html`. Le contenu (familles, histoire, programme, coordonnées de paiement) se modifie directement dans le HTML.

## Licence

Projet personnel. Tous droits réservés.
# pristivia-invite
