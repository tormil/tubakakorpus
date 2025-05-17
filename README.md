# Tubakakorpus
# Tubakareklaamide analüüsi tööprojekt

See repositoorium koondab minu bakalaureusetöö **„Eesti tubakareklaamid ajalehtedes 1920–1940“** käigus koostatud skriptid, andmetöötluse etapid ja vaheanalüüsid. Failid on siia kogunenud erinevatest tööharudest (branch‑idest) ning igaühel on oma fookus. Allpool on juhend, et leiaksid kiiresti üles, **kus miski asub ja mida see teeb**.

------------------------------------------------------------------------

## 1. Kiire stardijuhend

``` bash
# klooni reposti (eeldab Git‑i)
$ git clone <repo‑url>
$ cd tubakareklaamid‑1920‑40

# käivita RStudio projektis
# või ava Jupyter Notebookid, kui eelistad Python/R hübriidi
```

> **Eeldused**: R ≥ 4.3, Jupyter Lab (Python 3.11 + `IRkernel`), ning R‑paketid `digar.txts`(mida saab ainult läbi JupyterLab'i/RaRa digilabori), `tidyverse`, `tidytext`, `top2vec`, `stringdist`, `data.table` jpm.

------------------------------------------------------------------------

## 2. Failide ja teemade ülevaade

### 2.1 RMarkdowni tööharud ("branch\_…\*.Rmd")

| Fail | Fookus/teema |
|-----------------------|-------------------------------------------------|
| **tubakakorpus.Rmd** | PEAMINE "MASTER", kuhu koondub puhastatud andmestik ja lõplik graafikute genereerimine ning ka osaliselt korpuse koostamise retsept: päring DIGAR‑ist, puhastus‑/filtriloogika ja analüüs. |
| Fail | Harud/iteratsioonid, mis olen alles jätnud |
| **branch_bakat66top2vecrtest+stopptykid.Rmd** | Top2Vec‑i testid ja stoppsõnadeta katse korpusega. Uurib semantilisi klastreid ja visualiseerib reklaamide teemapilve. |
| **branch_bakat66 fuzzy matching trial.Rmd** | „Fuzzy” tekstilise vastavuse katse, et siduda reklaame ettevõtte‑ID‑dega, kasutades `stringdist`‑i ja Jaro‑Winkleri meetodit. |
| **branch_bakat66_konkordants_pohjendus.Rmd** | Põhjendus ja logi konkordantsipõhise lähenemise valikust: kuidas lehekülg‐ja‐kontekst‑ekstrakt aitab artikleid reklaamidena tuvastada. |
| **branch_bakat66_suitsu_pohjendus.Rmd** | Analüüs, miks „suitsuvabad“ tooted (nt närimistubakas) esimeses faasis kõrvale jäeti; võrdlused reklaamimustritega. |
| **branch_vana_ettevotte_analyys_bakat66.Rmd** | Varane/"vana" katse ettevõtete tasemel trendide leidmiseks; hoitud alles reproducibility huvides. |

### 2.2 Jupyter Notebookid ("\*.ipynb")

| Fail | Fookus/teema |
|-------------------------|----------------------------------------------|
| **Tubakaandmestik_loputoo.ipynb** | Korpuse koostamise retsept: päring DIGAR‑ist, puhastus‑/filtriloogika ja analüüs. |
| **branch_ilmasuitsutaTubakaandmestik_loputoo-Copy1.ipynb** | Paralleelharu korpuse versioonist, kust suitsuvabad tooted on *a priori* eemaldatud; võimaldab kontrollida, kuidas see mõjutab trendijooni. |

------------------------------------------------------------------------

## 3. Kaustastruktuur (kui kloonid Git‑ist)

```         
/
├── data/            # 🔒 ei ole Git‑is; toore CSV + JSON failid (alla laadida eraldi)
├── figs/            # kõik automaatselt salvestatavad pildid & graafikud
├── R/               # abifunktsioonid (.R) jagamiseks mitme skripti vahel
└── analysis/        # ülal loetletud *.Rmd ja *.ipynb failid
```

> *Märkus*: Hetkel on failid repoes juurkaustas. Kui teed `renv::init()` või `conda` keskkonna, soovitan need paigutada nagu ülal, et töövoog selgem oleks.

------------------------------------------------------------------------

## 4. Andmeallikad ja litsentsid

-   **DIGARi ajalehe‑korpus** (Eesti Rahvusraamatukogu). Kasutustingimused võimaldavad teadus‑ ja õppetööd; kaubanduslik kasutus vajab eraldi luba.
-   Kood on litsentseeritud MIT järgi, v.a. kui failis on teisiti märgitud.

------------------------------------------------------------------------

## 5. Analüüsi kordus ("reproducibility")

1.  **Laadi andmed** kausta `data/` (vt. `tubakakorpus.Rmd`, kus on allalaadimis‑URL‑id).
2.  **Käivita** `renv::restore()` või `conda env create -f environment.yml` vastavalt oma eelistusele.
3.  Ava kas:
    -   **`Tubakaandmestik_loputoo.ipynb`** – kui eelistad Jupyterit;
    -   **`branch_bakat66top2vecrtest+stopptykid.Rmd`** – kui tahad otse teemamodelleerimist R‑is.
4.  Pane tähele seadeid `params`‑plokis; mõned failid eeldavad tee‑muutuja (`data_dir`) määramist.

------------------------------------------------------------------------

## 6. Kontakt

**Autor**: Tormi Lust\
*E‑post*: tormilust@hotmail.com

Kui avastad vigu või sul on ettepanekuid – tee **Pull Request** või ava **Issue**.

------------------------------------------------------------------------

> *Viimati uuendatud: 17. mai 2025.*
