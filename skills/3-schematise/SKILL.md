---
name: 3-schematise
description: Troisième étape du parcours. Dessine sur un tableau blanc Claude (artefact Whiteboard) les flux d'information de l'outil et ses parcours utilisateurs principaux, à partir du cahier des charges, pour que le dirigeant voie l'outil avant qu'il soit construit et corrige ce qui cloche. Utilise sur /3-schematise, "schématise", "montre-moi les flux", "dessine le parcours", "fais un schéma", "tableau blanc", ou dès que docs/PRD.md est validé. Aval de /2-cadre, enchaîne sur /4-design.
---

# /3-schematise

Un cahier des charges se lit, un schéma se comprend d'un coup d'œil. Cette étape met à plat deux choses sur un tableau blanc partagé :

1. **Les flux d'information** : qui saisit quoi, où ça va, qui le reçoit, ce qui sort de l'outil.
2. **Les parcours principaux** : les deux ou trois user stories qui font l'essentiel de la valeur, étape par étape.

C'est souvent ici que le dirigeant dit « ah non, en vrai c'est la compta qui valide avant ». Tant mieux : c'est moins cher de corriger un schéma qu'un outil.

## 1. Préparer

Lis `docs/PRD.md`. Sans cahier des charges, propose `/2-cadre` d'abord.

Repère, sans poser de question :
- **Les acteurs** : chaque profil d'utilisateur, plus les systèmes extérieurs (tableur existant, logiciel de gestion, messagerie, client final).
- **Les informations qui circulent** : ce qui est saisi, calculé, transmis, notifié, exporté.
- **Les parcours principaux** : les 2 ou 3 US qui portent le moteur métier. Pas toutes les US : un schéma qui montre tout ne montre rien.

Annonce en une phrase ce que tu vas dessiner : « Je dessine les flux entre l'atelier, l'accueil et la compta, puis les parcours de prise de commande et de facturation. »

## 2. Dessiner sur le tableau blanc

Crée le tableau blanc avec l'outil `Artifact` :
1. Trouve le type **Whiteboard** (`action: "list"`, `scope: "types"`) et récupère son `type_url`.
2. Crée l'artefact à partir de ce type avec un titre clair, par exemple « Flux et parcours : nom du projet ».
3. Suis les instructions que renvoie la création pour écrire le contenu du tableau. Elles priment sur ce qui suit pour le format.

Organisation du tableau, de gauche à droite puis de haut en bas :
- **Un titre** et la phrase à retenir, 10 mots maximum (par exemple « Une commande saisie une fois, visible par tous »).
- **Section « Flux d'information »** : un bloc par acteur, des flèches nommées par l'information qui circule (« bon de commande », « facture validée »). Les systèmes extérieurs dans une forme distincte de celle des personnes.
- **Section « Parcours principaux »** : une ligne par parcours, une étape par bloc, le numéro de l'US en tête de ligne. Au-delà de 6 étapes, la ligne repart à gauche en dessous.

Sobriété :
- Quelques mots par bloc, le vocabulaire du cahier des charges.
- Une couleur par type d'élément (acteurs, systèmes, étapes), une seule couleur forte pour ce qui compte le plus (le moteur métier).
- Rien qui se chevauche, rien qui n'aide pas à comprendre.

**Si l'artefact tableau blanc n'est pas disponible** dans l'environnement : dis-le en une ligne, puis produis les mêmes deux schémas dans une page HTML autonome (`docs/schemas.html`, SVG intégré, sans librairie externe) et ouvre-la.

## 3. Faire réagir

Donne le lien du tableau, puis pose une seule question :
> « Est-ce que ça correspond à la réalité de votre entreprise ? Dites-moi ce qui manque ou ce qui est faux, même un détail. »

Le dirigeant peut aussi modifier le tableau directement : relis-le avant de répondre à ses remarques. Le tableau est privé : pour le montrer à son équipe, il le partage depuis le menu Partager du tableau (dis-le-lui une fois).

Sur chaque correction :
- mets à jour le tableau (sans le reconstruire, seulement ce qui change) ;
- si la correction change le fonctionnement de l'outil, mets à jour `docs/PRD.md` en conséquence et dis en une ligne ce qui a changé (« Ajouté US-12 : la compta valide la facture avant envoi »).

## 4. Garder la trace

Une fois le schéma validé, écris `docs/SCHEMAS.md` :

```
# Schémas : nom du projet

- Tableau blanc : lien
- Validé le AAAA-MM-JJ

## Flux d'information
Les flux en quelques lignes de texte (acteur → information → acteur), pour qu'ils restent lisibles sans le tableau.

## Parcours principaux
US-x : étape 1 → étape 2 → ...
```

Confirme « Écrit dans docs/SCHEMAS.md », puis termine comme indiqué dans « Fin de l'étape ».

## Fin de l'étape

Une fois le fichier écrit, termine toujours ainsi, en adaptant les mots au projet :

1. **Ce qui est fait** : une phrase sur ce que cette étape a produit.
2. **La suite du parcours** : les étapes restantes, une ligne chacune :
   - **/4-design** : poser une charte graphique sobre adaptée à votre activité
   - **/5-planifie** : découper le projet en un minimum de phases, la dernière étant un audit de sécurité
   - **/6-construis** : construire l'outil phase par phase sur votre feu vert, cahier des charges tenu à jour
3. **Ta recommandation** : l'étape suivante, avec une raison liée au projet (par défaut : les flux sont validés, on peut donner à l'outil une apparence cohérente avant de le construire). Termine par l'action à faire : lancez **/4-design**.

Si le projet est assez simple pour sauter l'étape suivante, dis-le et recommande celle d'après, sans décider à la place du dirigeant.

## Règles

- Pas de personnage dessiné : des blocs, des flèches, des formes.
- Les schémas suivent le cahier des charges. Un écart découvert ici se corrige dans le cahier des charges, jamais seulement sur le tableau.
- Pas de détail technique sur le schéma (pas de base de données, d'API, de serveur) sauf si le dirigeant le demande.
