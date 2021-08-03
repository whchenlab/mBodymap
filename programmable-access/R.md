Access to mBodyMap using R through APIs

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

## Install and load required libraries
Please install the following required libraries:
```R
## -- install httr
if( !requireNamespace("httr") ){
  install.packages( "httr" );
}

## -- simply install:
install.packages( c( "httr" ) );
```

Load required libraries:
```R
require("httr");
```

## Body sites
### Get all body sites and statistics
`input`: none,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllBodySitess'
body_01 = GET("https://mbodymap.microbiome.cloud/api/getAllBodySitess", body = list());

```
### Get associated phenotypes of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getPhenotypesOfOneBodySite'
body_02 = GET(url, query=list(site = "Lung"));

```
### Get associated species of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getSpeciesOfOneBodySite'
body_03 = GET(url, query=list(site = "Lung"))

```
### Get associated genera of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getGeneraOfOneBodySite'
body_04 = GET(url, query=list(site = "Lung"))

```
### Get associated projects of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjectsOfOneBodySite'
body_05 = GET(url, query=list(site = "Lung"))

```
### Get associated runs of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRunsOfOneBodySite'
body_06 = GET(url, query=list(site = "Lung"))

```
### Get associated species and genera prevalence of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getPrevalenceOfOneBodySite'
body_07 = GET(url, query=list(site = "Lung"))

```
### [Get calculated relative species and genera abundance of a body site
Using the corresponding body site  (e.g. `Lung`)

`input`: `body site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRelativeAbundanceOfOneBodySite'
body_08 = GET(url, query=list(site = "Lung"))

```

## Phenotypes
### Get all phenotypes and statistics
`input`: none,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllPhenotypes'
pheno_01 = GET(url)

```
### Get associated body sites of a phenotype
Using the corresponding MeSH ID (e.g. D006262 for Health )

`input`: `phenotype`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getBodySitesOfOnePhenotype'
pheno_02 = GET(url, query=list(phenotype = "D006262"))

```
### Get associated species of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getSpeciesOfOnePhenotypeInOneBodySite'
pheno_03 = GET(url, query=list(phenotype = "D006262", site = "Lung"))

```
### Get associated genera of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getGeneraOfOnePhenotypeInOneBodySite'
pheno_04 = GET(url, query=list(phenotype = "D006262", site = "Lung"))

```
### Get associated projects of a phenotype in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjectsOfOnePhenotypeInOneBodySite'
pheno_05 = GET(url, query=list(phenotype = "D006262", site = "Lung"))

```
### Get associated runs in a body site
Using the corresponding MeSH ID (e.g. D006262 for Health ) and body site (e.g. Lung)

`input`: `phenotype`, `site`,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRunsOfOnePhenotypeInOneBodySite'
pheno_06 = GET(url, query=list(phenotype = "D006262", site = "Lung"))

```


## Species/genera
### Get an overview of the species
`input`: none,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllSpecies'
all_species = GET(url)

```
### Get an overview of the genera
`input`: none,

`output`: an `Object`
```python
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getAllGenera'
all_genera = GET(url)

```

## Projects and runs
### Get projects
`input`: none,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getProjects'
projects = GET(url)

```
### Get runs
`input`: none,

`output`: an `Object`
```R
### -- Get all body sites --
url = 'https://mbodymap.microbiome.cloud/api/getRuns'
runs = GET(url)

```
