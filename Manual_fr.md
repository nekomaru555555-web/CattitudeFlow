# Manuel d'utilisation CattitudeFlow

## Table des matières

1. [Vue d'ensemble](#vue-densemble)
2. [Structure de l'interface](#structure-de-linterface)
3. [Écran d'accueil](#écran-daccueil)
4. [Écran Notes](#écran-notes)
5. [Écran Tickets](#écran-tickets)
6. [Écran Focus](#écran-focus)
7. [Écran Mémo OCR](#écran-mémo-ocr)
8. [Écran Paramètres](#écran-paramètres)
9. [Référence de la syntaxe de recherche](#référence-de-la-syntaxe-de-recherche)
10. [Liste des raccourcis](#liste-des-raccourcis)
11. [Foire aux questions (FAQ)](#foire-aux-questions-faq)
12. [Dépannage](#dépannage)

---

## Vue d'ensemble

**CattitudeFlow** est une application de bureau qui combine la prise de notes selon la méthode Cornell et la gestion des tickets.

Le corps des notes peut être rédigé en Markdown et prend en charge un format de méthode Cornell composé de trois panneaux : Cue, Note et Summary.  
Plusieurs **mémos** de méthode Cornell peuvent être ajoutés à un ticket afin de conserver un historique détaillé lié à la tâche.  
Dans la v1.0.5, outre la fonction **capture OCR** qui permet d'importer directement dans l'application le texte affiché à l'écran, de nouvelles fonctions ont été ajoutées : des **pense-bêtes** à placer librement sur le corps de la note, une **Vue présentation** pour le partage d'écran, et les **formules mathématiques Markdown (KaTeX)**.

---

## Structure de l'interface

### Navigation d'en-tête

Les boutons de navigation suivants sont affichés dans l'en-tête, en haut de l'application.

| Bouton | Description |
|--------|-------------|
| Home | Liste et recherche des notes, tickets et TODO |
| Notes | Création et édition de notes selon la méthode Cornell |
| Tickets | Gestion des tâches et des tickets |
| Focus | Liste des notes et tickets selon leur score d'importance |
| Mémo OCR | Liste et édition des mémos importés par capture OCR |
| Paramètres | Paramètres de l'application |

### InfoPill (pastille d'information)

Les informations suivantes sont affichées à droite de l'en-tête.

- **Jours restants** : nombre de jours restants de la période d'essai (ex. : 7 jours restants)
- **Espace libre** : état de l'espace disque (OK / Faible)

### Boutons de contrôle de la fenêtre

Ils s'affichent à l'extrémité droite de l'en-tête lorsque l'application est lancée en mode natif.

| Bouton | Action |
|--------|--------|
| `_` | Réduire |
| `□` | Agrandir / Restaurer |
| `×` | Fermer |

### Boutons rapides de la barre de titre

| Bouton | Action |
|--------|--------|
| `✂` | Ouvrir la boîte de dialogue de gestion des snippets (`Ctrl+I`) |
| `☀` | Activer / désactiver le curseur Spotlight |
| `☀ ▾` | Changer le preset Spotlight actuel |
| `🖥` Vue présentation | Activer/désactiver la **Vue présentation** pour améliorer la lisibilité de l'aperçu en direct / de l'aperçu (pour le partage d'écran) |

Le bouton des snippets affiche un badge indiquant le nombre d'éléments enregistrés. La couleur du bouton Spotlight suit celle du preset actuellement sélectionné.

La **Vue présentation** accentue la taille de police, l'interligne et le contraste de l'aperçu en direct et de l'aperçu afin qu'ils restent lisibles lors du partage d'écran. L'état Activé/Désactivé est mémorisé dans l'application et n'affecte ni les couleurs du thème ni vos données enregistrées.

### Menu de la barre des tâches système

Un clic droit sur l'icône de la barre des tâches système affiche le menu suivant.

| Élément | Description |
|---------|-------------|
| Afficher / Masquer | Afficher ou masquer la fenêtre principale |
| Spotlight | Activer / désactiver le curseur Spotlight |
| Snippets | Ouvrir la boîte de dialogue de gestion des snippets |
| OCR | Démarrer une capture d'écran |
| Quitter | Fermer l'application |

Le raccourci global actuellement défini s'affiche à droite de chaque élément.  
Les raccourcis peuvent être personnalisés via Paramètres → Raccourcis clavier.

---

## Écran d'accueil

L'écran d'accueil est composé de trois colonnes : menu à gauche, liste au centre et aperçu Peek à droite.

### Panneau de gauche (menu)

**Liste des filtres**

| Élément | Description |
|---------|-------------|
| Notes | Afficher uniquement les notes |
| Tickets | Afficher uniquement les tickets |
| TODO | Afficher les éléments TODO de toutes les notes |
| Images | Afficher la liste des images jointes |
| Tout | Afficher ensemble les notes, tickets et TODO |

Chaque élément affiche un nombre. Lorsqu'un tag est sélectionné, l'affichage prend la forme `nombre du tag / nombre total`.

**Filtre par tags**

Les tags des notes et des tickets sont fusionnés et affichés sous forme de puces.  
Cliquez sur un tag pour n'afficher que les éléments possédant ce tag. Cliquez sur `Tout` pour effacer le filtre.

### Panneau central (liste)

**Barre de recherche**

- Texte indicatif : `Recherche en texte intégral (Ctrl+K) ex. : has:url code:powershell foo`
- `Ctrl+K` place le focus sur la barre
- Le bouton `Effacer` réinitialise le mot-clé de recherche
- En saisissant rapidement `::`, vous pouvez ouvrir la fenêtre modale des snippets épinglés

**Puces de filtre**

Des puces de filtre sont affichées sous la barre de recherche (`Tout` / `Notes` / `Tickets` / `TODO`).  
Lorsque `TODO` est sélectionné, une puce **Portée** est également affichée (`Tout` / `Aujourd'hui`).  
Lorsqu'un filtre de date est actif, une puce `date: YYYY-MM-DD ×` s'affiche et peut être supprimée d'un clic.

**Opérations sur la liste**

| Action | Comportement |
|--------|--------------|
| Simple clic | Afficher l'aperçu Peek dans le panneau de droite |
| Double-clic | Ouvrir l'écran Notes ou Tickets correspondant |
| `Ctrl+Click` | Ouvrir l'écran correspondant |
| `Enter` | Ouvrir l'écran correspondant |

**Lignes de mémo de ticket**

Lorsqu'un ticket contient des mémos, ceux-ci sont affichés en lignes enfants sous la ligne du ticket.
Les tickets possédant des mémos affichent un bouton `▼ / ▶` permettant de replier ou développer l'arborescence des mémos.

| Action | Comportement |
|--------|--------------|
| Simple clic | Ouvrir le mémo dans l'écran Tickets |
| `⛶` (bouton plein écran) | Afficher le mémo en aperçu plein écran sans panneau de liste |

**Lorsque l'onglet Images est sélectionné**

- Les vignettes, chemins, dates de création, tailles et nombres de références des images sont affichés
- Une barre de recherche dédiée (recherche par uid / relPath) est affichée
- Vous pouvez charger des éléments supplémentaires en faisant défiler jusqu'en bas de la liste

### Panneau de droite (aperçu Peek)

Un simple clic sur un élément affiche un aperçu dans le panneau de droite.

- Note : aperçu au format méthode Cornell (Cue / Note / Summary)
- Ticket : aperçu des informations du ticket
- Image : aperçu de l'image avec la liste des notes et tickets qui y font référence
- Mémo de ticket : aperçu du mémo au format méthode Cornell (sans panneau de liste)
- **Bouton plein écran** (⛶) : afficher l'aperçu en plein écran
- **Réduction / agrandissement** : changer la taille de l'aperçu de méthode Cornell (une fiche / lecture confortable)
- Les fichiers modifiés dans un éditeur externe sont détectés automatiquement et répercutés dans la liste et l'aperçu

### Raccourcis clavier de l'écran d'accueil

| Raccourci | Action |
|-----------|--------|
| `Ctrl+K` | Placer le focus sur la barre de recherche |
| `Ctrl+Shift+T` | Appliquer le filtre de date du jour et afficher le calendrier du mois en cours |

---

## Écran Notes

### Structure de l'écran

L'écran Notes est composé de deux colonnes : **liste à gauche** et **éditeur à droite**.

### Panneau de gauche (liste des notes)

**Créer une note**

- Ouvrez la boîte de dialogue de création via le bouton `Nouveau` ou `+`
- Saisissez le titre et la date (par défaut : aujourd'hui), puis créez la note
- Si une note portant le même titre existe déjà, cette note existante est ouverte

**Créer une note enfant**

- Cliquez sur le bouton `+ Note enfant` lorsqu'une note est sélectionnée pour créer une note enfant de la note en cours
- Les notes enfants apparaissent comme des lignes indentées dans la liste
- Si la note actuellement ouverte est déjà une note enfant, une note sœur ayant le même parent est créée à la place (aucune note petit-enfant n'est créée)

**Recherche**

- La touche `/` place le focus sur la barre de recherche
- Recherche en texte intégral dans le contenu des notes via le Full-text search de l'hôte

**Filtre par tags**

Cliquez sur une puce de tag pour filtrer les notes par tag.

**Épinglage**

- L'icône ★ d'une ligne de note active ou désactive l'épinglage
- Les notes épinglées sont affichées en haut de la liste
- L'affichage est séparé en sections `Épinglé` et `Tout`
- L'état d'épinglage est conservé de manière persistante dans le Workspace (100 éléments maximum)

### Panneau de droite (éditeur)

**Champs de métadonnées**

| Champ | Description |
|-------|-------------|
| Titre | Titre de la note (obligatoire) |
| Date | Format YYYY-MM-DD (ex. : 2026-04-26) |
| Tags | Séparés par des virgules (ex. : ops, daily) |

**Éditeur de méthode Cornell**

Le corps de la note est composé des trois panneaux suivants.

| Panneau | Usage |
|---------|-------|
| **Cue** | Questions, mots-clés, indices |
| **Note** | Contenu principal, notes détaillées |
| **Summary** | Résumé, conclusion |

**Mode d'affichage des panneaux**

Le sélecteur de mode des panneaux permet de changer le mode d'affichage.

| Mode | Affichage |
|------|-----------|
| `1` | 1 panneau (seul le panneau actif est affiché) |
| `2` | 2 panneaux |
| `3` | 3 panneaux (tous les panneaux sont visibles en même temps) ※ Par défaut |

Le mode sélectionné est appliqué immédiatement et restauré lorsque vous rouvrez la note.

**Changement d'onglet**

| Onglet | Description |
|--------|-------------|
| Édition | Éditeur CodeMirror |
| Aperçu | Aperçu Markdown (avec table des matières) |

- Pendant l'édition, `Ctrl+F` ouvre un panneau de recherche adapté à la langue d'affichage de l'application
- Dans l'onglet d'aperçu, l'export PDF reflète la couleur d'arrière-plan actuelle

**Barre d'outils Markdown**

La barre d'outils au-dessus de l'onglet d'édition permet d'insérer différents formats.

| Bouton | Format |
|--------|--------|
| Gras | `**texte**` |
| Italique | `*texte*` |
| Barré | `~~texte~~` |
| Souligné | `<u>texte</u>` |
| Couleur du texte | `<span style="color:#XXXXXX">texte</span>` (20 couleurs) |
| Liste à puces | `- texte` |
| Liste numérotée | `1. texte` |
| Liste TODO | `- [ ] texte` |
| Tableau | Insérer un modèle de tableau |
| Boîte d'alerte | Alertes GFM (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Titre | H1 / H2 / H3 |

**Palette de couleurs (20 couleurs)**

Red / Crimson / Orange / Amber / Yellow / Lime / Green / Teal / Cyan / Sky /  
Blue / Indigo / Purple / Violet / Pink / Rose / Brown / Slate / Gray / Black

**Collage d'images**

Lorsque vous collez une image du presse-papiers dans l'éditeur, elle est automatiquement enregistrée dans le Workspace puis insérée au format image Markdown.  
Pendant l'importation, une surcouche « Importation de l'image… » est affichée.

**Pense-bêtes**

Vous pouvez placer des pense-bêtes flottants au-dessus du corps de la note. Faites un clic droit dans le corps de l'éditeur et choisissez `Ajouter un pense-bête` dans le menu contextuel.

- Un pense-bête nouvellement ajouté reçoit automatiquement le focus pour que vous puissiez saisir immédiatement (le focus n'est pas volé pendant la saisie)
- Faites glisser la barre supérieure pour le déplacer. Chaque pense-bête est ancré à une position dans le corps, il suit donc le défilement et les modifications
- Utilisez le bouton de couleur en haut à gauche pour changer la couleur (Jaune → Rose → Bleu → Vert, en boucle)
- Faites glisser le coin inférieur droit de la zone de texte pour la redimensionner ; la nouvelle taille est enregistrée
- Cliquez sur le bouton `✕` pour le supprimer (avec une boîte de dialogue de confirmation)
- Appuyez sur `Ctrl+;` pour insérer la date et `Ctrl+Shift+;` pour insérer l'heure
- Les pense-bêtes sont enregistrés dans le corps de la note, ils sont donc aussi inclus dans les sauvegardes Zip

**Formules mathématiques (Math)**

L'aperçu Markdown et l'aperçu en direct prennent en charge le rendu des formules via KaTeX.

- Formule en ligne : `$E = mc^2$`
- Formule en bloc : entourez-la de `$$` sur des lignes séparées

```
$$
\int_0^1 x^2 dx = \frac{1}{3}
$$
```

**État de sauvegarde**

L'état de sauvegarde est affiché en haut à droite.

| État | Affichage |
|------|-----------|
| Sauvegardé | `Sauvegardé` |
| Non sauvegardé | `Non sauvegardé` |
| Sauvegarde en cours | `Sauvegarde en cours…` |

- Les polices du contenu de l'éditeur et de l'aperçu peuvent être changées via Paramètres → Éditeur
- Si le fichier de note est mis à jour dans un éditeur externe, il est automatiquement rechargé

**Suppression**

L'icône de corbeille permet de supprimer la note. Un avertissement s'affiche si la note est épinglée ou non sauvegardée.  
S'il existe des notes enfants, une boîte de dialogue de confirmation vous demande si elles doivent aussi être supprimées.

### Raccourcis clavier de l'écran Notes

| Raccourci | Action |
|-----------|--------|
| `Ctrl+Enter` ou `Ctrl+S` | Sauvegarder |
| `Ctrl+1` | Aller au panneau Cue |
| `Ctrl+2` | Aller au panneau Note |
| `Ctrl+3` | Aller au panneau Summary |
| `Ctrl+E` | Basculer vers l'onglet Édition |
| `Ctrl+P` | Basculer vers l'onglet Aperçu |
| `/` | Placer le focus sur la barre de recherche des notes |

---

## Écran Tickets

Les tickets servent à gérer les tâches et les TODO. Ils prennent en charge un corps au format méthode Cornell, la gestion du statut, les commentaires et les mémos.

### Panneau de gauche (liste des tickets)

**Recherche et filtrage**

| Action | Description |
|--------|-------------|
| Touche `/` | Placer le focus sur la barre de recherche |
| Filtre de priorité | Tout / P0 / P1 / P2 / P3 |
| Tri | Date de mise à jour / échéance / priorité |

**Créer un ticket**

- Le bouton `Nouveau` affiche le formulaire de saisie du titre
- Saisissez un titre puis appuyez sur `Enter` pour créer le ticket

**Liste des mémos**

Lorsqu'un ticket est sélectionné, les mémos enregistrés pour ce ticket sont affichés en liste dans la partie inférieure.

| Action | Description |
|--------|-------------|
| Cliquer sur une ligne de mémo | Ouvrir ce mémo dans le panneau de droite |
| Icône `👁` | Masquer / réafficher le mémo dans la liste |
| Icône `🗑` | Supprimer le mémo (avec boîte de dialogue de confirmation) |

### Panneau de droite (éditeur de ticket)

Lorsque vous sélectionnez un ticket, l'éditeur s'affiche dans le panneau de droite.

**Champs de métadonnées**

| Champ | Description |
|-------|-------------|
| Titre | Titre du ticket (obligatoire) |
| Statut | Colonnes personnalisées (modifiables dans Paramètres, ex. : backlog / doing / done) |
| Échéance | Format YYYY-MM-DD |
| Priorité | P0 (la plus élevée) / P1 / P2 / P3 (la plus basse) |
| Libellés | Séparés par des virgules (ex. : urgent, ops) |

**Changement d'onglet**

| Onglet | Description |
|--------|-------------|
| Édition | Éditeur de méthode Cornell (Cue / Note / Summary) |
| Aperçu | Aperçu Markdown (méthode Cornell à 3 panneaux) |
| Commentaires (n) | Ajouter et consulter les commentaires |
| Mémos | Liste et édition des mémos du ticket sélectionné |

**Suppression**

L'icône de corbeille supprime le ticket (avec boîte de dialogue de confirmation).  
Si des mémos sont enregistrés, le message de confirmation affiche aussi leur nombre.

### Fonction Mémo

Plusieurs **mémos** de méthode Cornell peuvent être ajoutés à un ticket. Les comptes rendus de réunion, notes de recherche et documents complémentaires peuvent ainsi être organisés séparément du ticket principal.

**Ajouter un mémo**

- Le bouton `+ Ajouter un mémo` dans l'onglet `Mémos`, ou le bouton du même nom en bas du panneau de gauche, crée immédiatement un nouveau mémo
- Le titre par défaut d'un nouveau mémo est `Mémo`

**Éditeur de mémo**

L'éditeur de mémo reprend la même disposition Cornell que les notes et permet de basculer entre l'affichage 1 / 2 / 3 panneaux.

| Onglet | Description |
|--------|-------------|
| Édition | Éditeur de méthode Cornell (Cue / Note / Summary) |
| Aperçu | Aperçu Markdown (méthode Cornell en 1 / 2 / 3 panneaux) |

- La sauvegarde automatique démarre dès que le titre a été saisi
- Le mode de panneau est appliqué immédiatement après le changement et conservé pour la prochaine ouverture
- L'onglet d'aperçu permet l'export PDF
- Comme pour les notes, faites un clic droit dans le corps du volet Note → `Ajouter un pense-bête` pour placer des pense-bêtes

**Réorganiser les mémos**

Les boutons `▲` / `▼` affichés sur chaque ligne de la liste des mémos permettent d'en modifier l'ordre.

**Opérations sur les mémos**

| Action | Description |
|--------|-------------|
| Cliquer sur une ligne de mémo | Ouvrir l'éditeur de mémo |
| Icône `👁` | Masquer / réafficher le mémo dans la liste (les données sont conservées) |
| Icône `🗑` | Supprimer le mémo (avec boîte de dialogue de confirmation) |
| `⛶` (plein écran) | Ouvrir le mémo en plein écran sans panneau de liste |
| `▲` / `▼` | Modifier l'ordre d'affichage du mémo |

> Les mémos sont rattachés au ticket. Si le ticket est supprimé, les mémos le sont également.

### Raccourcis clavier de l'écran Tickets

| Raccourci | Action |
|-----------|--------|
| `Ctrl+Enter` | Sauvegarder |
| `/` | Placer le focus sur la barre de recherche |

---

## Écran Focus

Cet écran permet d'afficher les notes et tickets importants par ordre de score afin de les relire et de les consulter de manière concentrée.

### Mode d'affichage

| Mode | Description |
|------|-------------|
| Notes | Afficher les notes par ordre de score |
| Tickets | Afficher les tickets par ordre de score |

### Calcul du score

Le score des notes est calculé à partir des éléments suivants.

- **Nombre de modifications** (30 derniers jours) : activable/désactivable dans les paramètres
- **Nombre de références entrantes (incomingLinks)** : nombre de références depuis d'autres notes

### Structure de l'écran

| Zone | Contenu |
|------|---------|
| Liste de gauche | Rang, titre, nombre de références, date de mise à jour |
| Aperçu de droite | Aperçu au format méthode Cornell de la note sélectionnée |
| `Max` | Nombre maximal d'éléments à afficher (5 à 200) |

### Opérations

| Action | Comportement |
|--------|--------------|
| Clic | Sélectionner un élément et afficher son aperçu |
| Double-clic / `Enter` | Ouvrir l'élément dans l'écran Notes ou Tickets |
| Bouton `Plein écran` | Ouvrir la visionneuse plein écran |

### Visionneuse plein écran

- Vous pouvez changer d'élément depuis la liste de gauche
- La barre de recherche permet de rechercher par titre
- Le bouton `Ouvrir` permet d'aller à l'écran correspondant
- `ESC` ou `Fermer` quitte la visionneuse

### Recherche de snippets et épinglage

- Lorsque la barre de recherche est vide, la page reste en mode Focus et affiche les notes et tickets classés selon la fréquence d'édition
- Lorsque vous saisissez un mot-clé, elle passe en mode Snippet et met en évidence uniquement les panneaux Cornell correspondants
- En saisissant rapidement `::`, vous pouvez ouvrir la fenêtre modale des snippets épinglés pour les copier
- Le bouton `✂` de la barre de titre ou `Ctrl+I` permet d'ouvrir la boîte de dialogue de gestion des snippets à tout moment

### Raccourcis clavier de l'écran Focus

| Raccourci | Action |
|-----------|--------|
| `Enter` | Ouvrir l'élément sélectionné |
| `ESC` | Fermer la visionneuse plein écran |

---

## Écran Mémo OCR

Vous pouvez capturer une zone quelconque de l'écran, reconnaître le texte qu'elle contient, puis l'enregistrer, l'afficher et le modifier automatiquement comme **Mémo OCR**.  
Les langues de reconnaissance prises en charge sont le japonais, l'anglais, le chinois, le coréen, le français et l'allemand.

### Démarrer une capture OCR

La capture peut être lancée de l'une des manières suivantes.

| Méthode | Action |
|---------|--------|
| Raccourci global | Appuyer sur `Ctrl+Shift+F12` (par défaut) |
| Barre des tâches système | Clic droit sur l'icône de la barre des tâches système → sélectionner **OCR** |

Après le démarrage de la capture, l'écran devient semi-transparent. Faites glisser la souris pour sélectionner la zone rectangulaire à reconnaître ; le traitement OCR démarre alors.

### Liste des mémos OCR

Cliquez sur **Mémo OCR** dans l'en-tête pour afficher l'écran de liste.

| Colonne | Contenu |
|---------|---------|
| Date et heure de capture | Date et heure d'exécution de l'OCR |
| Texte reconnu | Début du résultat OCR |

### Écran d'édition d'un mémo OCR

Sélectionnez un mémo dans la liste pour ouvrir l'écran d'édition.

**Zone d'image (si l'option « Enregistrer l'image » est activée dans les paramètres)**

L'image découpée de la capture d'écran est affichée comme une carte épinglée sur un fond en liège.

**Zone de texte**

Le texte reconnu par l'OCR est affiché dans l'éditeur Markdown.  
Vous pouvez le modifier et le corriger librement.

| Action | Description |
|--------|-------------|
| Modifier le texte | Corriger directement dans l'éditeur |
| Copier | Copier le texte dans le presse-papiers |
| Supprimer | Supprimer le mémo sélectionné (avec boîte de dialogue de confirmation) |

### Suppression en masse

Cliquez sur le bouton **Tout supprimer** en haut de la liste pour afficher une boîte de dialogue de confirmation.  
Après confirmation, tous les mémos OCR sont supprimés.

> ⚠️ **Cette opération est irréversible.** Copiez les textes nécessaires avant de poursuivre.

---

## Écran Paramètres

Vous pouvez modifier les différents réglages depuis **Paramètres** dans l'en-tête. Sélectionnez une catégorie dans la barre latérale gauche.

### Général

| Réglage | Description |
|---------|-------------|
| Langue | Langue d'affichage de l'interface (system / ja / en / zh / ko / fr / de) |
| Paramètre régional | Paramètre régional utilisé pour les nombres et les dates (laissez vide pour utiliser le réglage de l'OS, ex. : ja-JP) |
| Preset de thème | Thème de couleurs |

- `Appliquer l'aperçu` : prévisualiser immédiatement le thème sélectionné
- `Enregistrer le thème` : enregistrer le thème dans l'hôte
- `Enregistrer langue / paramètre régional` : enregistrer les réglages de langue
- La langue enregistrée est aussi appliquée à l'interface native ou intégrée, comme les boîtes de dialogue de fichiers, les erreurs au démarrage et le panneau de recherche `Ctrl+F`

### Workspace

| Réglage | Description |
|---------|-------------|
| WorkspaceRoot | Chemin d'enregistrement des notes et des tickets |

- `Recharger` : relire le réglage Workspace actuel
- `Enregistrer` : enregistrer le chemin modifié

### Notes

| Réglage | Description |
|---------|-------------|
| Sauvegarde automatique | Indique si la sauvegarde automatique est activée pendant la saisie (ON/OFF) |
| Intervalle de sauvegarde automatique (ms) | Intervalle de la sauvegarde automatique (200 à 10 000 ms, réglage local de l'interface) |

### Éditeur

| Réglage | Description |
|---------|-------------|
| Famille de police | Police utilisée pour le contenu de l'éditeur et de l'aperçu |
| Taille de police (px) | Taille de police du contenu principal |
| Rendu de l'arrière-plan de l'aperçu | Activé : les arrière-plans des cartes/blocs de code sont affichés ; Désactivé : ils deviennent transparents et ce réglage s'applique aussi à l'export PDF (par défaut : Désactivé) |
| Couleur du thème pour titres et tableaux | Activé : les titres et en-têtes de tableau adoptent la couleur d'accentuation du thème (primaire) ; Désactivé (par défaut) : ils utilisent la couleur du texte, identique au rendu sobre de l'export PDF |

- Les valeurs saisies sont prévisualisées immédiatement, même avant l'enregistrement
- `Rétablir les valeurs par défaut` restaure les paramètres initiaux (police par défaut, rendu de l'arrière-plan désactivé, couleur du thème désactivée)

### Tickets

| Réglage | Description |
|---------|-------------|
| Sauvegarde automatique | Indique si la sauvegarde automatique est activée pendant l'édition des tickets (ON/OFF) |
| Intervalle de sauvegarde automatique (ms) | Intervalle de la sauvegarde automatique (réglage local de l'interface) |
| Colonnes (Columns) | Valeurs possibles du statut des tickets (séparées par des virgules)<br>Ex. : `backlog, doing, done, blocked, archived` |
| Afficher l'ID du ticket | Afficher l'ID du ticket dans les listes et aperçus (réglage local de l'interface) |

### Focus

| Réglage | Description |
|---------|-------------|
| Nombre maximal | Nombre maximal d'éléments dans la liste Focus |
| Utiliser le nombre de modifications pour le classement | Ajouter le nombre de `note.save` au score Focus |
| Journal d'activité (Activity) | Activer l'agrégation du nombre de modifications (le corps du texte et les requêtes de recherche ne sont pas enregistrés) |

> ※ Les sauvegardes automatiques consécutives sont comptées comme « une fois par minute ».

### Spotlight

| Réglage | Description |
|---------|-------------|
| Presets 1 à 5 | Choisir le Spotlight à utiliser parmi cinq presets fixes |
| Nom | Nom affiché pour chaque preset (20 caractères maximum) |
| Taille (px) | Diamètre du cercle Spotlight (20 à 200 px) |
| Couleur | Couleur du cercle Spotlight et de l'icône d'en-tête |
| Opacité | Niveau de transparence du Spotlight |

- Le bouton `☀` de la barre de titre permet d'activer ou désactiver Spotlight
- `↩ Rétablir les valeurs par défaut` réinitialise la couleur et la taille aux valeurs d'origine

### Raccourcis clavier

Les raccourcis globaux (niveau WPF) peuvent être modifiés.

| Raccourci | Valeur par défaut | Description |
|-----------|-------------------|-------------|
| Afficher / Masquer | `Ctrl+Shift+F9` | Afficher ou masquer la fenêtre principale |
| Spotlight | `Ctrl+Shift+F10` | Activer / désactiver le curseur Spotlight |
| Snippets | `Ctrl+Shift+F11` | Ouvrir la boîte de dialogue de gestion des snippets |
| Mémo OCR | `Ctrl+Shift+F12` | Démarrer la capture OCR |

**Procédure de modification**

1. Cliquez dans le champ du raccourci à modifier (`Cliquez pour modifier` s'affiche)
2. Appuyez sur la nouvelle combinaison de touches (une touche modificatrice est requise)
3. Validez avec le bouton `Enregistrer`
4. Utilisez le bouton `Réinitialiser` pour revenir à la valeur par défaut

Après l'enregistrement, l'affichage des raccourcis dans le menu de la barre des tâches système est mis à jour immédiatement.

### OCR

| Réglage | Description |
|---------|-------------|
| Enregistrer l'image | Joindre l'image au mémo lors d'une capture OCR (par défaut : ON) |

- **ON** : l'image capturée est enregistrée avec le texte OCR. Une zone d'image de style tableau en liège apparaît dans l'écran d'édition du Mémo OCR.
- **OFF** : seul le texte est enregistré.

### Maintenance

| Action | Description |
|--------|-------------|
| **Exporter en Zip** | Sauvegarder le Workspace (notes, tickets, mémos OCR, images) dans un fichier Zip |
| **Restaurer depuis un Zip** | Restaurer les notes, tickets et mémos OCR depuis un Zip (les données existantes sont remplacées) |
| **Ouvrir le dossier des logs** | Ouvrir le dossier des journaux de l'application dans le gestionnaire de fichiers |
| **Exporter les logs en Zip** | Exporter les journaux au format Zip |
| **Ouvrir le dossier des licences** | Ouvrir le dossier contenant les fichiers de licence inclus |

> ⚠️ **L'opération de restauration remplace complètement les notes et tickets existants.** Effectuez toujours une sauvegarde avant d'exécuter cette opération.

---

## Référence de la syntaxe de recherche

La barre de recherche en texte intégral de l'écran d'accueil prend en charge la syntaxe spéciale suivante.

| Syntaxe | Description | Exemple |
|---------|-------------|---------|
| Mots-clés ordinaires | Recherche AND séparée par des espaces | `mémo réunion` |
| `"phrase"` | Recherche d'expression exacte (plusieurs mots considérés comme un bloc) | `"travail du jour"` |
| `has:url` | Rechercher les notes et tickets contenant une URL | `has:url` |
| `code:any` | Rechercher les éléments contenant un bloc de code | `code:any` |
| `code:<langue>` | Rechercher les éléments contenant un bloc de code dans la langue indiquée | `code:powershell` |

**Exemple :**
```
has:url code:powershell mémo
```
→ Élément contenant une URL, un bloc de code PowerShell et le mot-clé « mémo »

Remarque : en saisissant rapidement `::`, vous ouvrez la fenêtre modale des snippets épinglés au lieu d'exécuter une recherche normale.

---

## Liste des raccourcis

### Raccourcis globaux (niveau WPF, personnalisables)

Ils peuvent être modifiés via Paramètres → Raccourcis clavier.

| Raccourci (par défaut) | Action |
|------------------------|--------|
| `Ctrl+Shift+F9` | Afficher / masquer la fenêtre principale |
| `Ctrl+Shift+F10` | Activer / désactiver le curseur Spotlight |
| `Ctrl+Shift+F11` | Ouvrir la boîte de dialogue de gestion des snippets |
| `Ctrl+Shift+F12` | Démarrer la capture OCR |

### Raccourcis globaux dans l'application

| Raccourci | Action |
|-----------|--------|
| `Ctrl+K` | Placer le focus sur la barre de recherche Home |
| `Ctrl+I` | Ouvrir la boîte de dialogue de gestion des snippets |
| `::` | Ouvrir la fenêtre modale des snippets épinglés |
| `Ctrl+Shift+T` | Appliquer le filtre de date du jour |
| `Ctrl+molette de la souris` | Zoom avant / Zoom arrière |
| `Ctrl+0` | Réinitialiser le zoom à 100 % |

### Écran Notes

| Raccourci | Action |
|-----------|--------|
| `Ctrl+Enter` / `Ctrl+S` | Sauvegarder |
| `Ctrl+1` | Aller au panneau Cue |
| `Ctrl+2` | Aller au panneau Note |
| `Ctrl+3` | Aller au panneau Summary |
| `Ctrl+E` | Basculer vers l'onglet Édition |
| `Ctrl+P` | Basculer vers l'onglet Aperçu |
| `/` | Placer le focus sur la barre de recherche |
| `Ctrl+F` | Ouvrir le panneau de recherche dans l'éditeur |

### Écran Tickets

| Raccourci | Action |
|-----------|--------|
| `Ctrl+Enter` | Sauvegarder |
| `/` | Placer le focus sur la barre de recherche |
| `Ctrl+F` | Ouvrir le panneau de recherche dans l'éditeur |

### Écran Focus

| Raccourci | Action |
|-----------|--------|
| `Enter` | Ouvrir l'élément sélectionné |
| `ESC` | Fermer la visionneuse plein écran |

### Écran d'accueil (opérations sur la liste)

| Raccourci | Action |
|-----------|--------|
| `Enter` | Aller à l'élément sélectionné |
| `Ctrl+Click` | Aller à l'élément sélectionné |

---

## Foire aux questions (FAQ)

### Q. Comment le score Focus est-il déterminé ?
**R.** Il est calculé à partir des éléments suivants.
- **Nombre de modifications (edit30d)** : nombre de sauvegardes sur les 30 derniers jours (les sauvegardes automatiques consécutives sont ramenées à une fois par minute)
- **Nombre de références entrantes (incomingLinks)** : nombre de liens provenant d'autres notes

Vous pouvez activer ou désactiver ce facteur via Paramètres → Focus → **Utiliser le nombre de modifications pour le classement**.

---

### Q. Puis-je ajouter autant de mémos que je veux à un ticket ?
**R.** Oui, il n'y a pas de limite. Utilisez le bouton `+ Ajouter un mémo` pour en créer autant que nécessaire. Les mémos inutiles peuvent être supprimés avec l'icône de corbeille, ou masqués temporairement avec l'icône 👁.

---

### Q. Comment supprimer un TODO ?
**R.** Un TODO est une ligne au format `- [ ] texte` dans une note. Supprimez cette ligne pendant l'édition de la note, ou marquez-la comme terminée avec `- [x] texte`. La liste TODO de l'écran d'accueil sera mise à jour automatiquement.

---

### Q. Je souhaite ajouter ou modifier les statuts des tickets
**R.** Allez dans Paramètres → Tickets → **Colonnes (Columns)**, saisissez les noms de statut séparés par des virgules, puis enregistrez.  
Exemple : `backlog, doing, done, blocked, archived`

---

### Q. La synchronisation sur plusieurs appareils est-elle possible ?
**R.** Vous pouvez référencer un dossier partagé (NAS ou dossier synchronisé dans le cloud) via WorkspaceRoot, mais **la modification simultanée n'est pas recommandée**, car elle peut provoquer des conflits de données.

---

### Q. Une note enfant peut-elle avoir elle-même des notes enfants ?
**R.** L'imbrication des notes enfants est limitée à un seul niveau. Si vous cliquez sur `+ Note enfant` alors qu'une note enfant est sélectionnée, une note sœur partageant le même parent sera créée à la place (aucune note petit-enfant n'est créée).

---

### Q. Quelles langues l'OCR peut-il reconnaître ?
**R.** L'OCR prend en charge le japonais, l'anglais, le chinois, le coréen, le français et l'allemand. Si plusieurs langues sont mélangées à l'écran, elles peuvent aussi être reconnues, mais la précision dépend de la langue et de la taille des caractères.

---

### Q. Je ne veux pas enregistrer l'image d'une capture OCR
**R.** Désactivez Paramètres → OCR → **Enregistrer l'image** pour ne sauvegarder que le texte. Les images déjà jointes aux mémos existants ne sont pas affectées.

---

### Q. Je souhaite modifier les raccourcis globaux
**R.** Vous pouvez modifier les quatre raccourcis dans Paramètres → Raccourcis clavier. Cliquez dans le champ voulu, appuyez sur la nouvelle combinaison de touches, puis cliquez sur `Enregistrer`.

---

### Q. La sauvegarde automatique et l'épinglage peuvent-ils être utilisés en même temps ?
**R.** Oui. La sauvegarde automatique enregistre régulièrement le contenu et les métadonnées de la note, tandis que l'état d'épinglage est enregistré par un mécanisme distinct.

---

## Dépannage

### L'application ne démarre pas
1. Vérifiez que **WebView2 Runtime** est installé
2. Vérifiez que le côté hôte (processus backend) démarre correctement
3. Ouvrez Paramètres → Maintenance → **Ouvrir le dossier des logs** pour consulter les journaux d'erreur

### Les données ne se chargent pas / une erreur s'affiche

| Erreur | Solution |
|--------|----------|
| `E_WS_NOT_WRITABLE` | Vérifiez les droits d'écriture du dossier Workspace |
| `E_WS_INVALID_ROOT` | Vérifiez et corrigez le chemin dans Paramètres → Workspace |
| `E_APP_NOT_READY` | Attendez la fin du démarrage de l'application puis réessayez |
| `E_WEBVIEW2_UNAVAILABLE` | Installez WebView2 Runtime |
| `E_SETTINGS_CORRUPT` | Les paramètres sont réinitialisés automatiquement. Reconfigurez-les ensuite |

Les erreurs de lecture / écriture de fichiers et les messages des boîtes de dialogue natives sont affichés dans la langue sélectionnée.

### La sauvegarde automatique ne fonctionne pas
1. Vérifiez que Paramètres → Notes / Tickets → **Sauvegarde automatique** est activé
2. Vérifiez que `autoSaveMs` est compris entre `200` et `10,000`
3. Vérifiez que le contenu de la note ou du ticket a réellement changé (sans modification, aucune sauvegarde n'a lieu)

### Aucun résultat de recherche ne s'affiche
1. Vérifiez l'orthographe du mot-clé
2. Vérifiez qu'aucun filtre de tag ou de date n'est appliqué (supprimez-le avec `×` dans les puces de filtre)
3. Repassez le filtre sur **Tout** puis relancez la recherche

### L'aperçu Peek ne s'affiche pas
- Cliquez sur l'élément avec un **simple clic**, et non avec un double-clic
- Si la fenêtre est trop étroite, élargissez-la pour faire apparaître le panneau de droite

### L'OCR ne fonctionne pas
1. L'initialisation du moteur OCR peut prendre quelques secondes. Patientez puis réessayez
2. Redémarrez l'application puis réessayez
3. Ouvrez Paramètres → Maintenance → **Ouvrir le dossier des logs** pour consulter les journaux d'erreur
