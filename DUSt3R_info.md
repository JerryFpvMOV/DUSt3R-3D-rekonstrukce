# DUST3R + Fotogrammetrie  
## Úvod (GIS / dálkový průzkum Země)

---

## Co budeme řešit

Cílem je ukázat, jak lze z obyčejných fotografií vytvořit 3D model.

Princip:

- vezmeme sadu snímků (mobil, dron, kamera)  
- algoritmus z nich dopočítá prostor  
- výsledkem je 3D reprezentace reality  

Výstupy mohou být:

- point cloud  
- depth map  
- 3D mesh  

Tento princip spadá do oblasti **fotogrammetrie**.

---

## Co je fotogrammetrie

Fotogrammetrie je metoda získávání prostorových informací z obrazových dat.

Základní princip:

- snímky mají překryv (overlap)  
- hledají se shodné body mezi snímky  
- rekonstruuje se poloha kamer  
- počítá se hloubka a 3D struktura  

Typické výstupy:

- DSM / DTM  
- ortofoto  
- 3D model  

Použití:

- mapování krajiny  
- stavebnictví  
- archeologie  
- monitoring změn (požáry, eroze)  
- urbanismus  

---

## Klasická fotogrammetrie

Nejčastější pipeline:

- SfM (Structure from Motion)  
- MVS (Multi-View Stereo)  

Nástroje:

- COLMAP  
- Agisoft Metashape  

Nevýhody:

- složitý workflow  
- vysoké výpočetní nároky  
- citlivost na kvalitu dat  

---

## Nový přístup (AI)

Moderní metody využívají deep learning:

- model se učí vztahy mezi snímky  
- nepotřebuje klasickou pipeline  
- funguje rychleji a jednodušeji  

Sem patří **DUST3R**.

---

## Co je DUST3R

DUST3R je model založený na deep learningu pro rekonstrukci 3D scény ze snímků.

---

## Co DUST3R dělá

- odhaduje hloubku (depth) pro každý pixel  
- propojuje více snímků do jednoho prostoru  
- vytváří point cloud  

Výsledek:

- rychlá 3D rekonstrukce  
- použitelná i pro méně kvalitní data  

---

## Výhody a limity

### Výhody

- jednoduché použití  
- rychlé výsledky  

### Limity

- nižší přesnost než klasická fotogrammetrie  
- horší kontrola nad procesem  
- bez georeference (nutno řešit zvlášť)  

---

## Použití v GIS a DPZ

DUST3R lze využít jako doplněk ke klasickým metodám:

- rekonstrukce menších objektů  
- rychlá vizualizace  

Další zpracování:

- export point cloudu  
- analýza 
- georeference

---

## Jak je DUST3R dostupný

### Google Colab

- běží v cloudu  
- není potřeba GPU  
