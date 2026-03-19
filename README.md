# La hausse des prix de l'électricité a-t-elle changé les habitudes des Français ?
### Analyse EDA — Python · Données officielles RTE, SDES et CRE (2012-2023)

---

## 🎯 Contexte et objectif

En arrivant en France en 2023, deux choses ont immédiatement 
attiré mon attention.

La première : tout le monde parlait de sa facture d'électricité. 
Les voisins, les commerçants, les gens dans la rue — la hausse 
des prix était dans toutes les conversations, et elle l'est encore 
aujourd'hui. Entre la guerre en Ukraine, la crise du parc nucléaire 
français en 2022 et un marché européen où le prix du gaz entraîne 
mécaniquement celui de l'électricité, les factures ont explosé 
partout sur le continent.

La deuxième : une publicité de plus en plus présente pour 
l'installation de panneaux solaires. Sur les routes, à la télévision, 
dans les boîtes aux lettres — comme si toute la France s'équipait 
du jour au lendemain.

Ces deux observations m'ont donné envie de comprendre ce qui se 
passait vraiment derrière ces tendances. Ce projet est le résultat 
de cette exploration — j'ai analysé 10 ans de données officielles 
pour répondre à mes questions.

---

## ❓ Questions analysées

**Question 1** — Face à des factures qui explosent, les Français 
ont-ils vraiment changé leur façon de consommer — et où en France 
l'impact est-il le plus fort ?

**Question 2** — Face à cette hausse, la France se tourne-t-elle 
vraiment vers le solaire ? La publicité reflète-t-elle une réalité 
dans les données ?

---

## 📊 Analyse 1 — Prix et comportement des ménages

> ⚡ **En 10 ans, le prix du kWh a augmenté de +71.7%.**
> De 0.1263 € en 2012 à 0.2169 € en 2023.
>
> *Le kWh (kilowatt-heure) est l'unité qui apparaît sur ta facture
> d'électricité — c'est l'énergie consommée par un appareil de 1000W
> pendant 1 heure. Le prix TTC (Toutes Taxes Comprises) est le prix
> réel payé par les ménages, taxes incluses.*

### Pourquoi les prix ont-ils autant augmenté ?

| Année | Prix du kWh TTC | Événement clé |
|-------|----------------|---------------|
| 2012 | 0.1263 € | Référence de départ |
| 2014 | 0.1401 € | Post-Fukushima + hausse taxes (+10% sur 2013-2015) |
| 2016 | 0.1503 € | Continuation rattrapage coûts nucléaires |
| 2019 | 0.1528 € | Rattrapage post-gel Gilets Jaunes (+5.9%) |
| 2020 | 0.1552 € | Correction résiduelle post-gel 2019 (+2.4%) |
| 2021 | 0.1570 € | Début crise énergétique |
| 2023 | 0.2169 € | Pic historique — guerre Ukraine + crise nucléaire |

### Ce que les données révèlent

| Année | Prix du kWh TTC | Conso. résidentielle | Conso. nationale |
|-------|----------------|---------------------|------------------|
| 2012 | 0.1263 € | 166.6 TWh | 487 TWh |
| 2013 | 0.1329 € | 172.6 TWh | 492 TWh |
| 2014 | 0.1401 € | 154.2 TWh | 462 TWh |
| 2015 | 0.1437 € | 159.0 TWh | 473 TWh |
| 2016 | 0.1503 € | 163.7 TWh | 480 TWh |
| 2017 | 0.1466 € | 159.4 TWh | 479 TWh |
| 2018 | 0.1458 € | 157.3 TWh | 476 TWh |
| 2019 | 0.1528 € | 156.7 TWh | 470 TWh |
| 2020 | 0.1552 € | 158.4 TWh* | 447 TWh* |
| 2021 | 0.1570 € | 166.7 TWh | 469 TWh |
| 2022 | 0.1740 € | 152.6 TWh | 450 TWh |
| 2023 | 0.2169 € | 148.0 TWh | 436 TWh |

*\*2020 : baisse ponctuelle liée aux confinements COVID,
non représentative d'un changement de comportement face aux prix.*

**Variation 2012-2023 :**
- Prix du kWh : **+71.7%**
- Consommation résidentielle : **-11.2%**
- Consommation nationale : **-10.5%**

**Variation 2021-2023 (crise) :**
- Prix du kWh : **+38.2%**
- Consommation résidentielle : **-11.2%**
- Consommation nationale : **-7.0%**

### L'insight clé — deux chocs distincts

**Choc 1 — 2019 : un choc politique français**
Fin 2018, face au mouvement des Gilets Jaunes, le gouvernement
gèle les tarifs d'électricité. En juin 2019, le gel est levé —
rattrapage brutal de +5.9% en un seul mois.

