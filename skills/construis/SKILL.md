---
name: construis
description: Sixième étape du parcours. Construit l'outil phase par phase selon docs/PLAN.md, sur le feu vert du dirigeant ("GO phase 1", "GO phase 2"...). Fait essayer chaque phase avant de proposer la suivante, débloque les bugs méthodiquement, et met à jour automatiquement le cahier des charges et le plan quand le dirigeant ajuste quelque chose en cours de route. Utilise sur /construis, "GO phase 1", "GO phase n", "on lance la construction", "on attaque", "continue", ou dès que docs/PLAN.md est validé. Aval de /planifie.
---

# /construis

Tu construis l'outil, une phase à la fois, uniquement sur le feu vert du dirigeant. Le cahier des charges (`docs/PRD.md`) reste toujours la vérité sur ce que fait l'outil : quand le projet change en route, tu le mets à jour sans attendre qu'on te le demande.

## Avant chaque phase

1. Lis `docs/PRD.md`, `docs/PLAN.md`, `docs/DESIGN.md` (ils ont pu changer depuis la dernière fois).
2. Identifie la phase demandée. « GO » ou « continue » sans numéro = la première phase dont le statut n'est pas « terminée ».
3. Si une phase précédente n'est pas terminée, dis-le : « La phase 1 n'est pas terminée (il reste : ...). On la finit d'abord ? »
4. Passe le statut de la phase à « en cours » dans `docs/PLAN.md`.
5. Annonce en deux lignes ce que tu vas construire et ce que le dirigeant pourra essayer à la fin.

## Pendant la phase

- Construis sur le socle du cahier des charges, en respectant la charte de `docs/DESIGN.md`.
- Ne construis que ce que couvre la phase. Une bonne idée hors phase se note et se propose à la fin, elle ne s'ajoute pas en douce.
- Coche chaque critère « C'est terminé quand » seulement après l'avoir vérifié toi-même (l'outil lancé, le parcours fait, une capture si possible). Un critère non vérifié reste décoché, et tu le dis.
- Parle au dirigeant en langage clair : ce qui marche, ce qui reste, ce dont tu as besoin de lui. Pas de jargon, pas de détail de code sauf s'il le demande.

### Quand quelque chose ne marche pas

Ne corrige pas au hasard. Procède dans l'ordre :
1. **Reproduire** : retrouve exactement quand le problème arrive.
2. **Trois hypothèses** sur la cause, de la plus probable à la moins probable, en une ligne chacune.
3. **Vérifier** la plus probable (un test, un affichage temporaire), puis les suivantes si besoin.
4. **Corriger** au plus simple, revérifier, retirer ce qui a servi au diagnostic.

Si le problème vient d'une information manquante (un accès, un fichier, une règle métier), arrête-toi et pose la question au dirigeant.

## Ajustements en cours de route

Le dirigeant change d'avis, découvre un cas oublié, veut un détail en plus ou en moins : c'est normal et prévu.

**Pour chaque ajustement, sans demander l'autorisation de mettre à jour les documents :**

1. **Classe-le** :
   - **Détail** qui ne change pas le fonctionnement (un libellé, un ordre d'affichage) : fais-le, aucun document à toucher.
   - **Changement de fonctionnement** (une règle, un parcours, un utilisateur, une donnée) : mets à jour le cahier des charges.
   - **Hors du périmètre** de cette version : signale-le en une ligne et propose de le noter dans « Ce qui n'est pas prévu pour cette version » ou dans une phase future. Ne l'ajoute pas sans accord.
2. **Mets à jour `docs/PRD.md`** pour un changement de fonctionnement :
   - US ajoutée : numérotée à la suite (si la dernière est US-14, la nouvelle est US-15).
   - US modifiée : remplace le texte.
   - US retirée : supprime-la et note pourquoi dans le journal.
   - Règle de fonctionnement, critère de succès, hors périmètre : mets la section à jour.
   - Ajoute une ligne au **Journal des ajustements** : `AAAA-MM-JJ · phase n · ce qui a changé · pourquoi`.
3. **Mets à jour `docs/PLAN.md`** si l'ajustement touche une phase : US ajoutée à la phase concernée (ou à une phase future), critère ajouté ou modifié, ligne dans le journal du plan. Ne modifie jamais les critères d'une phase déjà terminée : un changement qui la touche devient une tâche de la phase en cours.
4. **Dis-le en une ligne**, puis continue : « Cahier des charges mis à jour : US-15 ajoutée, la compta valide la facture avant envoi. »

Si l'ajustement contredit quelque chose de déjà décidé (une règle validée, un élément du hors périmètre, la charte), signale la contradiction et demande avant de toucher quoi que ce soit : « Le cahier des charges exclut l'envoi automatique des factures. On change ça ? »

## Fin de phase

1. Vérifie tous les critères de la phase.
2. Passe le statut à « terminée » dans `docs/PLAN.md`.
3. Dis au dirigeant **quoi essayer et comment**, en deux ou trois étapes concrètes (« Ouvrez le lien, créez une commande pour un client test, vérifiez qu'elle apparaît dans le tableau de suivi »).
4. Récapitule en une ligne les ajustements de la phase, s'il y en a eu.
5. Termine par la suggestion de la suite :
   > « Phase 1 terminée. Essayez-la, dites-moi ce qui ne va pas, ou lancez la suite : **GO phase 2** (titre de la phase 2). »

   Liste ensuite les phases restantes, titre seulement.

## Phase d'audit de sécurité

Pour la dernière phase, reprends chaque point de la liste du plan :
- vérifie-le concrètement (essai avec deux comptes, recherche de clés dans le code, saisie de valeurs absurdes, état des composants) ;
- corrige ce qui peut l'être tout de suite ;
- pour chaque point, donne au dirigeant un verdict clair : **OK**, **corrigé**, ou **à faire de votre côté** (par exemple activer la sauvegarde dans un service externe), avec le lien direct vers la page concernée quand c'est possible.

À la fin, résume l'état de l'outil en trois lignes : ce qui est en place, ce qui reste à faire de son côté, ce qu'on pourrait améliorer dans une prochaine version.

## Fin du projet

Quand toutes les phases sont terminées :
- relis `docs/PRD.md` et vérifie qu'il décrit bien l'outil tel qu'il est construit ; corrige tout écart et note-le dans le journal ;
- propose la suite : « L'outil est construit et le cahier des charges est à jour. Pour une nouvelle fonctionnalité plus tard, relancez /cadre : il partira du cahier des charges existant. »

## Règles

- Jamais de phase lancée sans feu vert explicite du dirigeant.
- Une phase à la fois, chacune utilisable seule avant de passer à la suivante.
- Le cahier des charges suit l'outil en permanence : jamais d'écart non noté entre les deux.
- Ce qui n'a pas été vérifié se dit.
- Vouvoiement par défaut, tutoiement si le dirigeant tutoie.
