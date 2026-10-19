BOUSSOLE RGPD - INSTRUCTIONS D'EXECUTION
=========================================

Agent conversationnel RGPD et AI Act, construit a partir de Qwen3-4B-Instruct-2507
et adapte par QLoRA. Mini-projet.
Auteur : Sofiane Ait El Hadj


1. CONTENU DU RENDU
-------------------
agent.ipynb      Notebook execute, organise de l'installation a l'interface (parties 0 a 7).
rapport.pdf      Rapport de 4 pages.
data/            Donnees creees : fiche de faits, dialogues, decoupage train/val/test,
                 requetes de test, fichiers de relecture.
eval/            Resultats : baselines, courbes de perte, reponses generees,
                 indicateurs automatiques, notation a l'aveugle.
Adaptateur LoRA  https://huggingface.co/sofianeAit/boussole-rgpd-lora
                 (fichiers adapter_model.safetensors et adapter_config.json)


2. ENVIRONNEMENT
----------------
- Google Colab avec un GPU NVIDIA T4 (Execution > Modifier le type d'execution > GPU T4).
  Les parties 2, 3, 5, 6 et 7 ont besoin du GPU ; la partie 4 fonctionne sur CPU.
- Les bibliotheques sont installees par le notebook : transformers, accelerate, peft,
  bitsandbytes, datasets, scikit-learn, pandas, matplotlib, gradio.
- Le modele de base (environ 8 Go) est telecharge automatiquement depuis Hugging Face
  au premier chargement.


3. EXECUTION COMPLETE
---------------------
1. Ouvrir agent.ipynb dans Google Colab et choisir un runtime GPU T4.
2. Dans le panneau Fichiers, creer un dossier data/ et y importer le contenu du dossier
   data/ du rendu. Pour la comparaison avec la premiere baseline (partie 3.7), importer
   aussi eval/qwen2.5-1.5b/ dans un dossier eval/.
3. Executer les cellules dans l'ordre, de la partie 0 a la partie 7.

Durees indicatives sur un T4 :
- parties 2 et 3 (observation et baseline) : environ 30 minutes ;
- partie 4 (preparation des donnees) : quelques minutes ;
- partie 5 (entrainement QLoRA) : environ 20 minutes (18 minutes d'entrainement) ;
- partie 6 (generation des 120 reponses de test) : environ 30 minutes ;
- partie 7 (interface) : 1 minute.

Remarques :
- Le modele de base en demi-precision (parties 2 et 3) et le modele quantifie en 4 bits
  (parties 5 a 7) ne tiennent pas ensemble en memoire : la partie 5 libere le premier
  avant de charger le second.
- La relecture (partie 4.3) et la notation a l'aveugle (partie 6.4) sont des etapes
  manuelles : les fichiers deja remplis sont fournis (data/relecture.csv et
  eval/notation_aveugle.csv), donc les cellules suivantes s'executent directement.
- Pour des raisons de quota GPU, le notebook rendu a ete execute en plusieurs sessions
  Colab successives, toujours dans l'ordre des parties.


4. LANCER SEULEMENT L'INTERFACE (SANS REENTRAINER)
--------------------------------------------------
1. Runtime GPU T4.
2. Executer la partie 0 (installation et imports) et la cellule des prompts (partie 3.1).
3. Telecharger l'adaptateur :
       from huggingface_hub import snapshot_download
       snapshot_download("sofianeAit/boussole-rgpd-lora",
                         local_dir="adapters/boussole-rgpd-lora")
4. Executer la cellule de la partie 7 : elle charge le modele de base en 4 bits et
   l'adaptateur, puis lance l'interface Gradio. Un lien public temporaire
   (https://....gradio.live) s'affiche.


5. REPRODUCTIBILITE
-------------------
- Graine fixe (42) pour le decoupage des donnees, l'entrainement et la notation.
- Decodage glouton (deterministe) pour toutes les evaluations.
- Hyperparametres de l'adaptateur : partie 5.3 du notebook et fichier hyperparametres.json
  de l'adaptateur sur Hugging Face.
- De legeres differences peuvent apparaitre d'une machine a l'autre (calculs en
  demi-precision sur GPU).
