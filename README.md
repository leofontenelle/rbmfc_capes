# Contextualizing RBMFC in the Brazilian postgraduate education scenario

Copyright © 2022 Leonardo Ferreira Fontenelle <leonardof@leonardof.med.br>.

Distributed under the GNU General Public License v3.0; see LICENSE.

This is the analytic code for the equally named manuscript, to be 
submitted to [ABEC Meeting 2022](https://meeting22.abecbrasil.org.br/). 
It downloads open data from CAPES and tabulates which postgraduate 
programs published how many articles in which journals during years 
2017-2020.

The analytic code (`rbmfc_capes.R`) is meant to be run with R version 
4.2.1 and packages `data.table` 1.14.2 and `renv` 0.15.5. Starting R 
from the same directory as the code, or opening the project file 
`rbmfc_capes.Rproj` in RStudio, should be enough for `renv` to ensure 
the appropriate versions are available run running the code. This is 
just an additional precaution, as the code is expected to run just fine 
with other versions.

Running the analytic code will create two directories: `data_raw` and 
`data`. Open data from CAPES will be downloaded into `data_raw`, and 
tabulated data will be written to `data`. There will be one 
comma-separated values (CSV) file for each journal, named after one of 
its ISSN.

By default, the analytic code tabulates data for two journals: _Revista 
Brasileira de Medicina de Família e Comunidade_ (e-ISSN 2179-7994, 
ISSN-L 1809-5909) and _Revista de APS_ (e-ISSN 1809-8363, ISSN-L 
1516-7704). If you want to run a similar analysis for another 
journal(s), take hold of all the ISSNs and edit these lines of code in 
`rbmfc_capes.R`, section "Pick journals":

```{r}
focal_journals <- list(
  # Revista Brasileira de Medicina de Família e Comunidade
  c("2179-7994", "1809-5909"),
  # Revista de APS
  c("1809-8363", "1516-7704")
)
```

Some background: _Coordenação de Aperfeiçoamento de Pessoal de Nível 
Superior_ (CAPES) is the governmental organization responsible for 
coordinating "strict sense" postgraduate programs, that is, those 
offering masters' and PhD courses. CAPES groups postgraduate programs 
in "evaluation areas" for the purpose of evaluating, regulating and 
funding the postgraduate programs. A major part of the evaluation 
consists in assessing the postgraduate programs' scholarly output. In 
turn, ranking the journals within the evaluation areas is a major part 
of assessing the scholarly output.
