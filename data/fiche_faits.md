# Fiche de faits de référence — Boussole RGPD

Cette fiche est la **source de vérité** du jeu de données. Chaque dialogue d'entraînement ne peut s'appuyer que sur les faits listés ici, et chaque fait porte un identifiant (F01, F02…) repris dans les métadonnées des dialogues.

**Liste blanche des chiffres.** Seuls les chiffres marqués 🔢 peuvent apparaître dans une réponse de l'agent. Tout autre chiffre (date, montant, délai, numéro d'article) est interdit dans les données et signalé par le contrôle automatique.

**Sources.** RGPD : règlement (UE) 2016/679. AI Act : règlement (UE) 2024/1689, modifié en 2026 par le règlement dit « Digital Omnibus ». Recommandations de la CNIL (cnil.fr). Faits vérifiés le 27/09/2026.

---

## A. Notions de base

**F01 — Donnée personnelle.** Toute information se rapportant à une personne physique identifiée ou identifiable, directement (nom, photo) ou indirectement (adresse IP, numéro client, email, voix, plaque d'immatriculation). *RGPD art. 4.*

**F02 — Traitement.** Toute opération sur des données personnelles : collecte, enregistrement, organisation, conservation, consultation, utilisation, communication, effacement… **automatisée ou non**. Le RGPD s'applique aussi aux **fichiers papier** dès lors que les données sont organisées dans un fichier (classeur de fiches clients, dossiers du personnel). *RGPD art. 2 et 4.*

**F03 — Responsable de traitement et sous-traitant.** Le responsable de traitement décide pourquoi et comment les données sont traitées. Le sous-traitant traite les données pour son compte (hébergeur, prestataire de paie, éditeur de logiciel) et doit être lié par un contrat qui encadre ce traitement. *RGPD art. 4 et 28.*

**F04 — Données sensibles.** Origine raciale ou ethnique, opinions politiques, convictions religieuses ou philosophiques, appartenance syndicale, données génétiques, **données biométriques** servant à identifier une personne de façon unique, données de **santé**, vie sexuelle ou orientation sexuelle. Leur traitement est **interdit par principe**, sauf exceptions (consentement explicite, obligation en droit du travail, etc.). Les données bancaires **ne sont pas** des données sensibles au sens du RGPD, même si elles doivent être bien protégées. Les données d'infractions et de condamnations suivent un régime spécifique. *RGPD art. 9 et 10.*

**F05 — Anonymisation et pseudonymisation.** Des données **anonymisées** ne permettent plus, de façon irréversible, d'identifier quiconque : elles sortent du RGPD. Des données **pseudonymisées** (nom remplacé par un code, avec une table de correspondance) restent des données personnelles. Anonymiser suppose de retirer les identifiants directs **et** de limiter la réidentification (généraliser, agréger, supprimer les valeurs rares).

## B. Principes et bases légales

**F06 — Principes.** Licéité, loyauté et transparence ; limitation des finalités ; minimisation (ne collecter que le nécessaire) ; exactitude ; limitation de la durée de conservation ; intégrité et confidentialité (sécurité) ; responsabilité (pouvoir démontrer sa conformité). *RGPD art. 5.*

**F07 — Bases légales.** 🔢 **Six** bases légales : consentement, exécution d'un contrat, obligation légale, sauvegarde des intérêts vitaux, mission d'intérêt public, intérêts légitimes. Le consentement **n'est donc pas toujours nécessaire** : il n'est qu'une base parmi six. *RGPD art. 6.*

**F08 — Consentement valide.** Libre, spécifique, éclairé et univoque (acte positif clair, pas de case précochée). Il doit pouvoir être retiré aussi facilement qu'il a été donné. *RGPD art. 7.*

## C. Droits des personnes

**F09 — Droits.** Information, accès, rectification, effacement, limitation, portabilité, opposition, et droit de ne pas faire l'objet d'une décision entièrement automatisée produisant des effets importants. Toute personne peut aussi saisir la CNIL d'une plainte. *RGPD art. 12 à 22.*

**F10 — Délai de réponse.** 🔢 Répondre **dans un délai d'un mois** à compter de la réception de la demande, prolongeable de **deux mois** si la demande est complexe ou si elles sont nombreuses, en informant la personne. La réponse est gratuite en principe. On peut vérifier l'identité en cas de doute raisonnable. Le droit d'accès donne droit à une copie des données, sans porter atteinte aux droits des tiers. Ce droit s'applique à toute personne, y compris un **salarié ou ancien salarié**. *RGPD art. 12 et 15.*

## D. Obligations de l'organisme

**F11 — Registre des traitements.** Document interne qui recense les traitements : finalités, catégories de données et de personnes, destinataires, transferts, durées de conservation, mesures de sécurité. Une exemption existe pour les petites structures mais elle est très limitée : en pratique, la CNIL recommande à toutes les structures de tenir un registre. *RGPD art. 30.*

**F12 — DPO (délégué à la protection des données).** Obligatoire pour les autorités et organismes publics, et pour les organismes dont l'activité de base implique un suivi régulier et systématique des personnes à grande échelle, ou le traitement à grande échelle de données sensibles. Sinon, il est facultatif mais recommandé. *RGPD art. 37.*

**F13 — Analyse d'impact (AIPD).** Obligatoire avant un traitement susceptible d'engendrer un risque élevé pour les personnes (la CNIL publie une liste de traitements concernés). *RGPD art. 35.*

**F14 — Sécurité.** Mesures adaptées au risque : accès limité aux personnes habilitées, mots de passe robustes, chiffrement, sauvegardes, mises à jour, journalisation, sensibilisation du personnel, prudence avec les envois par email et les supports amovibles. La CNIL publie un guide de la sécurité des données. *RGPD art. 32.*

**F15 — Violation de données.** Perte, vol, fuite, accès non autorisé, destruction… 🔢 Notification à la CNIL dans les meilleurs délais et, si possible, **72 heures** au plus tard après en avoir pris connaissance, sauf si la violation n'est pas susceptible d'engendrer un risque. Information des personnes concernées si le risque est élevé. Toute violation doit être documentée en interne. *RGPD art. 33 et 34.*

**F16 — Transferts hors de l'Union européenne.** Encadrés : pays reconnu comme offrant une protection adéquate (décision d'adéquation), ou garanties appropriées comme les **clauses contractuelles types** de la Commission européenne. Pour les États-Unis, un cadre d'adéquation existe pour les entreprises certifiées ; sa situation juridique doit être vérifiée au moment du transfert. *RGPD chapitre V.*

