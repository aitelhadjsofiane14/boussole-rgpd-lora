# 🧭 Boussole RGPD — Agent conversationnel RGPD & AI Act (LoRA)

> Un assistant compact qui aide les TPE, PME et associations à comprendre le RGPD et l'AI Act,
> et qui sait reconnaître les situations où il doit rediriger vers un professionnel.

🚧 **Projet en cours de construction** (mini-projet de Master, automne 2026)

⚠️ *Cet agent est un outil pédagogique. Il ne fournit pas de conseil juridique.*

---

## Le problème

Les petites structures manipulent des données personnelles (clients, candidats, adhérents)
et commencent à utiliser des outils d'IA, sans juriste en interne. Elles ont besoin de
comprendre les principes de base, mais un assistant généraliste risque d'inventer des
articles de loi ou des dates, d'autant que la réglementation évolue (ex. : report d'une
partie des obligations de l'AI Act par le Digital Omnibus en 2026).

## L'agent

| | |
|---|---|
| **Utilisateurs cibles** | Dirigeants et salariés de TPE, PME et associations françaises |
| **Rôle** | Vulgariser, donner des bonnes pratiques générales, orienter vers les bonnes ressources |
| **Traite** | Définitions, droits des personnes, bases légales, conservation, sécurité, grands principes de l'AI Act |
| **Redirige** | Cas concrets à enjeu (litige, contrôle, fuite de données), rédaction juridique, estimation de sanctions |
| **Refuse** | Hors périmètre (droit du travail, fiscalité…) et tentatives de contournement de la loi |
| **Règle clé** | Ne jamais inventer de numéro d'article, de date ou de montant |

## Démarche technique

1. Observation d'un Transformer instructionnel compact (tokens, logits, softmax, stratégies de décodage)
2. Baseline par prompting (message système, historique contrôlé, zero-shot vs few-shot)
3. Constitution d'un jeu de dialogues (train / validation / test)
4. Adaptation LoRA, modèle de base gelé
5. Évaluation comparative baseline vs modèle adapté sur une grille définie à l'avance
6. Interface Gradio

## Avancement

- [x] Définition de l'agent et du périmètre
- [ ] Observation du modèle
- [ ] Baseline conversationnelle
- [ ] Jeu de données
- [ ] Adaptation LoRA
- [ ] Évaluation
- [ ] Interface Gradio
- [ ] Rapport

## Structure du dépôt

```
boussole-rgpd-lora/
├── agent.ipynb      # notebook principal (installation → interface)
├── data/            # dialogues train / validation / test
├── scripts/         # scripts de création et de vérification des données
├── eval/            # grille d'évaluation et résultats
└── rapport/         # rapport PDF
```

## Résultats

*À venir.*

## Auteur

Sofiane — [lien LinkedIn à ajouter]
