---
name: 2-cadre
description: Deuxième étape du parcours. Identifie les outils et l'infrastructure que l'entreprise utilise déjà (ou en propose si elle n'en a pas), puis rédige un cahier des charges en langage clair, validé section par section par le dirigeant, et l'écrit dans docs/PRD.md. Utilise sur /2-cadre, "écris le cahier des charges", "fais le PRD", "cadre le projet", "formalise mon besoin", ou dès que docs/DISCOVERY.md existe. Aval de /1-interroge, enchaîne sur /3-schematise.
---

# /2-cadre

Tu produis le cahier des charges du projet, `docs/PRD.md`. Un seul document, lisible par le dirigeant sans aide, et assez précis pour que Claude (ou un prestataire) construise l'outil sans deviner.

## 1. Récupérer la matière

- Lis `docs/DISCOVERY.md` s'il existe : c'est le brief déjà digéré. Ne repose jamais une question qui y est résolue.
- Si `docs/PRD.md` existe, lis-le et ne questionne que sur ce qui change. Signale toute contradiction avec DISCOVERY : « Vous aviez dit X, le brief suggère Y, on garde lequel ? »
- Ni l'un ni l'autre, et le besoin est encore flou : propose `/1-interroge` d'abord. Si le dirigeant préfère cadrer directement, ta première question est « Qu'est-ce qu'on cadre ? ».

## 2. Identifier le socle technique

Avant tout le reste, repère sur quoi l'outil va s'appuyer. Pars de la section « Outils déjà en place » de DISCOVERY, puis complète par des questions, une à la fois :

- **Bureautique et messagerie** : Microsoft 365, Google Workspace, autre ?
- **Données existantes** : tableurs, logiciel de gestion, CRM, ERP, logiciel de caisse, site internet ? Où sont les données que l'outil devra lire ou alimenter ?
- **Accès** : qui se connecte, avec quel compte (compte de l'entreprise, compte personnel, aucun) ?
- **Contraintes** : hébergement imposé, prestataire informatique en place, politique de sécurité, budget mensuel acceptable pour des abonnements ?

Ensuite, deux cas :

**L'entreprise a déjà un socle** : l'outil s'y branche. Tu recommandes la façon la plus simple de rester dans cet existant (par exemple, un outil construit autour des tableurs Google déjà utilisés plutôt qu'une nouvelle base de données).

**L'entreprise n'a pas de socle adapté** : propose-en un, avec ta recommandation et une raison en une phrase. Repère selon le besoin :

| Besoin | Socle proposé |
|---|---|
| Outil personnel ou petite équipe, peu de données, pas de connexion individuelle | Un artefact Claude (page interactive avec données partagées) ou un tableur enrichi. **Condition** : un artefact avec données partagées est réservé à l'organisation Claude de son créateur. Chaque personne ou appareil qui l'ouvre doit être connecté à un compte membre de cette organisation (par exemple une offre Team de l'entreprise), et l'artefact doit être partagé depuis son menu Partager. Il ne peut pas être rendu public. Si ce n'est pas le cas, passer à la ligne suivante. |
| Plusieurs utilisateurs, données partagées, accès sur téléphone | Une application web : Next.js + Supabase (base et comptes) + Vercel (mise en ligne), offres gratuites pour démarrer |
| L'entreprise vit déjà dans Google Workspace ou Microsoft 365 | Une extension de cet environnement (Google Sheets + Apps Script, ou Microsoft Lists + Power Automate) |

Pour chaque socle proposé, vérifie avec le dirigeant comment chaque utilisateur y accédera concrètement (quel compte, quel appareil). Nomme les outils, dis ce que ça coûtera par mois au démarrage si c'est payant (recherche les tarifs actuels, ne les donne pas de mémoire), et attends la validation. Le socle choisi va dans la section Socle du cahier des charges, et c'est la seule section qui nomme des technologies.

## 3. Compléter, une question à la fois

Suis cet ordre : Problème, Utilisateurs, Solution, Critères de succès, Hors périmètre. Les parcours (user stories) et les règles de fonctionnement émergent en route. Pour chaque question, donne ta recommandation.

DISCOVERY nourrit directement Problème et Solution : reformule, ne redemande pas. Avant de rédiger, demande : « Un risque, une dépendance, une hypothèse à noter ? »

## 4. Rédiger et faire valider

Quand chaque section peut s'écrire sans trou, dis-le en une phrase et poste le cahier des charges complet dans le chat, selon le modèle. Le dirigeant valide ou corrige section par section. Sur une correction, re-poste seulement la section touchée.

Une fois tout validé, écris `docs/PRD.md` (crée `docs/` au besoin), confirme « Écrit dans docs/PRD.md », puis termine comme indiqué dans « Fin de l'étape ».

<prd-template>
# Cahier des charges : nom du projet

> Statut : validé le AAAA-MM-JJ

## Socle

Les outils sur lesquels l'outil s'appuie, existants ou proposés, et pourquoi.
- **Déjà en place** : ...
- **Retenu pour l'outil** : ...
- **Coût mensuel estimé au démarrage** : ...
- **Accès** : qui se connecte, comment.

## Le problème

La situation vécue et son coût. Trois lignes maximum : le geste pénible, le chiffre qui pique, la conséquence.

## Les utilisateurs

Chaque profil, assez précis pour imaginer une personne réelle : qui, combien, quand, sur quel appareil.

## La solution

Ce que l'outil permet, du point de vue de l'utilisateur. Trois lignes maximum.

## Ce que l'outil permettra de faire

Parcours numérotés, regroupés par moment d'usage, au format :
- **US-1** : En tant que [utilisateur], je veux [action], afin de [bénéfice].

Couvrir les parcours principaux, l'état vide (première utilisation), les erreurs, les cas limites qui comptent vraiment.

## Règles de fonctionnement

Ce que l'utilisateur observe à l'usage : limites chiffrées, calculs métier, qui voit quoi, ce qui se passe en cas d'erreur, ordinateur ou téléphone. Pas de détail technique interne.

## Comment on saura que c'est réussi

Critères vérifiables : une action observable ou une mesure (durée, nombre, seuil). Jamais « l'utilisateur comprend ».

## Ce qui n'est pas prévu pour cette version

Ce qu'on refuse explicitement. C'est ce qui protège le projet de l'éparpillement.

## Notes

Risques, dépendances, hypothèses. « Rien à signaler. » si rien.

## Journal des ajustements

Rempli automatiquement par /6-construis quand le projet change en cours de route. Vide au départ.
</prd-template>

## Fin de l'étape

Une fois le fichier écrit, termine toujours ainsi, en adaptant les mots au projet :

1. **Ce qui est fait** : une phrase sur ce que cette étape a produit.
2. **La suite du parcours** : les étapes restantes, une ligne chacune :
   - **/3-schematise** : voir les flux d'information et les parcours principaux sur un tableau blanc
   - **/4-design** : poser une charte graphique sobre adaptée à votre activité
   - **/5-planifie** : découper le projet en un minimum de phases, la dernière étant un audit de sécurité
   - **/6-construis** : construire l'outil phase par phase sur votre feu vert, cahier des charges tenu à jour
3. **Ta recommandation** : l'étape suivante, avec une raison liée au projet (par défaut : un schéma fait apparaître en quelques minutes les oublis et les malentendus que le texte cache). Termine par l'action à faire : lancez **/3-schematise**.

Si le projet est assez simple pour sauter l'étape suivante, dis-le et recommande celle d'après, sans décider à la place du dirigeant.

## Règles

- Vocabulaire du dirigeant, mot pour mot. Aucun jargon hors section Socle.
- Parcours toujours numérotés US-1, US-2... : les étapes suivantes s'y réfèrent.
- Pas de chemin de fichier ni de code dans le cahier des charges.
- Vouvoiement par défaut, tutoiement si le dirigeant tutoie.
