# 📊 Analyse-des-Feedbacks-Communautaires-Sensibilisation-au-Mouvement-de-l-ONG

---

> **Titre du projet : Analyse des Feedbacks Communautaires — Sensibilisation au Mouvement de l'ONG** 

---

**Période :** 10– 29 octobre 2025 | Élection présidentielle du 12 octobre 2025

**Organisation :** ONG— Cellule d'Écoute et d'Analyse (CEA)

**Auteur :** Patricia — Data Analyst

**Outils :** QUALCODER (codification qualitative) • Microsoft Excel (matrice de données) • Jamovi (analyses statistiques) • Matplotlib/Seaborn (visualisations)

---

## Contexte du projet

Ce projet analyse 138 feedbacks communautaires collectés autour de l'élection présidentielle camerounaise du 12 octobre 2025, dans le cadre du mécanisme de redevabilité communautaire. L'objectif était de comprendre comment les populations perçoivent l’ONG concernée — ses missions, ses principes de neutralité et ses actions — dans un contexte électoral par nature sensible et propice à la circulation de rumeurs.

La collecte s'est étendue sur 14 jours : quelques jours avant le vote (10–11 octobre) et cinq jours après reparties sur une période de 12 jours (13–29 octobre). Les feedbacks ont été recueillis par les volontaires dans 10 régions du Cameroun, via des faces à face.


---

## 📋 Table des matières

├── README.md
├── data/
 ├── crc_feedback_electoraux.xlsx
 ├── verbatim_des_codes.xlsx  ← Verbatims codifiés QUACLODER
 ├── chart1_categories.jpg
 ├── chart2_sentiment.jpg
 ├── chart3_odds_ratio.jpg
 ├── chart4_temporal.jpg
 ├── chart5_milieu_langue.jpg
 ├── chart6_regions.jpg
 └── chart7_connaissance_confiance.jpg

---

## Méthodologie — Du qualitatif au quantitatif
 
Ce projet illustre une méthode rigoureuse de transformation de données qualitatives en données quantitatives analysables statistiquement. Voici les 9 étapes clés :

