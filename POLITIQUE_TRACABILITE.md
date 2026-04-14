# Politique de traçabilité — Projet IA Agentique

**Objectif :** Maintenir une trace claire des modifications dans Obsidian en utilisant GitHub comme système de gouvernance, sans dépendre d'automation technique.

---

## 1. Workflow par défaut (A) — Modifications importantes

### Avant d'éditer dans Obsidian

**Ouvrir une Issue GitHub (privé)** avec le template `modification.md` :

```
Title: [MOD] Titre de la note | Raison courte

Body:
---
**Note modifiée :** source-xxx-yyyy.md (ou infra-xxx.md ou ligne-temps-xxx.md)
**Raison :** [correction / ajout / clarification / mise à jour]
**Éditeur :** [ton nom]
**Statut :** En cours

---
**Détails :**
[ce que tu changes et pourquoi]
```

### Processus

1. **Éditeur** ouvre l'Issue (intention déclarée)
2. **Fred** valide / discute dans le thread
3. **Éditeur** procède à la modification dans Obsidian
4. **Fred** relit et publie dans Obsidian Publish (le goulot)
5. **Fred** ferme l'Issue avec lien vers la note publiée

---

## 2. Exception (C) — Modifications mineures

**Typos, formattage, petites clarifications (<2 lignes)** :

- Pas d'Issue requise
- Éditeur note simplement : "Typo corrigé dans [note], ligne X"
- Fred documente en batch dans le commit de publication

---

## 3. Commits GitHub — Template de publication

**Chaque fois que tu publies dans Obsidian Publish**, crée **1 commit** :

```
Publish [date]: [liste des notes]

Raison: [correction | ajout | mise à jour | synchronisation]
Éditeurs: [nom1, nom2, ...]
Publiée: [date Obsidian Publish]

---

Exemple :
---
Publish 2026-04-14: source-lewis-rag-2020, _INDEX_Chronologie, infra-memoire

Raison: Ajout source manquante (RAG 2020) + cohérence inter-dossiers
Éditeurs: Fred, ChatBot
Publiée: 2026-04-14
```

---

## 4. Journal des publications

Le fichier `JOURNAL_PUBLICATIONS.md` enregistre l'historique de chaque publication. Fred le met à jour à chaque commit.

**Format :** 
```
| Date | Notes modifiées | Raison | Éditeurs |
|------|-----------------|--------|----------|
| 2026-04-14 | source-lewis-rag-2020, INDEX-Chro | Ajout source + cohérence | Fred |
```

---

## 5. Principes fondamentaux

- **Autonomie Fred :** Pas de script d'automation qui pourrait briser. Fred contrôle la publication.
- **Traçabilité distribée :** La trace repose sur la compétence humaine (Issues + commits) et la cohérence (gabarit).
- **Goulot accepté :** Fred est le goulot de publication. C'est une feature, pas un bug.
- **Flexibilité :** Exception pour les petites choses (C) ; default pour l'important (A).

---

## 6. Checklist pour éditeurs

Avant de modifier une note dans Obsidian :

- [ ] C'est une modification importante (>typo) ?
  - [ ] Oui → ouvrir une Issue d'abord
  - [ ] Non (typo/formattage) → tu peux éditer, Fred documentera en batch

---

## 7. Checklist pour Fred (avant publication)

- [ ] Toutes les Issues sont fermées ou en discussion ?
- [ ] Les notes Obsidian reflètent les changements approuvés ?
- [ ] Créer le commit avec le template (raison + éditeurs)
- [ ] Mettre à jour `JOURNAL_PUBLICATIONS.md`
- [ ] Push vers GitHub
