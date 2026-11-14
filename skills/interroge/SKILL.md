---
name: interroge
description: Première étape du parcours. Part d'un premier brief du dirigeant (quelques lignes, un fichier Excel, un process qui coince, une transcription) et pose toutes les questions nécessaires, une à la fois et sans limite de nombre, jusqu'à une compréhension partagée du vrai besoin. Fait émerger plusieurs pistes, regarde ce qui existe déjà sur le marché, puis écrit docs/DISCOVERY.md. Utilise sur /interroge, "j'ai une idée d'outil", "voici mon brief", "transforme cet excel en outil", "aide-moi à clarifier mon besoin", ou dès qu'un besoin arrive à l'état brut. Enchaîne sur /cadre.
---

# /interroge

Avant d'écrire un cahier des charges, il faut comprendre le besoin. Le dirigeant arrive avec une idée, un fichier, un irritant. Cette skill transforme ce premier brief en compréhension partagée, par une vraie conversation, jamais par un questionnaire à remplir. Elle écrit `docs/DISCOVERY.md`, la matière de `/cadre`.

**Principe central : ne pas sauter à la solution.** Le dirigeant décrit souvent la solution qu'il imagine (« il me faut une appli qui... »). Ton travail est de remonter au problème réel, d'ouvrir plusieurs pistes, de faire trancher, puis seulement de regarder l'existant.

## 1. Recevoir le premier brief

Le premier brief est obligatoire. Prends ce qui est fourni : texte collé, fichier joint, transcription, capture. S'il y a un fichier Excel, utilise la skill `xlsx` si elle est disponible, sinon lis-le directement.

Si rien n'est fourni, ta seule question est :
> « Racontez-moi votre idée ou ce qui vous fait perdre du temps aujourd'hui, en quelques lignes. Si vous avez un fichier (Excel, document, capture), joignez-le. »

N'invente jamais un besoin. Si `docs/DISCOVERY.md` existe déjà, lis-le et ne questionne que sur ce qui manque ou a changé.

## 2. Analyser

Cherche **le moteur métier caché** : la règle, le calcul, la décision que l'outil devra porter. C'est lui le cœur du futur outil, pas la liste des écrans.

- **Fichier Excel** : rôle de chaque onglet, formules clés et la logique qu'elles encodent, ou la logique implicite de la structure (catégories, scores, statuts). Repère les frictions visibles : copier-coller, onglets dupliqués par mois ou par client, saisie en double. C'est souvent là que se trouve la vraie douleur.
- **Brief texte** : même question, au-delà de la solution formulée.

## 3. Restituer

Dis ce que tu as compris en deux ou trois phrases simples : à quoi servirait l'outil, qui s'en servirait, quel est le moteur métier, où est la vraie douleur. Pas de liste, pas de mise en forme. Demande : « C'est bien ça ? »

## 4. Questionner, sans limite

Pose une question à la fois, attends la réponse, puis la suivante. **Il n'y a pas de nombre maximum de questions** : continue tant qu'une zone d'ombre empêcherait d'écrire un cahier des charges solide. Arrête-toi quand chaque réponse n'apporte plus rien de neuf, et dis-le.

Pour chaque question :
- donne ta recommandation ou une hypothèse, pour que le dirigeant puisse simplement valider (« Je suppose que seule votre assistante saisit les commandes, c'est ça ? ») ;
- n'explique pas pourquoi tu poses la question, sauf si on te le demande ;
- ne redemande jamais ce que le brief ou une réponse précédente a déjà donné.

Les zones à couvrir, dans l'ordre qui vient naturellement :
- **Qui** : qui utiliserait l'outil, combien de personnes, à quel moment de leur journée, sur ordinateur ou sur téléphone, au bureau ou sur le terrain.
- **Quoi** : le geste répété aujourd'hui, ce qu'il coûte (temps, erreurs, oublis), ce qui se passe quand ça rate.
- **Données** : ce qui entre, ce qui sort, d'où ça vient, qui doit voir quoi, ce qui est sensible (données de clients, de salariés, financières).
- **Contexte** : outils déjà en place dans l'entreprise, contrainte qui changerait tout (délai, budget, obligation légale), usage interne ou outil destiné à des clients.
- **Succès** : à quoi verrait-on, dans trois mois, que l'outil a réussi.

Vocabulaire du dirigeant, mot pour mot. Aucun terme technique.

## 5. Proposer des pistes

Si le besoin laisse plusieurs directions vraiment différentes, propose 2 à 4 pistes. Pas des variantes de fonctionnalités : de vraies directions. Une ligne chacune :
> « Piste A, [nom court] : [pour qui, quel problème résolu] »

Si le dirigeant sait déjà précisément ce qu'il veut, dis-le et garde cette seule direction.

**Étape bloquante** : ne passe pas à la suite tant qu'une piste n'est pas choisie.

## 6. Regarder ce qui existe

Cherche 2 à 4 outils existants sur le créneau précis de la piste retenue. Pour chacun : ce qu'il fait, ce qu'il ne fait pas, son prix si visible. Paraphrase toujours.

Sois honnête : si un outil du marché couvre déjà 90 % du besoin pour un prix raisonnable, dis-le clairement. Construire n'est pas toujours la bonne réponse.

Puis propose deux options, sans les moyenner :
- **S'inspirer d'un modèle qui marche** : lequel, ce qu'on en reprend.
- **Se différencier** : ce que l'existant fait mal, ancré dans le moteur métier propre à l'entreprise.

Laisse trancher.

## 7. Écrire la synthèse

Écris `docs/DISCOVERY.md` (crée `docs/` au besoin) selon le modèle ci-dessous, confirme « Écrit dans docs/DISCOVERY.md », puis termine par :

> « Prochaine étape : écrire le cahier des charges. On lance /cadre ? »

<discovery-template>
# Discovery : nom provisoire du projet

## Origine
Le premier brief, tel quel, ou la référence au fichier analysé.

## Compréhension
À quoi ça sert, qui s'en sert, le moteur métier, la vraie douleur.

## Ce qu'on a appris
Les réponses clés de la discussion, regroupées par thème (utilisateurs, usage, données, contexte).

## Pistes envisagées
Les pistes proposées, celle retenue, pourquoi les autres sont écartées.

## Ce qui existe déjà
Outils repérés, ce qu'ils font et ne font pas, prix.

## Direction retenue
S'inspirer, se différencier ou mélange, et pourquoi.

## Outils déjà en place
Ce que l'entreprise utilise aujourd'hui (messagerie, tableur, logiciel métier, site...), relevé pendant la discussion.

## À trancher dans /cadre
Ce qui reste ouvert.
</discovery-template>

## Règles

- Une question à la fois, jamais une liste de questions d'un coup.
- Pas de limite de questions, mais pas de question inutile.
- Vouvoiement par défaut, tutoiement si le dirigeant tutoie.
- Pas de cahier des charges ici, pas de découpage, pas de technique : c'est le rôle des étapes suivantes.
