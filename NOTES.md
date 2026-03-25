# 🧠 DUSt3R — poznámky pro prezentaci

---

## Co je DUSt3R

DUSt3R je AI model pro 3D rekonstrukci z fotografií.
Z několika běžných snímků stejné scény dokáže:

* odhadnout hloubku
* najít vztahy mezi obrázky
* rekonstruovat prostor
* vytvořit 3D model (point cloud / mesh)

👉 Jednoduše řečeno:
**vezme fotky a vytvoří z nich 3D scénu**

---

## Kde je v tom AI

AI je tady v samotném jádru řešení.

Klasická 3D rekonstrukce:

* potřebuje znát kamery (kalibraci, pozice)
* pak teprve počítá 3D

DUSt3R:

* rovnou odhaduje 3D body z obrázků
* nepotřebuje znát kamery předem

👉 AI tedy:

* nahrazuje část klasické geometrie
* umožňuje jednodušší použití
* funguje i na „běžných“ fotkách

---

## Co DUSt3R umí

* odhad hloubky (depth)
* rekonstrukce 3D bodů
* odhad pozic kamer
* nalezení shod mezi pixely (matching)
* spojení více obrázků do jedné scény

👉 výstup:

* point cloud
* nebo 3D mesh

---

## V čem je DUSt3R dobrý

* funguje bez kalibrace kamer
* stačí běžné fotografie
* rychlý vizuální výsledek
* ideální pro demonstraci AI + 3D

👉 vhodné pro:

* výuku
* experimenty
* rychlé prototypy

---

## Proč Google Colab

Google Colab je cloudové prostředí.

Výhody:

* není potřeba vlastní GPU
* není potřeba instalace
* vše běží na serverech Google
* stejné prostředí pro všechny

👉 důležité:
DUSt3R je výpočetně náročný → GPU je prakticky nutnost

---

## Co obsahuje můj GitHub

Repo obsahuje:

* README → vysvětlení projektu
* CODE → postup pro spuštění v Colabu
* data → ukázkové obrázky
* assets → preview výsledku

👉 cíl:
aby student jen otevřel Colab a spustil demo

---

## Vysvětlení kódu krok za krokem

---

### 1️⃣ Klonování projektu

```python
!git clone --recursive https://github.com/naver/dust3r
```

* stáhne celý projekt z GitHubu
* `--recursive` stáhne i submoduly

👉 vykřičník znamená: spouštím shell příkaz, ne Python

---

### 2️⃣ Instalace knihoven

```python
!pip install -r /content/dust3r/requirements.txt
```

* nainstaluje všechny potřebné balíčky
* připraví prostředí pro běh modelu

---

### 2.1️⃣ HEIC support

```python
!pip install -r /content/dust3r/requirements_optional.txt
```

* přidá podporu pro HEIC (iPhone fotky)
* * další doplňkové balíčky

---

### 3️⃣ Úprava demo (share=True)

```python
!sed -i 's/share=False/share=True/g' /content/dust3r/dust3r/demo.py
```

* změní `share=False` → `share=True`
* umožní vytvoření veřejného odkazu

👉 důležité:

* upravuje se **vnitřní soubor**
* ale spouští se jiný (horní)

---

### 4️⃣ Spuštění demo

```python
!python3 /content/dust3r/demo.py --model_name DUSt3R_ViTLarge_BaseDecoder_512_dpt
```

* spustí webovou aplikaci (Gradio)
* zobrazí link
* nahraješ obrázky
* vznikne 3D model

---

## Jak probíhá rekonstrukce

1. nahrajeme obrázky
2. vytvoří se páry snímků
3. AI spočítá 3D pointmapy
4. proběhne global alignment
5. vznikne výsledná 3D scéna

---

## Co znamenají prvky v UI

* **schedule** → průběh optimalizace
* **niter** → počet iterací
* **min_conf_thr** → filtr nejistých bodů

další:

* **As pointcloud** → zobrazí body
* **Mask sky** → odstraní oblohu
* **Clean-up depthmaps** → vyčistí data
* **Transparent cameras** → průhledné kamery

---

## Shrnutí

DUSt3R umožňuje vytvořit 3D scénu z obyčejných fotografií pomocí AI.

* nepotřebuje kalibraci kamer
* funguje na běžných datech
* ukazuje moderní přístup v computer vision

👉 ideální ukázka propojení:
AI + 3D + fotogrammetrie
