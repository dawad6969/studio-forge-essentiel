---
name: 5-planifie
description: Cinquième étape du parcours. Découpe le cahier des charges en un minimum de phases, chacune utilisable seule par le dirigeant, et termine toujours par une phase d'audit de sécurité simple. Écrit docs/PLAN.md après validation. Utilise sur /5-planifie, "découpe le projet", "fais le plan", "par quoi on commence", "en combien d'étapes", ou dès que le cahier des charges est validé. Aval de /4-design, enchaîne sur /6-construis.
---

# /5-planifie

Tu découpes le projet en phases de construction. **Le moins de phases possible**, mais chacune doit produire quelque chose que le dirigeant peut essayer seul. La dernière phase est toujours un audit de sécurité simple. Sortie : `docs/PLAN.md`.

## 1. Lire

Lis `docs/PRD.md` (en particulier le Socle), `docs/DESIGN.md` et `docs/SCHEMAS.md` s'ils existent. Sans cahier des charges, propose `/2-cadre` d'abord.

Si `docs/PLAN.md` existe déjà, lis-le : ne réécris pas les phases validées, propose seulement ce qui manque (US non couvertes, écart avec un cahier des charges qui a bougé) et signale les contradictions avant d'écrire.

## 2. Découper

Chaque phase est une **tranche complète** : un parcours réel, de la saisie au résultat visible, même minimal. Jamais une phase « on fait toute la base de données » puis une phase « on fait les écrans ».

Méthode :
- **Phase 1 = le moteur métier sur le parcours le plus important**, dans sa forme la plus simple. À la fin de la phase 1, le dirigeant doit pouvoir faire le geste principal de bout en bout, même sans finitions.
- **Phases suivantes** : chacune ajoute un parcours ou un utilisateur qui compte. Regroupe les petites US ensemble plutôt que d'en faire des phases.
- **Viser 2 à 4 phases de construction** pour un outil de PME. Au-delà de 5, le projet est probablement trop gros pour une première version : propose de reporter une partie dans « Ce qui n'est pas prévu pour cette version ».
- **Dernière phase : audit de sécurité simple** (voir plus bas), toujours présente, jamais fusionnée avec une autre.

Chaque US du cahier des charges est couverte par exactement une phase, ou explicitement reportée.

## 3. Faire valider

Présente le découpage en liste courte. Pour chaque phase :
- **Titre** : ce que le dirigeant pourra faire à la fin (« Saisir et suivre une commande »).
- **US couvertes** : numéros.
- **Ce qu'on pourra essayer** : une phrase concrète.
- **Temps avec Claude** : écriture en minutes, nombre d'échanges de votre part (tests, retours, décisions). Jamais en jours ni en semaines.

Puis une seule question : « Ce découpage vous convient, ou on regroupe / sépare une phase ? » Itère jusqu'à validation.

## 4. Écrire le plan

Écris `docs/PLAN.md` selon le modèle et confirme « Écrit dans docs/PLAN.md », puis termine comme indiqué dans « Fin de l'étape ».

<plan-template>
# Plan : nom du projet

> Cahier des charges : docs/PRD.md · Charte : docs/DESIGN.md

## Choix qui ne bougeront pas

Les décisions qui valent pour toutes les phases, en langage clair : le socle retenu, les grandes informations que l'outil manipule (commandes, clients, interventions...), qui se connecte et comment.

---

## Phase 1 : titre

**Statut** : à faire | en cours | terminée
**US** : US-1, US-2
**Temps avec Claude** : n min d'écriture, n échanges

### Ce qu'on pourra essayer
Le parcours de bout en bout, du point de vue de l'utilisateur.

### C'est terminé quand
- [ ] critère observable
- [ ] critère observable

---

## Phase n : Audit de sécurité

**Statut** : à faire
**Temps avec Claude** : n min, n échanges

### C'est terminé quand
- [ ] Chaque page qui affiche des données demande d'être connecté (sauf ce qui est volontairement public).
- [ ] Un utilisateur ne voit jamais les données d'un autre utilisateur ou d'une autre équipe s'il ne doit pas les voir : testé avec deux comptes.
- [ ] Aucun mot de passe, clé ou code d'accès n'est écrit dans le code ou dans un fichier partagé.
- [ ] Les champs de saisie refusent ce qui n'a pas de sens (montant négatif, date impossible, texte trop long).
- [ ] Les données personnelles stockées sont listées (quoi, pourquoi, qui y a accès), et une mention d'information existe pour les personnes concernées.
- [ ] Les données sont sauvegardées, et on sait comment les récupérer.
- [ ] Les composants utilisés sont à jour, sans faille connue signalée.

Adapter la liste au socle : un artefact sans connexion ni données personnelles n'a besoin que des points qui s'appliquent. Chaque point non applicable est noté « sans objet » avec sa raison, jamais supprimé en silence.

---

## Journal des ajustements

Rempli par /6-construis quand un ajustement change une phase.
</plan-template>

## Fin de l'étape

Une fois le fichier écrit, termine toujours ainsi, en adaptant les mots au projet :

1. **Ce qui est fait** : une phrase sur ce que cette étape a produit.
2. **La suite du parcours** : les étapes restantes, une ligne chacune :
   - **/6-construis** : construire l'outil phase par phase sur votre feu vert, cahier des charges tenu à jour
3. **Ta recommandation** : l'étape suivante, avec une raison liée au projet (par défaut : le plan est validé, la construction peut commencer). Termine par l'action à faire : dites simplement **GO phase 1** (cela lance /6-construis).

Si le projet est assez simple pour sauter l'étape suivante, dis-le et recommande celle d'après, sans décider à la place du dirigeant.

## Règles

- Le minimum de phases qui garde chaque phase utilisable seule.
- Pas de nom de fichier ni de détail de code dans le plan.
- L'audit de sécurité est toujours la dernière phase.
- Vocabulaire du cahier des charges. Vouvoiement par défaut.
