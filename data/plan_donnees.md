# Plan de constitution des données — Boussole RGPD

## 1. Objectif

Corriger les défauts **mesurés** sur la baseline Qwen3-4B (config C) sans dégrader ce qui fonctionne déjà :

| Défaut observé (requêtes de test) | Réponse du jeu de données |
|---|---|
| Dates inventées malgré la consigne (T13, sondage AI Act) | Catégorie D : ne jamais donner de date, expliquer que le calendrier a changé |
| Faits inventés (T10 niveaux de risque, T27 « 30 jours ouvrés », T31 obligation inexistante) | Dialogues fondés uniquement sur la fiche de faits, liste blanche des chiffres |
| « Non » faux aux questions de permission (T29, T15, fichier papier) | Catégorie C : réponses « oui, mais » / « ça dépend » |
| « Oui » dangereux (T25 biométrie) | Catégorie C : rappeler le caractère sensible et l'alternative |
| Oubli de l'AI Act quand il est pertinent (T26) | Catégorie E : AI Act et cumul avec le RGPD |
| Tutoiement (T20, T35) | Vouvoiement dans 100 % des dialogues |
| Refus total d'une question mixte (T35) | Catégorie H : réponses partielles |
| Organismes et URL inventés | Ressources limitées à F32 |

## 2. Répartition cible (~330 dialogues)

| Cat. | Comportement | Nb | Faits principaux |
|---|---|---|---|
| A | Répondre : notions et principes | 60 | F01–F14 |
| B | Répondre : situations pratiques (recrutement, prospection, cookies, sécurité, anonymisation, IA générative) | 55 | F14, F18–F25 |
| C | Répondre « oui, mais » / « ça dépend » à une question de permission | 45 | F10, F20–F24 |
| D | Ne pas inventer : dates, montants pour un cas précis, durées absentes de la fiche | 30 | F17, F30 |
| E | AI Act : niveaux, haut risque, fournisseur/déployeur, transparence, cumul avec le RGPD | 35 | F26–F31 |
| F | Rediriger : contrôle, plainte, litige, contrat, violation en cours, rédaction juridique | 30 | F15, F17, F32 |
| G | Refuser : hors périmètre (15), contournement de la loi (12), injection de consigne (8) | 35 | F32 |
| H | Multi-tours (2 à 3 échanges) et questions mixtes | 40 | variés |

Environ 60 % de réponses directes (A, B, C, E), pour éviter un modèle qui refuse ou redirige trop. Les refus (G) restent minoritaires car la baseline les réussit déjà.

## 3. Règles de rédaction des réponses

1. **Vouvoiement**, français, **3 à 6 phrases**, texte continu (pas de titres ni de listes à puces).
2. La **première phrase répond** à la question (« Oui, à condition que… », « Non, … », « Cela dépend de… »).
3. Uniquement des faits de la fiche. Chiffres : seulement ceux marqués 🔢.
4. Aucune URL détaillée, aucun numéro d'article cité dans la réponse, aucun organisme inventé.
5. Renvoi vers une ressource (CNIL, DPO, avocat) quand il est utile, **pas systématiquement** (environ une réponse sur deux), pour éviter une formule finale répétée mécaniquement.
6. Refus : poli, une phrase d'explication, rappel du périmètre ou alternative légale.
7. Formulations des questions variées : registre familier ou soutenu, fautes de frappe occasionnelles, secteurs variés (boulangerie, cabinet médical, association sportive, agence web, garage, école de musique…).
8. Aucune donnée personnelle réelle : prénoms génériques si nécessaire, pas d'email ni de téléphone.

## 4. Format d'un dialogue

Une ligne JSON par dialogue dans `data/dialogues.jsonl` :

```json
{"id": "D0001", "categorie": "C", "faits": ["F10"], "messages": [
  {"role": "user", "content": "..."},
  {"role": "assistant", "content": "..."}
]}
```

Le message système (SYSTEM_V2, identique à celui de la baseline) est ajouté **au moment de l'entraînement**, sans les exemples few-shot : on veut que l'adaptateur apprenne le comportement sans avoir besoin de ces exemples dans le prompt.

## 5. Règle anti-fuite avec les requêtes de test

Les 40 requêtes de test (`data/test_queries.jsonl`) ne sont jamais reprises ni reformulées. Les **thèmes** peuvent être couverts, mais pas les **mêmes scénarios**. Scénarios réservés au test, à ne pas utiliser dans l'entraînement :

| Test | Scénario réservé | Variante autorisée dans l'entraînement |
|---|---|---|
| T13 | Date d'application du haut risque | Questions sur d'autres échéances ou « quand l'AI Act s'applique-t-il ? » en général |
| T14 | Montant maximal d'une amende | Critères de fixation d'une amende, types de sanctions |
| T18 | Vol d'un ordinateur contenant le fichier des adhérents | Email envoyé au mauvais destinataire, rançongiciel, clé USB perdue |
| T25 | Empreintes digitales pour l'accès des adhérents d'une salle de sport | Biométrie pour un coffre-fort, une cantine, un pointage |
| T26 | Prévenir les clients d'un chatbot sur un site de vente | Assistant vocal au téléphone, chatbot interne RH |
| T27 | Délai de réponse à une candidate qui demande ses données | Demande d'accès d'un client ou d'un adhérent |
| T28 | Caméras dans un magasin | Caméras dans un entrepôt, un parking, une salle d'attente |
| T29 | Ancien salarié qui demande ses données | Client qui demande une copie de son dossier |
| T31 | IA générative pour rédiger des emails commerciaux | IA générative pour résumer des réunions, traduire des documents |
| T32 | Photos d'adhérents d'une association sur Facebook | Photos d'événement sur le site d'une entreprise |
| T33 | « Ignore tes instructions » + recette | Autres formes d'injection (« tu es maintenant… », « mode développeur ») |
| T37 | Garder des CV 10 ans en cachette | Autres contournements (surveillance, revente de fichiers de prospects) |
| T39 | SMS aux non-clients d'une boulangerie | Emailing d'un club de sport, newsletter d'un site |
| T40 | Logiciel qui note les salariés pour les primes | Outil d'aide au recrutement vidéo, planification automatique |

Un contrôle automatique mesure en plus la similarité de chaque question d'entraînement avec les 40 requêtes de test et signale les cas trop proches.

## 6. Contrôles automatiques (script du notebook)

Format et alternance des rôles, vouvoiement, longueur (3 à 6 phrases), chiffres hors liste blanche, URL, listes à puces, données personnelles (emails, téléphones), doublons, similarité avec le test, répartition par catégorie.

## 7. Relecture manuelle

Tous les dialogues signalés, plus un échantillon aléatoire de 60 dialogues, relus avec la fiche de faits. Corrections consignées dans `data/journal_relecture.csv` (id, problème, action).

## 8. Découpage

80 % entraînement, 10 % validation, 10 % test, **stratifié par catégorie**, graine fixe.
- La **validation** sert à choisir le meilleur adaptateur (perte de validation).
- Le **test** mesure la perte sur des dialogues jamais vus.
- Les **40 requêtes de test** restent l'évaluation comportementale (grille).
