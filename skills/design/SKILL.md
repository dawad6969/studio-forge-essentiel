---
name: design
description: Quatrième étape du parcours. Propose une charte graphique sobre adaptée à l'activité de l'entreprise et à l'outil (2 à 3 couleurs, une typographie lisible, boutons plats, peu d'effets), en partant de l'identité existante si elle existe, montre un aperçu, puis écrit docs/DESIGN.md. Utilise sur /design, "charte graphique", "design system", "couleurs", "à quoi ressemblera l'outil", ou dès que le cahier des charges est validé. Aval de /illustre, enchaîne sur /planifie.
---

# /design

Un outil de PME n'a pas besoin d'être spectaculaire. Il doit être lisible, calme et cohérent avec l'entreprise. Cette étape pose une charte simple que toutes les phases de construction respecteront. Sortie : `docs/DESIGN.md`.

## 1. Partir de l'existant

Avant de proposer quoi que ce soit, cherche dans cet ordre et dis ce que tu as trouvé :

1. **`docs/DESIGN.md`** : s'il existe, demande « On le garde, on l'ajuste, ou on repart de zéro ? ».
2. **Identité de l'entreprise** : demande s'il existe un logo, une charte, un site internet. Si oui, analyse le site (couleurs, typographie, ton) et pars de là. L'identité existante prime sur tes préférences.
3. **Rien** : tu proposes une charte sobre (étape 2).

## 2. Comprendre en une question

Lis `docs/PRD.md` (activité, utilisateurs, ordinateur ou téléphone) et pose une seule question :
> « Votre outil est pour [utilisateurs], surtout sur [appareil]. Quelle impression doit-il laisser en trois secondes ? Par exemple : sérieux et rassurant, chaleureux et artisanal, net et efficace. »

## 3. Proposer la charte

En un seul message, chaque choix avec une raison courte liée à l'activité ou aux utilisateurs.

**Le cadre, non négociable sauf demande contraire :**
- **Couleurs** : 2 à 3 au total. Une couleur principale (boutons, liens, éléments actifs), un neutre foncé pour le texte, un neutre clair pour le fond. Une couleur d'accent seulement si elle a un rôle précis (alerte, statut). Ajoute les couleurs d'état (succès, erreur) en version discrète.
- **Typographie** : une seule famille, deux au plus (titres et texte). Lisible avant tout. Taille de texte 16 px minimum.
- **Boutons** : plats, sans dégradé, sans ombre portée. Un bouton principal plein, un bouton secondaire en contour. Coins légèrement arrondis (4 à 8 px).
- **Espacement** : une unité de base (8 px) et ses multiples. De l'air plutôt que des bordures.
- **Effets** : aucun dégradé, aucune ombre forte, aucune animation décorative.
- **Accessibilité** : contraste du texte de 4,5:1 minimum, cibles tactiles de 44 px sur téléphone, pas d'emoji dans l'interface.

**Adapter à l'activité :**
- Artisanat, alimentaire, tourisme : tons chauds et naturels.
- Conseil, finance, juridique : tons sobres et froids, beaucoup de blanc.
- Industrie, logistique, terrain : contraste fort, gros boutons, lisible en plein soleil.
- Santé, social : tons doux, texte grand.

Format de la proposition :

```
IMPRESSION : la phrase du dirigeant
COULEURS : principale #xxxxxx, texte #xxxxxx, fond #xxxxxx (+ accent si utile) : raison
TYPOGRAPHIE : police(s) : raison
BOUTONS : plats, arrondi n px : raison
ESPACEMENT : base 8 px, densité aérée ou compacte : raison
```

Évite les choix génériques : pas de dégradé violet, pas de grille d'icônes dans des ronds colorés, pas de tout-centré.

## 4. Montrer

Montre la charte en vrai plutôt qu'en mots. Avec l'outil `Artifact`, crée un design system à partir du type **Design System** (`action: "list"`, `scope: "types"` pour trouver son `type_url`), puis suis les instructions renvoyées à la création. Contenu minimal : les couleurs, la typographie, les boutons principal et secondaire, un champ de saisie, une carte, et un README d'une page qui explique la charte.

**Si l'artefact design system n'est pas disponible** : écris un aperçu dans `docs/design-preview.html` (une page autonome : palette, typographie, boutons, un champ, une carte, un écran type de l'outil) et ouvre-le.

Demande : « On valide, ou on ajuste une partie ? » Sur un ajustement, propose 2 alternatives pour cette partie seulement.

## 5. Écrire la charte

Une fois validée, écris `docs/DESIGN.md` :

```
# Charte : nom du projet

- Source : identité existante (site, charte) ou création
- Design system : lien de l'artefact, s'il existe
- Impression recherchée : ...

## Couleurs
| Rôle | Valeur | Usage |

## Typographie
Police(s), tailles des titres et du texte.

## Composants
Boutons, champs, cartes : règles en une ligne chacun.

## Règles
Espacement, accessibilité, ce qu'on s'interdit.

## Variables CSS
:root { ... } prêtes à coller.
```

Confirme « Écrit dans docs/DESIGN.md », puis termine par :

> « Prochaine étape : découper le projet en étapes de construction. On lance /planifie ? »

## Règles

- Sobriété d'abord : en cas de doute, enlever plutôt qu'ajouter.
- L'identité existante de l'entreprise se reprend, elle ne se corrige pas sans demande.
- Pas de librairie CSS externe sauf demande.
- Accepte le choix final du dirigeant, même contre ton avis : une ligne sur la cohérence, jamais de blocage.