**F17 — Sanctions.** 🔢 Amende administrative jusqu'à **20 millions d'euros ou 4 %** du chiffre d'affaires annuel mondial (le montant le plus élevé), ou **10 millions d'euros ou 2 %** pour certains manquements. Le montant dépend de nombreux critères : gravité, durée, nombre de personnes, mesures prises, coopération. La CNIL peut aussi prononcer un rappel à l'ordre, une mise en demeure ou une injonction. **L'agent n'estime jamais une sanction pour un cas précis.** *RGPD art. 83.*

## E. Situations pratiques

**F18 — Recrutement.** Ne collecter que les informations utiles pour évaluer les compétences (pas de numéro de sécurité sociale, de coordonnées bancaires, de situation familiale). Informer les candidats. 🔢 Pour les candidats non retenus, conservation possible **deux ans au maximum** après le dernier contact, s'ils en sont informés et ne s'y opposent pas. *Source : CNIL, recrutement dans les TPE/PME.*

**F19 — Prospection commerciale par email ou SMS.** Vers des **particuliers** : consentement préalable, sauf pour des clients existants et des produits ou services analogues, à condition qu'ils aient été informés et puissent s'opposer facilement à chaque message. Vers des **professionnels** : information et possibilité de s'opposer, avec un message en rapport avec leur profession. Un fichier acheté ne peut être utilisé que si les personnes ont consenti à être démarchées par des partenaires. *Source : CNIL.*

**F20 — Vidéosurveillance dans un lieu recevant du public.** Possible pour la sécurité des biens et des personnes. On peut filmer les entrées, les allées, les caisses, mais pas les toilettes ni les vestiaires, et pas les salariés en continu à leur poste de travail. 🔢 Conservation en principe **un mois** au maximum. Panneaux d'information visibles. Les zones ouvertes au public nécessitent une autorisation préfectorale. Accès aux images limité aux personnes habilitées ; représentants du personnel informés et consultés. *Source : CNIL, vidéosurveillance dans les commerces.*

**F21 — Surveillance des salariés.** Les salariés doivent être informés de tout dispositif de contrôle, et les représentants du personnel consultés. Le dispositif doit être justifié et proportionné. Une surveillance cachée est en principe illicite.

**F22 — Biométrie (empreintes, reconnaissance faciale).** Les données biométriques sont des données sensibles (F04) lorsqu'elles servent à identifier une personne de façon unique, ce qui est le cas d'un contrôle d'accès par empreinte ou par visage. La CNIL a une position restrictive : la biométrie doit répondre à un besoin réel, pas à une simple commodité. Pour des clients ou usagers, il faut une alternative non biométrique (badge, code) sans pénalité et un consentement spécifique ; le gabarit biométrique doit rester sous le contrôle de la personne (support individuel). Au travail, un règlement type de la CNIL encadre strictement ces dispositifs. Une analyse d'impact est en général nécessaire. *Source : CNIL.*

**F23 — Cookies et traceurs.** Consentement préalable pour les traceurs non essentiels (publicité, réseaux sociaux…). Refuser doit être aussi simple qu'accepter. Certains traceurs sont exemptés (panier, authentification, certaines mesures d'audience). *Source : CNIL.*

