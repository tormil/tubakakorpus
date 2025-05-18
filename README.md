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

> **Eeldused**: R ≥ 4.3, Jupyter Lab (Python 3.11 + `IRkernel`), ning R‑paketid `digar.txts`(mida saab ainult läbi JupyterLab'i/RaRa digilabori), `tidyverse`, `tidytext`, `top2vec`, `stringdist`, `data.table` jpt.

------------------------------------------------------------------------

## 2. Failide ja teemade ülevaade

### 2.1 RMarkdowni tööharud ("branch\_…\*.Rmd")

| Fail | Fookus/teema |
|-----------------------|-------------------------------------------------|
| **tubakakorpus.Rmd** | PEAMINE "MASTER", kuhu koondub puhastatud andmestik ja lõplik graafikute genereerimine ning ka osaliselt korpuse koostamise retsept: päring DIGAR‑ist, puhastus‑/filtriloogika ja analüüs. |
| Fail | Harud/iteratsioonid, mis olen alles jätnud |
| **branch_bakat66top2vecrtest+stopptykid.Rmd** | Top2Vec‑i testid ja käsitsi puhastamise (stopptykid) katse korpusega. |
| **branch_bakat66 fuzzy matching trial.Rmd** | „Fuzzy” tekstilise vastavuse katse, et siduda reklaame ettevõtte‑ID‑dega. Varasemad katsed olid ka fuzzy matching põhimõttel tehtud, aga lihtsalt käsitsi proovitud erinevaid regex metamärke. |
| **branch_bakat66_konkordants_pohjendus.Rmd** | Põhjendus konkordantsipõhise lähenemise valikust: kuidas lehekülg‐ja‐kontekst‑ekstrakt aitab artikleid reklaamidena tuvastada. Siia kuulub ka Joonis 3. Reklaamisegmendi teksti pikkused tähemärkide numbrite arvuna. |
| **branch_bakat66_suitsu_pohjendus.Rmd** | Analüüs, miks „suitsuvabad“ tooted (nt närimistubakas) esimeses faasis kõrvale jäeti; võrdlused reklaamimustritega. |
| **branch_vana_ettevotte_analyys_bakat66.Rmd** | Varane/"vana" katse ettevõtete tasemel trendide leidmiseks; hoitud alles reproducibility huvides. |

### 2.2 Jupyter Notebookid ("\*.ipynb")

| Fail | Fookus/teema |
|-------------------------|----------------------------------------------|
| **Tubakaandmestik_loputoo.ipynb** | Korpuse koostamise retsept: päring DIGAR‑ist, puhastus‑/filtriloogika ja analüüs. |
| **branch_ilmasuitsutaTubakaandmestik_loputoo-Copy1.ipynb** | Paralleelharu korpuse versioonist, kust regulaaravaldis "suits" eemaldatud; võimaldab kontrollida, kuidas see mõjutab trendijooni. |

------------------------------------------------------------------------

## 3. Kaustastruktuur (kui kloonid Git‑ist)

```         
/
├── andmestik/            # 🔒 ei ole Git‑is; toored CSV tabelid
├── kood/            # ülal loetletud *.Rmd ja *.ipynb failid
├── logid vms/               # idk
└── plottide pngd/        # kõik automaatselt salvestatavad pildid & graafikud
```

------------------------------------------------------------------------

## 4. Andmeallikad ja litsentsid

-   **DEA DIGARi ajalehe‑korpus** (Eesti Rahvusraamatukogu digilabor). https://digilab.rara.ee/tooriistad/ligipaas-dea-tekstidele/ Kasutustingimused võimaldavad teadus‑ ja õppetööd; kaubanduslik kasutus vajab eraldi luba.
-   Kood on litsentseeritud ?????????

------------------------------------------------------------------------

## 5. Analüüsi kordus ("reproducibility")

1.  **Laadi andmed** kausta `kood/` (vt. `tubakakorpus.Rmd`, kus on allalaadimis‑URL‑id).
2.  **Käivita** `renv::restore()` või `conda env create -f environment.yml` vastavalt oma eelistusele.
3.  Ava:
    -   **`Tubakaandmestik_loputoo.ipynb`**
    -   **`tubakakorpus.Rmd`**
4.  Pane tähele seadeid `params`‑plokis; mõned failid eeldavad tee‑muutuja (`data_dir`) määramist.

------------------------------------------------------------------------

## 6. Kontakt

**Autor**: Tormi Lust\
*E‑post*: tormilust@hotmail.com

Kui avastad vigu või sul on ettepanekuid – tee **Pull Request** või ava **Issue**.

------------------------------------------------------------------------

> *Viimati uuendatud: 18. mai 2025.*
