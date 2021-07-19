Access to mBodyMap using python through APIs

## Table of contents
<!-- MDTOC maxdepth:6 firsth1:1 numbering:0 flatten:0 bullets:1 updateOnSave:1 -->

   - [Table of contents](#table-of-contents)
   - [Install and load required libraries](#install-and-load-required-libraries)
   - [Body sites](#bodysites)
      - [Get all body sites and statistics](#get-all-body-sites-and-statistics)
      - [Get associated phenotypes of a body site](#get-associated-phenotypes-of-a-body-site)
      - [Get associated species of a body site](#get-associated-species-of-a-body-site)
      - [Get associated genera of a body site](#get-associated-genera-of-a-body-site)
      - [Get associated projects of a body site](#get-associated-projects-of-a-body-site)
      - [Get associated runs of a body site](#get-associated-runs-of-a-body-site)
      - [Get associated species/genera prevalence of a body site](#get-associated-species/genera-prevalence-of-a-body-site)
      - [Get calculated relative species/genera abundance of a body site](#get-calculated-relative-species/genera-abundance-of-a-body-site)
   - [Phenotypes](#phenotypes)
      - [Get all phenotypes and statistics](#get-all-phenotypes-and-statistics)
      - [Get associated body sites of a phenotype](#get-associated-body-sites-of-a-phenotype)
      - [Get associated species of a phenotype in a body site](#get-associated-species-of-a-phenotype-in-a-body-site)
      - [Get associated genera of a phenotype in a body site](#get-associated-genera-of-a-phenotype-in-a-body-site)
      - [Get associated projects of a phenotype in a body site](#get-associated-projects-in-a-body-site)
      - [Get associated runs in a body site](#get-associated-runs-in-a-body-site)   
   - [Species/genera](#speciesgenera)
      - [Get an overview of the species](#get-an-overview-of-the-species)
      - [Get an overview of the genera](#get-an-overview-of-the-genera)
   - [Projects and runs](#projects-and-runs)
      - [Get projects](#get-peojects)
      - [Get runs](#get-runs)

<!-- /MDTOC -->

=======

## Install required modules
Please install the following required modules:
```python
## --install requests
import os
count = 2
while count:
    try:
        import requests
        print('importing module requests...done!')
        break
    except:
        print('Cannot find module named requests, installing...')
        os.system('pip install requests')
        count -= 1
        continue

## --install json
import os
count = 2
while count:
    try:
        import json
        print('importing module json...done!')
        break
    except:
        print('Cannot find module named json, installing...')
        os.system('pip install json')
        count -= 1
        continue

```

```bash
## -- simply install all of them without checking:
## run in your terminal --
pip install requests
pip install json
```

Load required modules:
```python
import requests
import json
```

## Body sites
### Get all body sites and statistics
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllBodySites'
body_01 = requests.get(url)

## -- a Object --
body_01_data = body_01.json().get('allBodySites')
```
### Get associated phenotypes of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getPhenotypesOfOneBodySite'
body_02 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_02_data = body_02.json().get('phenotypesOfLung')
```
### Get associated species of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getSpeciesOfOneBodySite'
body_03 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_03_data = body_03.json().get('speciesOfLung')
```
### Get associated genera of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getGeneraOfOneBodySite'
body_04 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_04_data = body_04.json().get('generaOfLung')
```
### Get associated projects of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjectsOfOneBodySite'
body_05 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_05_data = body_05.json().get('projectsOfLung')
```
### Get associated runs of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRunsOfOneBodySite'
body_06 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_06_data = body_06.json().get('runsOfLung')
```
### Get associated species/genera prevalence of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRunsOfOneBodySite'
body_07 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_07_genera_data = body_07.json().get('generaPrevalenceOfLung')
body_07_species_data = body_07.json().get('speciesPrevalenceOfLung')
```
### [Get calculated relative species/genera abundance of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRelativeAbundanceOfOneBodySite'
body_08 = requests.get(url, params={'site': 'Lung'})

## -- a Object --
body_08_genera_data = body_08.json().get('generaRelativeAbundanceOfLung')
body_08_species_data = body_08.json().get('speciesRelative_abundanceOfLung')
```

## Phenotypes
### Get all phenotypes and statistics
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllPhenotypes'
pheno_01 = requests.get(url)

## -- a Object --
pheno_01_data = pheno_01.json().get('allPhenotypes')
```
### Get associated body sites of a phenotype
Using the corresponding MeSH ID (e.g. D006262 for Health )

`input`: `phenotype`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getBodySitesOfOnePhenotype'
pheno_02 = requests.get(url, params={'phenotype': 'D006262'})

## -- a Object --
pheno_02_data = pheno_02.json().get('bodySitesOfD006262')
```
### Get associated species of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getSpeciesOfOnePhenotypeInOneBodySite'
pheno_03 = requests.get(url, params={'phenotype': 'D006262', 'site': 'Lung'})

## -- a Object --
pheno_03_data = pheno_03.json().get('speciesOfD006262InLung')
```
### Get associated genera of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getGeneraOfOnePhenotypeInOneBodySite'
pheno_04 = requests.get(url, params={'phenotype': 'D006262', 'site': 'Lung'})

## -- a Object --
pheno_04_data = pheno_04.json().get('generaOfD006262InLung')
```
### Get associated projects of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjectsOfOnePhenotypeInOneBodySite'
pheno_05 = requests.get(url, params={'phenotype': 'D006262', 'site': 'Lung'})

## -- a Object --
pheno_05_data = pheno_05.json().get('projectsOfD006262InLung')
```
### Get associated runs in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRunsOfOnePhenotypeInOneBodySite'
pheno_06 = requests.get(url, params={'phenotype': 'D006262', 'site': 'Lung'})

## -- a Object --
pheno_06_data = pheno_06.json().get('runsOfD006262InLung')
```

## Species/genera
### Get an overview of the species
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllSpecies'
all_species = requests.get(url)

## -- a Object --
all_species_data = all_species.json().get('allSpecies')
```
### Get an overview of the genera
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllGenera'
all_genera = requests.get(url)

## -- a Object --
all_genera_data = all_genera.json().get('all_genera')
```

## Projects and runs
### Get projects
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjects'
projects = requests.get(url)

## -- a Object --
projects_data = projects.json().get('projects')
```
### Get runs
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRuns'
runs = requests.get(url)

## -- a Object --
runs_data = runs.json().get('runs')
```