**F24 — Photos et droit à l'image.** L'image d'une personne identifiable est une donnée personnelle. Pour publier une photo où une personne est reconnaissable et isolée, il faut en principe son accord (celui des parents pour un mineur), l'informer, et retirer la photo si elle le demande.

**F25 — Outils d'IA générative et données.** Éviter de saisir des données personnelles ou confidentielles dans un outil en ligne non maîtrisé. Vérifier les conditions d'utilisation (réutilisation des données pour entraîner le modèle), la localisation des données et le contrat. Anonymiser ou pseudonymiser avant usage. Relire et vérifier les contenus produits. **Aucune obligation générale** n'impose de signaler qu'un email commercial a été rédigé avec l'aide d'une IA.

## F. AI Act

**F26 — Approche par les risques.** 🔢 **Quatre** niveaux : 1) risque **inacceptable** : pratiques interdites (notation sociale, manipulation, reconnaissance des émotions au travail ou à l'école, etc.) ; 2) **haut risque** : obligations renforcées ; 3) risque lié à la **transparence** : obligations d'information ; 4) risque **minimal** : pas d'obligation spécifique. Des règles propres s'appliquent aussi aux modèles d'IA à usage général.

**F27 — Haut risque.** Notamment : **emploi et gestion des travailleurs** (tri de CV, évaluation de candidats, décisions de promotion ou de rémunération, évaluation des performances), éducation et formation, accès aux services essentiels (dont l'évaluation de la solvabilité), **certains** systèmes biométriques, infrastructures critiques, justice, migrations. Un outil qui trie des CV ou évalue des salariés est donc en principe **à haut risque**.
**Attention : toute biométrie n'est pas « à haut risque » au sens de l'AI Act.** Sont visées notamment l'identification biométrique à distance, la catégorisation biométrique et la reconnaissance des émotions. Une simple vérification d'identité (une empreinte pour déverrouiller une porte ou un appareil) n'est **pas** en elle-même un système à haut risque au sens de l'AI Act, même si elle reste strictement encadrée par le RGPD (F22). L'agent ne doit donc pas confondre « donnée sensible » (RGPD) et « système à haut risque » (AI Act).

**F28 — Fournisseur et déployeur.** Le **fournisseur** développe le système et porte l'essentiel des obligations (documentation, gestion des risques, marquage CE). Le **déployeur** (par exemple une PME qui utilise l'outil) a des obligations plus légères : utiliser le système selon ses instructions, assurer une supervision humaine, informer les personnes concernées, en particulier les salariés.

**F29 — Transparence.** Les obligations dépendent du type de système et du rôle de l'organisme ; ce ne sont pas des règles générales pour tout usage de l'IA :
- **chatbot ou assistant conversationnel** : les personnes doivent être informées qu'elles échangent avec une IA, sauf si c'est évident ;
- **contenus hypertruqués (deepfakes)** : celui qui les diffuse doit indiquer qu'ils ont été générés ou manipulés artificiellement ;
- **marquage technique** des contenus générés (image, audio, vidéo, texte) : obligation qui pèse sur les **fournisseurs** des systèmes d'IA générative, pas sur la PME qui les utilise ;
- **reconnaissance des émotions ou catégorisation biométrique** (quand elles sont autorisées) : informer les personnes exposées.
Un texte ordinaire rédigé avec l'aide d'une IA (email commercial, compte rendu) n'a pas à être signalé comme tel (voir F25).

**F30 — Calendrier.** L'AI Act s'applique par étapes, et ce calendrier **a été modifié en 2026** par le règlement dit « Digital Omnibus », qui a notamment reporté les obligations des systèmes à haut risque. **L'agent ne cite aucune date d'application** : il signale que le calendrier a évolué et renvoie vers le site de la Commission européenne ou de la CNIL.
> 🚫 **Donnée de correction, exclue de la génération.** Ce bloc n'est jamais fourni comme fait utilisable pour écrire les dialogues, et le contrôle automatique signale toute date dans une réponse. *Pour la correction uniquement, jamais dans les réponses :* interdictions depuis le 2 février 2025 ; modèles à usage général depuis le 2 août 2025 ; transparence des chatbots depuis le 2 août 2026 ; haut risque de l'annexe III au 2 décembre 2027 ; annexe I au 2 août 2028.

**F31 — Cumul.** L'AI Act et le RGPD s'appliquent en même temps : un système d'IA qui traite des données personnelles doit respecter les deux.

## G. Ressources autorisées

**F32 — Orientation.** Site de la CNIL (cnil.fr, **sans URL détaillée inventée**), textes officiels (EUR-Lex), site de la Commission européenne, DPO, avocat spécialisé en protection des données. Pour les sujets hors périmètre : un expert-comptable, un avocat en droit du travail ou des affaires, les sites officiels de l'administration, **sans inventer de nom d'organisme**.
