# Manuel utilisateur de CattitudeFlow

## Table des matières

1. [Vue d'ensemble](#vue-densemble)
2. [Disposition de l'ecran](#disposition-de-lecran)
3. [Ecran Home](#ecran-home)
4. [Ecran Notes](#ecran-notes)
5. [Ecran Tickets](#ecran-tickets)
6. [Ecran Focus](#ecran-focus)
7. [Ecran Settings](#ecran-settings)
8. [Reference de la syntaxe de recherche](#reference-de-la-syntaxe-de-recherche)
9. [Raccourcis clavier](#raccourcis-clavier)
10. [FAQ](#faq)
11. [Depannage](#depannage)

---

## Vue d'ensemble

**CattitudeFlow** est une application de bureau qui combine la prise de notes de style Cornell avec la gestion de tickets (tâches).

Les notes sont rédigées au format Markdown et structurées en trois panneaux — **Cue / Note / Summary** — selon la méthode Cornell.  
Les tickets prennent en charge des **Memos** de style Cornell, ce qui vous permet d'attacher plusieurs notes structurées à n'importe quelle tâche.

---

## Disposition de l'ecran

### Navigation d'en-tête

Les boutons de navigation en haut de l'application sont les suivants.

| Bouton | Description |
|--------|-------------|
| Home | Liste unifiée et recherche des notes, tickets et TODO |
| Notes | Créer et modifier des notes de style Cornell |
| Tickets | Gérer les tâches et les tickets |
| Focus | Afficher les notes/tickets classés par score d'importance |
| Settings | Configuration de l'application |

### InfoPill

Affiché du côté droit de l'en-tête.

- **Days remaining**: Nombre de jours restants dans la période d'essai (par ex., 7 jours restants)
- **Free space**: État de l'espace disque (OK / Low)

### Contrôles de fenêtre

Affichés tout à droite de l'en-tête lors de l'exécution en tant qu'application native.

| Bouton | Action |
|--------|--------|
| `_` | Réduire |
| `□` | Agrandir / Restaurer |
| `×` | Fermer |

### Boutons rapides de la barre de titre

| Bouton | Action |
|--------|--------|
| `✂` | Ouvrir la boîte de dialogue du gestionnaire de snippets (`Ctrl+I`) |
| `☀` | Activer / désactiver le curseur Spotlight (`Alt+P`) |
| `☀ ▾` | Changer le preset Spotlight actif |

Le bouton des snippets affiche un badge avec le nombre d'éléments enregistrés. La couleur de l'icône Spotlight suit le preset actuellement sélectionné.


---

## Ecran Home

L'écran Home a une disposition à 3 colonnes : menu à gauche, liste au centre et aperçu Peek à droite.

### Panneau gauche (Menu)

**Liste des filtres**

| Élément | Description |
|------|-------------|
| Notes | Afficher uniquement les notes |
| Tickets | Afficher uniquement les tickets |
| TODO | Afficher les éléments TODO de toutes les notes |
| Images | Afficher une liste des images jointes |
| All | Afficher ensemble les notes + tickets + TODO |

Chaque élément affiche un nombre. Lorsqu'un tag est sélectionné, le nombre est affiché au format `tag count / total count`.

**Filtre de tags**

Les tags des notes et des tickets sont fusionnés et affichés sous forme de chips.  
Cliquez sur un tag pour filtrer les éléments ayant ce tag. Cliquez sur **All** pour effacer le filtre.

### Panneau central (Liste)

**Barre de recherche**

- Texte indicatif : `Full-text search (Ctrl+K) e.g. has:url code:powershell foo`
- `Ctrl+K` pour placer le focus
- Bouton `Clear` pour réinitialiser le terme de recherche
- Saisir rapidement `::` ouvre la fenêtre modale des snippets épinglés

**Chips de filtre**

Les chips de filtre sont affichés sous la barre de recherche (All / Notes / Tickets / TODO).  
Lorsque TODO est sélectionné, une chip **Scope** apparaît également (All / Today).  
Lorsqu'un filtre de date est actif, une chip `date: YYYY-MM-DD ×` est affichée et peut être cliquée pour être retirée.

**Opérations sur la liste**

| Action | Comportement |
|--------|----------|
| Single click | Afficher l'aperçu Peek dans le panneau de droite |
| Double click | Aller à l'écran Notes/Tickets correspondant |
| `Ctrl+Click` | Aller à l'écran correspondant |
| `Enter` | Aller à l'écran correspondant |

**Lignes de Memo de ticket**

Lorsqu'un ticket a des memos attachés, chaque memo est affiché comme ligne enfant sous la ligne du ticket.
Les tickets qui ont des memos affichent un bouton `▼ / ▶` pour développer ou replier l'arborescence des memos.

| Action | Comportement |
|--------|----------|
| Single click | Ouvrir l'écran ticket avec le memo sélectionné |
| `⛶` (fullscreen button) | Ouvrir le memo en aperçu plein écran sans le panneau de liste |

**Onglet Image**

- Affiche la vignette, le chemin, la date de création, la taille et le nombre de références pour chaque image
- Une barre de recherche dédiée (recherche par uid / relPath) est affichée
- Faites défiler jusqu'en bas de la liste pour charger plus d'éléments

### Panneau droit (Aperçu Peek)

Un simple clic sur un élément affiche un aperçu dans le panneau de droite.

- Notes: aperçu de style Cornell (Cue / Note / Summary)
- Tickets: aperçu des informations du ticket
- Images: aperçu de l'image avec une liste des notes/tickets qui la référencent
- Ticket Memos: aperçu du memo de style Cornell (sans panneau de liste)
- **Fullscreen button** (⛶): Ouvrir l'aperçu en plein écran
- **Zoom toggle**: Changer la taille de l'aperçu Cornell (compact / readable)
- Les fichiers modifiés dans un éditeur externe sont détectés automatiquement et actualisent la liste et l'aperçu

### Raccourcis clavier de l'ecran Home

| Raccourci | Action |
|----------|--------|
| `Ctrl+K` | Placer le focus sur la barre de recherche |
| `Ctrl+Shift+T` | Appliquer le filtre de date d'aujourd'hui et afficher le calendrier du mois en cours |

---

## Ecran Notes

### Disposition

L'écran Notes a une disposition à 2 colonnes : **liste de gauche** et **éditeur de droite**.

### Panneau gauche (Liste de notes)

**Création d'une note**

- Ouvrez la boîte de dialogue de nouvelle note à partir du bouton `New` ou de `+`
- Saisissez un titre et une date (par défaut : aujourd'hui) pour la créer
- Si une note portant le même titre existe déjà, cette note sera ouverte

**Création d'une note enfant**

- Cliquez sur le bouton `+ Child Note` lorsqu'une note est sélectionnée pour créer une note enfant de cette note
- Les notes enfants sont affichées comme lignes indentées dans la liste
- Si la note actuellement ouverte est déjà une note enfant, une note sœur (même parent) est créée à la place (les petits-enfants ne sont pas autorisés)

**Recherche**

- Appuyez sur `/` pour placer le focus sur la barre de recherche
- Recherche en texte intégral du contenu des notes via l'hôte

**Filtre de tags**

Cliquez sur une chip de tag pour filtrer les notes par ce tag.

**Pin**

- Cliquez sur l'icône ★ d'une ligne de note pour activer/désactiver le pin
- Les notes épinglées apparaissent en haut de la liste
- La liste est divisée en sections `Pinned` et `All`
- L'état du pin est conservé dans le Workspace (jusqu'à 100 entrées)

### Panneau droit (Editeur)

**Champs de métadonnées**

| Champ | Description |
|-------|-------------|
| Title | Titre de la note (obligatoire) |
| Date | Format YYYY-MM-DD (par ex., 2026-04-26) |
| Tags | Séparés par des virgules (par ex., ops, daily) |

**Éditeur Cornell**

Le corps de la note est divisé en trois panneaux.

| Panneau | Usage |
|------|---------|
| **Cue** | Questions, mots-clés, indices |
| **Note** | Contenu principal, notes détaillées |
| **Summary** | Conclusion, points à retenir |

**Mode d'affichage des panneaux**

Utilisez le commutateur de mode des panneaux pour changer le nombre de panneaux affichés.

| Mode | Affichage |
|------|---------|
| `1` | Panneau unique (uniquement le panneau actif) |
| `2` | Deux panneaux |
| `3` | Trois panneaux (tous les panneaux visibles simultanément) ※ Par défaut |

Le mode d'affichage choisi est appliqué immédiatement et restauré lorsque vous rouvrez la note. En mode 3 panneaux, le panneau Summary reste bien visible.

**Onglets**

| Onglet | Description |
|-----|-------------|
| Edit | Éditeur CodeMirror |
| Preview | Aperçu Markdown (avec table des matières) |

- Appuyez sur `Ctrl+F` pendant l'édition pour ouvrir le panneau de recherche localisé
- L'onglet Preview permet d'exporter en PDF avec le style d'arrière-plan actuel

**Barre d'outils Markdown**

Utilisez la barre d'outils au-dessus de la zone d'édition pour insérer de la mise en forme.

| Bouton | Format |
|--------|--------|
| Bold | `**text**` |
| Italic | `*text*` |
| Strikethrough | `~~text~~` |
| Underline | `<u>text</u>` |
| Text color | `<span style="color:#XXXXXX">text</span>` (20 colors) |
| Bullet list | `- text` |
| Numbered list | `1. text` |
| TODO list | `- [ ] text` |
| Table | Insérer un modèle de tableau |
| Alert box | Alertes GFM (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Heading | H1 / H2 / H3 |

**Palette de couleurs (20 colors)**

Red / Crimson / Orange / Amber / Yellow / Lime / Green / Teal / Cyan / Sky /  
Blue / Indigo / Purple / Violet / Pink / Rose / Brown / Slate / Gray / Black

**Collage d'images**

Collez une image du presse-papiers dans l'éditeur ; elle sera automatiquement enregistrée dans le Workspace et insérée au format d'image Markdown.  
Une surcouche "Importing image…" est affichée pendant le traitement.

**État de sauvegarde**

Affiché dans le coin supérieur droit.

| État | Affichage |
|-------|---------|
| Saved | `Saved` |
| Unsaved | `Unsaved` |
| Saving | `Saving…` |

- Les polices du contenu de l'éditeur et de l'aperçu peuvent être modifiées dans Settings → Editor
- Les fichiers de note modifiés hors de l'application sont rechargés automatiquement

**Suppression**

Cliquez sur l'icône de corbeille pour supprimer une note. Un avertissement est affiché si la note est épinglée ou comporte des modifications non enregistrées.  
Si des notes enfants existent, une boîte de dialogue de confirmation demande s'il faut également les supprimer.

### Raccourcis clavier de l'ecran Notes

| Raccourci | Action |
|----------|--------|
| `Ctrl+Enter` or `Ctrl+S` | Sauvegarder |
| `Ctrl+1` | Aller au panneau Cue |
| `Ctrl+2` | Aller au panneau Note |
| `Ctrl+3` | Aller au panneau Summary |
| `Ctrl+E` | Basculer vers l'onglet Edit |
| `Ctrl+P` | Basculer vers l'onglet Preview |
| `/` | Placer le focus sur la barre de recherche des notes |

---

## Ecran Tickets

Les tickets servent à gérer les tâches et les to-dos. Ils prennent en charge un corps de style Cornell, la gestion du statut, les commentaires et les memos.

### Panneau gauche (Liste des tickets)

**Recherche et filtrage**

| Action | Description |
|--------|-------------|
| `/` key | Placer le focus sur la barre de recherche |
| Priority filter | All / P0 / P1 / P2 / P3 |
| Sort | Par date de mise à jour / date d'échéance / priorité |

**Création d'un ticket**

- Cliquez sur le bouton `New` pour afficher le formulaire de saisie du titre
- Saisissez un titre et appuyez sur `Enter` pour créer

**Liste des memos**

Lorsqu'un ticket est sélectionné, les memos qui lui sont associés sont affichés sous forme de liste sous le ticket.

| Action | Description |
|--------|-------------|
| Click a memo row | Ouvrir ce memo dans le panneau de droite |
| `👁` icon | Masquer / afficher le memo dans la liste (les données sont conservées) |
| `🗑` icon | Supprimer le memo (boîte de dialogue de confirmation affichée) |

### Panneau droit (Editeur de ticket)

La sélection d'un ticket ouvre l'éditeur dans le panneau de droite.

**Champs de métadonnées**

| Champ | Description |
|-------|-------------|
| Title | Titre du ticket (obligatoire) |
| Status | Colonne personnalisée (configurable dans Settings, par ex., backlog / doing / done) |
| Due date | Format YYYY-MM-DD |
| Priority | P0 (la plus haute) / P1 / P2 / P3 (la plus basse) |
| Labels | Séparés par des virgules (par ex., urgent, ops) |

**Onglets**

| Onglet | Description |
|-----|-------------|
| Edit | Éditeur de style Cornell (Cue / Note / Summary) |
| Preview | Aperçu Markdown (disposition Cornell à 3 panneaux) |
| Comments (n) | Ajouter et afficher des commentaires |
| Memo | Voir et modifier les memos du ticket sélectionné |

**Suppression**

Cliquez sur l'icône de corbeille pour supprimer un ticket (boîte de dialogue de confirmation affichée).  
Si le ticket a des memos, la boîte de dialogue inclut le nombre de memos dans le message de confirmation.

### Fonction Memo

Les tickets peuvent avoir plusieurs **memos** de style Cornell. L'onglet s'appelle désormais **Memo**, et les documents enfants auparavant considérés comme des « docs » sont gérés sous le même nom. Vous pouvez ainsi séparer les comptes rendus, notes de recherche et documents d'appui du corps principal du ticket.

**Ajout d'un memo**

- Cliquez sur le bouton `+ Add Memo` dans l'onglet `Memo` ou en bas du panneau de gauche pour créer un memo immédiatement
- Les nouveaux memos utilisent `Memo` comme titre par défaut

**Éditeur de memo**

L'éditeur de memo utilise la même disposition Cornell que les notes, avec des modes 1 / 2 / 3 panneaux. Les comportements de sauvegarde, suppression, plein écran et changement de disposition sont maintenant alignés sur ceux des notes.

| Onglet | Description |
|-----|-------------|
| Edit | Éditeur de style Cornell (Cue / Note / Summary) |
| Preview | Aperçu Markdown (disposition Cornell à 1 / 2 / 3 panneaux) |

- L'auto-save commence dès que le titre existe
- Les changements de mode de panneau sont appliqués immédiatement et restaurés à la prochaine ouverture
- L'onglet Preview inclut l'export PDF
- Les fichiers de memo modifiés dans un éditeur externe sont rechargés automatiquement

**Opérations sur les memos**

| Action | Description |
|--------|-------------|
| Click a memo row | Ouvrir l'éditeur de memo |
| `👁` icon | Masquer / afficher le memo dans la liste (les données sont conservées) |
| `🗑` icon | Supprimer le memo (boîte de dialogue de confirmation affichée) |
| `⛶` (fullscreen) | Ouvrir le memo dans une vue Peek plein écran sans panneau de liste |

> Les memos appartiennent à leur ticket parent. La suppression d'un ticket supprime également tous ses memos.

### Raccourcis clavier de l'ecran Tickets

| Raccourci | Action |
|----------|--------|
| `Ctrl+Enter` | Sauvegarder |
| `/` | Placer le focus sur la barre de recherche des tickets |

---

## Ecran Focus

L'écran Focus affiche vos notes et tickets les plus importants, classés par score, pour une révision et une lecture ciblées.

### Mode d'affichage

| Mode | Description |
|------|-------------|
| Notes | Notes classées par score |
| Tickets | Tickets classés par score |

### Scoring

Les scores des notes sont calculés à partir des facteurs suivants.

- **Edit count** (30 derniers jours) : Peut être activé/désactivé dans Settings
- **Incoming links** : Nombre de fois où la note est référencée depuis d'autres notes

### Disposition

| Zone | Contenu |
|------|---------|
| Left list | Rang, titre, nombre de références, date de mise à jour |
| Right preview | Aperçu de style Cornell de la note sélectionnée |
| `Max` | Nombre maximal d'éléments affichés (5–200) |

### Opérations

| Action | Comportement |
|--------|----------|
| Click | Sélectionner un élément et afficher son aperçu |
| Double-click / `Enter` | Ouvrir dans l'écran Notes/Tickets |
| `Fullscreen` button | Ouvrir la visionneuse plein écran |

### Visionneuse plein écran

- Changer d'élément à l'aide de la liste de gauche
- Rechercher par titre avec la barre de recherche
- Cliquez sur `Open` pour aller à l'écran correspondant
- Appuyez sur `ESC` ou cliquez sur `Close` pour quitter

### Recherche de snippets et fenêtre des éléments épinglés

- Lorsque la barre de recherche est vide, la page reste en mode Focus et affiche les notes et tickets classés par activité d'édition
- Lorsque vous saisissez un mot-clé, la page passe en mode Snippet et met en évidence les panneaux Cornell correspondants
- Saisir rapidement `::` ouvre la fenêtre modale des snippets épinglés pour les copier
- Utilisez le bouton `✂` de la barre de titre ou `Ctrl+I` pour ouvrir le gestionnaire de snippets à tout moment

### Raccourcis clavier de l'ecran Focus

| Raccourci | Action |
|----------|--------|
| `Enter` | Ouvrir l'élément sélectionné |
| `ESC` | Fermer la visionneuse plein écran |

---

## Ecran Settings

Accédez aux réglages depuis le bouton **Settings** de l'en-tête. Sélectionnez une catégorie dans la barre latérale gauche.

### General

| Réglage | Description |
|---------|-------------|
| Language | Langue d'affichage de l'UI (system / ja / en / zh / ko / fr / de) |
| Locale | Paramètre régional pour le formatage des nombres et des dates (laisser vide pour utiliser le réglage de l'OS, par ex., en-US) |
| Theme preset | Thème de couleur |

- `Preview`: Prévisualiser immédiatement le thème sélectionné
- `Save theme`: Sauvegarder le thème vers l'hôte
- `Save language/locale`: Sauvegarder les réglages de langue
- La langue enregistrée est aussi utilisée pour l'interface native et intégrée, comme les boîtes de dialogue de fichiers, les erreurs de démarrage et le panneau de recherche `Ctrl+F`

### Workspace

| Réglage | Description |
|---------|-------------|
| WorkspaceRoot | Chemin où les notes et les tickets sont stockés |

- `Reload`: Récupérer à nouveau les réglages actuels du Workspace
- `Save`: Sauvegarder le chemin modifié

### Notes

| Réglage | Description |
|---------|-------------|
| Auto-save | Si l'auto-save a lieu lors de la saisie (ON/OFF) |
| Auto-save interval (ms) | Intervalle d'auto-save (200–10,000 ms, réglage UI local) |

### Editor

| Réglage | Description |
|---------|-------------|
| Font family | Police utilisée pour le contenu de l'éditeur et de l'aperçu |
| Font size (px) | Taille de police du contenu principal |

- Les modifications sont prévisualisées immédiatement, même avant la sauvegarde
- `Reset to default` rétablit les valeurs par défaut

### Tickets

| Réglage | Description |
|---------|-------------|
| Auto-save | Si l'auto-save a lieu lors de la modification des tickets (ON/OFF) |
| Auto-save interval (ms) | Intervalle d'auto-save (réglage UI local) |
| Columns | Options de statut pour les tickets (séparées par des virgules)<br>par ex., `backlog, doing, done, blocked, archived` |
| Show ticket ID | Afficher les ID de ticket dans les listes/aperçus (réglage UI local) |

### Focus

| Réglage | Description |
|---------|-------------|
| Max items | Nombre maximal d'éléments dans la liste Focus |
| Use edit count for ranking | Ajouter le nombre de sauvegardes de note au score Focus |
| Activity log | Activer le suivi du nombre d'éditions (le contenu des notes et les requêtes de recherche ne sont pas stockés) |

> ※ Les auto-saves consécutives sont comptées comme une seule fois par minute afin d'éviter de gonfler les scores.

### Curseur Spotlight

| Réglage | Description |
|---------|-------------|
| Presets 1–5 | Choisir parmi cinq presets Spotlight fixes |
| Name | Nom affiché pour chaque preset (20 caractères max.) |
| Size (px) | Diamètre du cercle Spotlight (20–200 px) |
| Color | Couleur utilisée par le cercle Spotlight et l'icône d'en-tête |
| Opacity | Niveau de transparence du Spotlight |

- Utilisez le bouton `☀` de la barre de titre ou `Alt+P` pour activer / désactiver le Spotlight
- `Reset to default` restaure la couleur et la taille par défaut du preset actuel

### Maintenance

| Action | Description |
|--------|-------------|
| **Export as Zip** | Sauvegarder le Workspace sous forme de fichier Zip |
| **Restore from Zip** | Restaurer les notes et les tickets depuis un Zip (les données existantes seront remplacées) |
| **Open log folder** | Ouvrir le dossier des logs de l'application dans l'Explorateur de fichiers |
| **Export log Zip** | Exporter les logs sous forme de fichier Zip |
| **Open license folder** | Ouvrir le dossier contenant les fichiers de licence inclus |

> ⚠️ **L'opération de restauration remplace complètement toutes les notes et tous les tickets existants.** Sauvegardez toujours vos données avant de restaurer.

---

## Reference de la syntaxe de recherche

La barre de recherche de l'écran Home prend en charge la syntaxe spéciale suivante.

| Syntaxe | Description | Exemple |
|--------|-------------|---------|
| Plain keywords | Recherche AND avec des espaces | `memo meeting` |
| `"phrase"` | Recherche d'expression (plusieurs mots comme une seule unité) | `"today's work"` |
| `has:url` | Trouver les notes/tickets contenant une URL | `has:url` |
| `code:any` | Trouver les éléments contenant un bloc de code | `code:any` |
| `code:<language>` | Trouver les éléments avec un bloc de code dans le langage spécifié | `code:powershell` |

**Exemple :**
```
has:url code:powershell memo
```
→ Éléments qui contiennent une URL, un bloc de code PowerShell et le mot-clé "memo"

Remarque : saisir rapidement `::` ouvre la fenêtre des snippets épinglés au lieu d'exécuter une recherche normale.

---

## Raccourcis clavier

### Global

| Raccourci | Action |
|----------|--------|
| `Ctrl+K` | Placer le focus sur la barre de recherche Home |
| `Ctrl+I` | Ouvrir la boîte de dialogue du gestionnaire de snippets |
| `Alt+P` | Activer / désactiver le curseur Spotlight |
| `::` | Ouvrir la fenêtre des snippets épinglés |
| `Ctrl+Shift+T` | Appliquer le filtre de date d'aujourd'hui |
| `Ctrl+Mouse Wheel` | Zoom avant / Zoom arrière |
| `Ctrl+0` | Réinitialiser le zoom à 100% |

### Ecran Notes

| Raccourci | Action |
|----------|--------|
| `Ctrl+Enter` / `Ctrl+S` | Sauvegarder |
| `Ctrl+1` | Aller au panneau Cue |
| `Ctrl+2` | Aller au panneau Note |
| `Ctrl+3` | Aller au panneau Summary |
| `Ctrl+E` | Basculer vers l'onglet Edit |
| `Ctrl+P` | Basculer vers l'onglet Preview |
| `/` | Placer le focus sur la barre de recherche des notes |
| `Ctrl+F` | Ouvrir le panneau de recherche dans l'éditeur |

### Ecran Tickets

| Raccourci | Action |
|----------|--------|
| `Ctrl+Enter` | Sauvegarder |
| `/` | Placer le focus sur la barre de recherche des tickets |
| `Ctrl+F` | Ouvrir le panneau de recherche dans l'éditeur |

### Ecran Focus

| Raccourci | Action |
|----------|--------|
| `Enter` | Ouvrir l'élément sélectionné |
| `ESC` | Fermer la visionneuse plein écran |

### Ecran Home

| Raccourci | Action |
|----------|--------|
| `Enter` | Aller à l'élément sélectionné |
| `Ctrl+Click` | Aller à l'élément sélectionné |

---

## FAQ

### Q. Comment le score Focus est-il calcule ?
**A.** Le score est calculé à partir des facteurs suivants :
- **Edit count (edit30d)** : Nombre de sauvegardes au cours des 30 derniers jours (les auto-saves consécutives comptent comme une fois par minute)
- **Incoming links** : Nombre de fois où la note est référencée depuis d'autres notes

Activez/désactivez cela via Settings → Focus → **Use edit count for ranking**.

---

### Q. Combien de memos puis-je ajouter a un ticket ?
**A.** Il n'y a pas de limite. Cliquez sur `+ Add Memo` pour en ajouter autant que nécessaire. Supprimez les memos indésirables avec l'icône de corbeille, ou masquez-les temporairement avec l'icône 👁.

---

### Q. Comment supprimer un element TODO ?
**A.** Les TODO sont des lignes au format `- [ ] text` à l'intérieur d'une note. Supprimez la ligne pendant l'édition de la note, ou marquez-la comme terminée avec `- [x] text`. La liste TODO de l'écran Home se met automatiquement à jour.

---

### Q. Comment ajouter ou modifier les statuts de ticket ?
**A.** Allez dans Settings → Tickets → **Columns** et saisissez des noms de statut séparés par des virgules, puis sauvegardez.  
Exemple : `backlog, doing, done, blocked, archived`

---

### Q. Puis-je synchroniser sur plusieurs appareils ?
**A.** Vous pouvez définir WorkspaceRoot vers un dossier partagé (NAS ou dossier synchronisé via le cloud) pour accéder à vos données, mais **la modification simultanée n'est pas recommandée** car elle peut provoquer des conflits de données.

---

### Q. Une note enfant peut-elle avoir ses propres notes enfants ?
**A.** L'imbrication est limitée à un seul niveau. Si vous cliquez sur `+ Child Note` alors qu'une note enfant est sélectionnée, une note sœur (ayant le même parent) est créée à la place (les petits-enfants ne sont pas créés).

---

### Q. Puis-je utiliser auto-save et le pinning en meme temps ?
**A.** Oui. Auto-save gère le contenu et les métadonnées de la note, tandis que l'état du pinning est géré séparément.

---

## Depannage

### L'application ne demarre pas
1. Vérifiez que **WebView2 Runtime** est installé
2. Vérifiez que le processus hôte (backend) a démarré correctement
3. Allez dans Settings → Maintenance → **Open log folder** pour consulter les logs d'erreur

### Les donnees ne se chargent pas / Une erreur s'affiche

| Error | Solution |
|-------|---------|
| `E_WS_NOT_WRITABLE` | Vérifiez les permissions d'écriture du dossier Workspace |
| `E_WS_INVALID_ROOT` | Vérifiez et corrigez le chemin dans Settings → Workspace |
| `E_APP_NOT_READY` | Attendez que l'application ait fini de démarrer, puis réessayez |
| `E_WEBVIEW2_UNAVAILABLE` | Installez WebView2 Runtime |
| `E_SETTINGS_CORRUPT` | Les réglages seront réinitialisés automatiquement. Reconfigurez vos réglages |

Les erreurs de lecture/écriture de fichiers et les messages des boîtes de dialogue natives sont affichés dans la langue choisie dans Settings.

### Auto-save ne fonctionne pas
1. Vérifiez que Settings → Notes/Tickets → **Auto-save** est activé
2. Vérifiez que autoSaveMs est dans l'intervalle `200–10,000`
3. Vérifiez que le contenu a effectivement changé (aucune sauvegarde n'a lieu si rien n'a changé)

### La recherche ne renvoie aucun resultat
1. Vérifiez l'orthographe de votre terme de recherche
2. Vérifiez si un filtre de tag ou de date est actif (cliquez sur `×` dans les chips de filtre pour l'effacer)
3. Passez le filtre sur **All** et recommencez la recherche

### L'aperçu Peek ne s'affiche pas
- Cliquez sur les éléments avec un **simple clic**, pas un double clic
- Si la fenêtre est trop étroite, élargissez-la pour faire apparaître le panneau de droite