**1.Analyse qualitative initiale (QUALCODER).** 138 feedbacks codifiés en arborescence hiérarchique : 4 catégories principales, 21 sous-codes, variables socio-démographiques intégrées (Sexe, Tranche d'âge, Milieu, Langue, Diversité).

**2.Stabilisation du codebook.** Fusion des doublons, création de 7 méta-catégories pour l'analyse quantitative (CAT_RUMEURS, CAT_QUESTIONS, CAT_DEMANDES, CAT_POSITIF, CAT_SECURITE, SENTIMENT_CRC, CONNAISSANCE).

**3.Construction de la matrice Excel.** 25 variables structurées en 5 blocs : Identifiants (A-C), Géographie (D-F), Socio-démographie (G-K), Thématiques (L-R), Perception (S-Y).

**4.Codification et quantification.** Attribution des scores de sentiment (−2 à +2), variables binaires (0/1), formules automatisées (NB_CATEGORIES, JOUR_RELATIF, CONFIANCE_BINAIRE).

**5.Variables de contexte.** PERIODE (−1/0/+1), JOUR_RELATIF (−7 à +7), ZONE_CONFLIT (0/1), Indice de Confiance Institutionnelle (ICI, 0–100).

**6.Analyses descriptives Excel.** Tableaux de fréquences, KPIs (Taux de Confiance, Taux de Rumeurs, Score moyen de sentiment), tableaux croisés dynamiques.

**7.Import et configuration Jamovi.** Types de variables configurés (Nominal/Ordinal/Continu), étiquettes de valeurs, création de VULNERABILITE_BINAIRE.

**8.Analyses inférentielles (7 catégories).** Khi-deux (15 tests), Corrélations Spearman, Mann-Whitney (7 comparaisons), Régression logistique (3 modèles), ACM, ANOVA, Régression linéaire.

**9.Visualisations et restitution.** 7 graphiques Python (Matplotlib/Seaborn), 3 versions de rapport PowerPoint (Partenaires, CEA, Terrain).

---

## Principaux résultats


![Figure 1 : Répartition des 138 feedbacks par catégorie principale.](https://github.com/user-attachments/assets/d5e4b29f-aa79-4622-9546-a969e6c5647e)

                    Figure 1 : Répartition des 138 feedbacks par catégorie principale.


**Résultat 1 — La CRC comme filtre à rumeurs.** 64,5 % des messages portent sur des rumeurs, croyances ou observations. En contexte électoral, les populations utilisent l'ONG comme référence informationnelle — une opportunité institutionnelle unique.




![Figure 2 : Distribution du sentiment (score −2 à +2).](https://github.com/user-attachments/assets/56d65121-71ac-4f34-9297-d8ed4a13bbdf)

                    Figure 2 : Distribution du sentiment envers l'ONG (score −2 à +2).


**Résultat 2 — Sentiment légèrement positif et stable.** Score moyen de +0,30/2. 36,2 % de feedbacks positifs (confiance), 48,4 % neutres, 16,8 % négatifs (méfiance). Aucune variation significative sur les 19 jours de collecte.




![Figure 3 : Évolution temporelle du sentiment sur 19 jours (ANOVA : F=0,24, p=0,624 — stabilité prouvée).](https://github.com/user-attachments/assets/7e5d6655-27b4-4d34-9843-b9616433bf95)

                     Figure 3 : Évolution temporelle du sentiment sur 19 jours (ANOVA : F=0,24, p=0,624 — stabilité prouvée).
                     
**Résultat 3 — La connaissance prédit la confiance.** Seul prédicteur statistiquement significatif : la connaissance (OR=2,79, p=0,015). Une personne qui connaît la connait a 2,79 fois plus de chances de lui faire confiance.




![Figure  4 : Lien Connaissance → Confiance (OR=2,79 — résultat statistiquement prouvé).](https://github.com/user-attachments/assets/314aa8a0-9248-495d-a006-fa5e56635556)

Figure 4 : Lien Connaissance → Confiance (OR=2,79 — résultat statistiquement prouvé).



![ Figure 5 : Forest plot des Odds Ratios — facteurs prédicteurs de la confiance.](https://github.com/user-attachments/assets/960ca93e-9367-4132-9260-78369e08dbc1)

Figure 5 : Forest plot des Odds Ratios — facteurs prédicteurs de la confiance.

**Résultat 4 — Langue rurale = barrière d'accès.** Association très forte Milieu × Langue (χ²=41,3, p<0,001, V de Cramer=0,659) : zones rurales et langues locales sont indissociables. Toute communication uniquement en français exclut ces populations.




![Figure 6 : Association Milieu × Langue — résultat le plus fort de l'analyse (V=0,659, p<0,001).](https://github.com/user-attachments/assets/7d7269e7-f60d-4751-b506-c56128a1a46f)

Figure 6 : Association Milieu × Langue — résultat le plus fort de l'analyse (V=0,659, p<0,001).




![Figure 7 : Distribution géographique des feedbacks par analyse (H+F vs Groupe Mixte).](https://github.com/user-attachments/assets/fac09b59-61cd-417b-ae5b-66ffdcaddd2d)

Figure 7 : Distribution géographique des feedbacks par analyse (H+F vs Groupe Mixte).

**Résultat 5 — Groupe Mixte = zones à risque.** La Zone NOSO représente 16,3 % des feedbacks en Groupe Mixte vs 8,4 % en analyse individuelle. Dans les zones de conflit, les populations s'expriment collectivement plutôt qu'individuellement — signe de méfiance contextuelle.

---

## Recommandations opérationnelles

**1. Campagne multilingue ciblée.** Zones rurales Nord, Extrême-Nord, NOSO : développer des messages en Fulfuldé et Pidgin. Le lien milieu rural = langue locale est le résultat statistiquement le plus fort de l'analyse (V=0,659).

**2. Institutionnaliser le mécanisme CEA.** Transformer le dispositif électoral ponctuel en monitoring permanent mensuel. Objectif : 300 feedbacks individuels minimum par cycle pour atteindre la puissance statistique suffisante pour analyser les sous-groupes.

**3. Former les équipes terrain au protocole rumeurs.** 64,5 % des feedbacks portent sur des rumeurs. Créer une fiche de collecte dédiée (rumeur entendue, source, réaction communautaire) et former les agents à l'écoute active sans amplification.

**4. Valoriser la neutralité perçue.** La stabilité du sentiment sur 19 jours est un actif réputationnel démontré par les données. Communiquer explicitement sur cette neutralité dans les prochaines campagnes.

**5. Note sur la collecte des données de contact.** Les coordonnées de contact ont été intégrées au formulaire. La faible adoption (réticence des populations par crainte d'identification) est un enjeu de contexte terrain, non un défaut méthodologique. Des approches de collecte anonymisée ou via représentants communautaires sont à explorer.

---

## Limites de l'analyse

**•Taille d'échantillon.** N=95 pour l'analyse individuelle (H+F) limite la puissance statistique pour détecter des effets de taille modérée. Plusieurs tendances intéressantes (ρ=0,199 entre Connaissance et Sentiment, p=0,053) n'atteignent pas formellement le seuil de 0,05.

**•Langue non précisée.** 58,9 % des feedbacks H+F sans langue déclarée. Reflet de la réticence des populations à s'identifier, non d'une lacune du formulaire.

**•R² McFadden faible (0,004–0,095).** Le modèle prédictif capture une variance limitée. Des variables complémentaires (contact antérieur avec la CRC, type de sensibilisation reçue, source d'information) amélioreraient l'explication.

**•Représentativité géographique.** Surreprésentation de la zone Littoral/Ouest (51,6 %) et sous-représentation de Centre/Sud/Est (9,5 %). Les résultats reflètent les zones d'activité CEA active.

---

## Technologies utilisées

| Outil	| Usage	Version | Notes |
|---|---|---|
|**QUALCODER** | Codification qualitative des feedbacks |	| Version Web / Desktop |
| **Microsoft Excel** |	 Matrice de données, formules, KPIs |	Excel 365 |
| **Jamovi** |	Analyses statistiques inférentielles |	 v2.x — gratuit et open source |
| **Python / Matplotlib	Visualisations data / graphiques** |	Python 3.x, Matplotlib, Seaborn |
| **PowerPoint** |	Rapports de restitution (3 versions) |	Microsoft 365 |

---

## Compétences démontrées

Ce projet illustre un pipeline complet d'analyse data dans un contexte humanitaire :

•**Mixed-methods analysis.** Passage du qualitatif (QUALCODER) au quantitatif (Jamovi) avec rigueur méthodologique documentée

**•Statistical analysis.** Khi-deux, Spearman, Mann-Whitney, Régression logistique, ACM, ANOVA — avec interprétation critique des résultats

**•Data storytelling.** Traduction des résultats statistiques en langage accessible à 3 audiences distinctes (partenaires, CEA, terrain)

**•Humanitarian data standards.** Intégration de l'approche SADD (Sex, Age, Disability Disaggregation) — CHS compliant

**•Data visualization.** Forest plot, bar charts, pie charts, temporal analysis avec Matplotlib/Seaborn

**•Excel advanced.** RECHERCHEV, NB.SI.ENS, tableaux croisés dynamiques, formules de calcul d'indicateurs composites (ICI)

---

## Licence et contact

**Projet :**  Cellule d'Écoute et d'Analyse (CEA)

**Contexte :** Projet humanitaire — données anonymisées

**Auteur :** Patricia | Data Analyst 

**Répertoire :** github.com/[username]/crc-feedback-electoral-2025

Ce projet fait partie d'un portfolio de Data Analytics axé sur les données humanitaires et communautaires au Cameroun. Il démontre la capacité à transformer des données de terrain complexes en insights actionnables pour la prise de décision institutionnelle.

---

📄 Licence MIT
Copyright (c) 2026 BELINGUINE Patricia

L'autorisation est accordée, gracieusement, à toute personne acquérant une copie de ce logiciel
et des fichiers de documentation associés (le « Logiciel »), de l'utiliser sans restriction,
y compris sans limitation les droits d'utiliser, de copier, de modifier, de fusionner, de publier,
de distribuer, de sous-licencier et/ou de vendre des copies du Logiciel, et de permettre
aux personnes auxquelles le Logiciel est fourni de le faire, sous réserve des conditions suivantes :

La notice de copyright ci-dessus et la présente autorisation doivent être incluses dans toutes
les copies ou parties substantielles du Logiciel.

LE LOGICIEL EST FOURNI « EN L'ÉTAT », SANS GARANTIE D'AUCUNE SORTE, EXPRESSE OU IMPLICITE,
Y COMPRIS MAIS SANS S'Y LIMITER, LES GARANTIES DE QUALITÉ MARCHANDE, D'ADÉQUATION À
UN USAGE PARTICULIER ET D'ABSENCE DE CONTREFAÇON. EN AUCUN CAS LES AUTEURS OU TITULAIRES
DU DROIT D'AUTEUR NE POURRONT ÊTRE TENUS POUR RESPONSABLES D'UNE RÉCLAMATION, DOMMAGES
OU AUTRE RESPONSABILITÉ, QUE CE SOIT DANS LE CADRE D'UN CONTRAT, D'UN DÉLIT OU AUTRE,
DÉCOULANT DE, OU EN RELATION AVEC LE LOGICIEL OU L'UTILISATION OU AUTRES RAPPORTS AVEC LE LOGICIEL.

