# studio-forge-essentiel

Le parcours essentiel du Studio David Perret, pour les dirigeants de PME qui veulent transformer une idée, un fichier Excel ou un process qui coince en un outil construit avec Claude.

Six étapes, toujours dans le même ordre. Chacune lit ce que la précédente a produit, ne redemande jamais ce qui est déjà tranché, et finit en vous proposant de lancer la suivante.

## Le parcours

```
votre idée, votre fichier, votre irritant
  → /interroge   comprendre le vrai besoin          docs/DISCOVERY.md
  → /cadre       écrire le cahier des charges        docs/PRD.md
  → /illustre    schématiser les flux et parcours    tableau blanc Claude
  → /design      poser une charte sobre              docs/DESIGN.md
  → /planifie    découper en étapes, finir par la sécurité   docs/PLAN.md
  → /construis   GO phase 1, GO phase 2...           l'outil, et un cahier des charges à jour
```

| Étape | Ce qu'elle fait |
|---|---|
| `/interroge` | Part de votre premier brief et vous pose toutes les questions nécessaires, une à la fois, jusqu'à ce que le besoin soit clair. Fait émerger plusieurs pistes, regarde ce qui existe déjà sur le marché. |
| `/cadre` | Repère les outils que votre entreprise utilise déjà (ou vous en propose), puis rédige le cahier des charges à valider section par section. |
| `/illustre` | Dessine sur un tableau blanc Claude les flux d'information et les parcours principaux des utilisateurs. On voit l'outil avant de le construire. |
| `/design` | Propose une charte graphique sobre adaptée à votre activité : 2 ou 3 couleurs, une typographie lisible, des boutons plats. |
| `/planifie` | Découpe le projet en un minimum d'étapes, chacune utilisable seule, et termine toujours par un audit de sécurité simple. |
| `/construis` | Construit l'outil phase par phase sur votre feu vert (« GO phase 1 »). Si vous changez d'avis en route, le cahier des charges est mis à jour automatiquement. |

## Où ça tourne

Dans Claude Code et dans Cowork. Les documents sont écrits dans un dossier `docs/` du projet : ouvrez un dossier dédié par projet avant de commencer.

`/illustre` et `/design` utilisent les artefacts Claude (tableau blanc, design system). S'ils ne sont pas disponibles dans votre environnement, la skill bascule sur un schéma ou une page HTML classique.

## Installation

Dans Claude Code :

```
/plugin marketplace add <compte-github>/studio-forge-essentiel
/plugin install studio-forge-essentiel@studio-forge-essentiel
```

Puis tapez `/interroge` et collez votre premier brief.

## Origine

Version allégée de `studio-forge`, le plugin de production du Studio. `/cadre`, `/planifie`, `/design` et `/illustre` sont adaptés de [Claude Mastery](https://github.com/naiersaidane/claude-mastery) (licence MIT, voir `LICENSE-claude-mastery`). Le suivi des ajustements de `/construis` reprend le cycle d'évolution d'[OpenSpec](https://github.com/Fission-AI/OpenSpec), simplifié.

## Licence

MIT.