**Choc 2 — 2021-2023 : un choc international**
Guerre en Ukraine + crise nucléaire française = +38.2% en 2 ans.
Quand le prix a bondi de **+38.2% en seulement 2 ans**,
la consommation résidentielle a chuté de **-11.2%**.

👉 **Conclusion** : ce n'est pas la hausse progressive qui change
les comportements. C'est le choc brutal des prix qui force
les ménages à agir — et ils l'ont fait plus vite que les industries
(-11.2% vs -7.0%).

### Par région — qui a le plus changé ?

| Région | Variation 2013-2023 | Explication |
|--------|---------------------|-------------|
| Île-de-France | **-16.5%** | Télétravail + désindustrialisation |
| Normandie | -14.8% | Réduction activité industrielle |
| Grand Est | -14.0% | Industrie lourde en baisse |
| PACA | -9.5% | Dans la moyenne nationale |
| Bretagne | **-6.5%** | Économie résidentielle résiliente |
| Occitanie | -5.1% | Croissance démographique compensatrice |

👉 **Conclusion** : l'impact de la hausse des prix n'est pas
uniforme sur le territoire. Les régions industrielles comme
Île-de-France, Normandie et Grand Est ont le plus réduit leur
consommation — portées par le télétravail et la baisse de
l'activité industrielle. À l'inverse, Bretagne résiste grâce
à son économie résidentielle et agricole peu sensible aux
crises industrielles, et Occitanie grâce à sa forte croissance
démographique qui compense les efforts de sobriété.

---

## ☀️ Analyse 2 — La transition solaire est-elle réelle ?

### Ce que les données révèlent

La production solaire nationale a augmenté de **+489%**
entre 2012 et 2023 — de ~450 MW à ~3 100 MW.

| Période | Tendance | Explication |
|---------|----------|-------------|
| 2012-2018 | Croissance lente | Panneaux encore très chers |
| 2019-2020 | Ralentissement | Prix électricité encore abordables |
| 2021-2023 | **Accélération forte** | Crise énergétique + MaPrimeRénov' + panneaux ÷10 depuis 2010 |

👉 **Conclusion** : oui, la transition est réelle. Et paradoxalement,
c'est la même crise qui a fait exploser les factures qui a
accéléré l'adoption du solaire — la publicité ne mentait pas.

### Par région — qui produit le plus ?

| Rang | Région | Production 2023 |
|------|--------|-----------------|
| 🥇 | Nouvelle-Aquitaine | ~630 MW |
| 🥈 | Occitanie | ~520 MW |
| 🥉 | PACA | ~355 MW |
| ⚠️ | Île-de-France | ~35 MW |

**Résultat contre-intuitif** : Nouvelle-Aquitaine devance
Occitanie et PACA malgré un ensoleillement inférieur —
grâce à sa superficie (plus grande région de France)
qui offre plus de surfaces disponibles.

👉 **Conclusion** : la transition solaire est inégale selon
les régions. Le Sud et l'Ouest dominent la production —
mais c'est la superficie disponible, et non uniquement
l'ensoleillement, qui fait la différence.

> **Note méthodologique** : la production solaire analysée
> inclut particuliers + entreprises + collectivités.
> Les données solaires résidentielles seules ne sont pas
> disponibles en open data officiel.

---

## 🔗 Le fil conducteur
```
💸 Prix électricité +71.7% en 10 ans
        ↓
🏠 Ménages réduisent consommation -11.2%
   (1.6x plus que les industries)
        ↓
☀️ France adopte le solaire +580%
   (accéléré par la même crise)
        ↓
📍 Mais de façon très inégale selon les régions
```

---

## 🛠️ Outils et données

- **Python** — pandas, matplotlib
- **Jupyter Notebook**
- **4 datasets** — 485 184 enregistrements nationaux +
  2 311 260 régionaux + prix CRE + consommation résidentielle SDES

---

## 📚 Sources officielles

| Source | Données | Lien |
|--------|---------|------|
| RTE | Consommation et production nationale | https://opendata.reseaux-energies.fr |
| RTE | Données régionales | https://opendata.reseaux-energies.fr |
| RTE | Bilan électrique 2022 | https://www.rte-france.com/actualites/bilan-electrique-2022 |
| SDES | Consommation résidentielle 1990-2023 | https://www.statistiques.developpement-durable.gouv.fr/consommation-denergie-par-usage-du-residentiel |
| CRE | Tarifs réglementés particuliers | https://www.data.gouv.fr/datasets/historique-des-tarifs-reglementes-de-vente-delectricite-pour-les-consommateurs-residentiels |
