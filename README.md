# Fortnite – Historique complet des mises à jour (patches) par Chapitre/Saison  

Ce dépôt fournit un suivi chronologique **du Chapitre 1 → Chapitre 6**, trié par chapitre puis par saison, avec **toutes les versions de patch** et **leurs dates de déploiement** (lorsqu’elles sont connues publiquement).  
Les sources primaires sont les pages « Patch Notes » / « Saison » du **Fortnite Wiki (Fandom)** et, lorsqu’elles existent, les notes officielles d’Epic Games.  

## Contenu  
- `chapters/` : vue récapitulative par chapitre (Saisons, dates de début/fin, lien vers détail).    
- `seasons/` : une page par saison listant **toutes** les versions (vX.YY[.Z], « Content Update »…) et **la date exacte**.    
- `data/patches.csv` : export plat (chapitre, saison, version, date ISO 8601, type, URL source).    
- `scripts/scrape_patches.py` : script pour régénérer `patches.csv` et les `.md` à partir des pages du wiki.  

## Format CSV  
| chapter | season | season_code | patch_version | patch_type | release_date | source |  
|--------:|-------:|-------------|---------------|------------|--------------|--------|  
| 1 | 1 | ch1_s1 | v1.8 | Update | 2017-10-26 | https://fortnite.fandom.com/wiki/Season_1 |  
| 1 | 1 | ch1_s1 | v1.8.1 | Update | 2017-11-02 | https://fortnite.fandom.com/wiki/Season_1 |  
| … | … | … | … | … | … | … |  

> Remarque : certaines mises à jour « Content Update » sans binaire sont aussi incluses si datées.  

## Sources  
- Fortnite Wiki – **Season 1 (Chapitre 1)** : liste officielle des patches et dates (v1.8 → v1.10).    
- Fortnite Wiki – **Chapter 2 : Season 1** : v11.00 → v11.50 et dates détaillées.    
- Index « Patch Notes » (catégorie) pour navigation globale.    
- Notes Epic Games lorsque disponibles (ex. v2.2.0, v6.00).  

## Génération / mise à jour  

```
bash
python3 scripts/scrape_patches.py
```

Le script :  
1. parcourt les pages « Saison »/« Patch Notes » du wiki,    
2. extrait **version** + **date**,    
3. normalise les dates au format `YYYY-MM-DD`,    
4. écrit `data/patches.csv`,    
5. régénère les pages `chapters/*.md` et `seasons/*.md`.  

## Licence  
MIT – voir `LICENSE`. 
