# Rpa process for fleksløns refusion

## Flekslønsrefusion regler:

Brobot er sat op til at sorterer mellem automatiske og manuelle behandlinger af flekslønsrefusion på følgende regler:

### En borgers KMD-Indkomst data for indeværende måned skal:
* Indeholde én og kun én lønseddel.
* Ikke indeholde Sygedagpenge.
* Ikke indeholde barselsdagpenge.

### Lønseddel
#### Selve lønseddelen skal indeholde:
* 6057 - A-indkomst
* 6096 - timetal

#### Kan indeholde:
* 6068 - feriepenge
* 6197 - pension
* 6198 - pension

### Brobot skal have adgang til:
* Borgers SBSYS-SAGSID
* Borgers - Pensionsrate

### Beregning for flekslønsrefusion:
#### Hvis der kun forekommer A-indkomst:
flekslønsrefusion = A-indkomst.
#### Hvis der kun forekommer A-indkomst og feriepenge:
flekslønsrefusion = A-indkomst - feriepenge
#### Hvis der kun forekommer A-indkomst og pension:
A-indkomst * pensionssats
#### Hvis der forekommer A-indkomst, feriepenge og pension:
(A-indkomst - feriepenge) * pensionssats.

Alle andre sager omkring flekslønsrefusion, kræver ikke regel-sat vurdering, og sendes derfor til manuel behandling hos sagsbehandler.
