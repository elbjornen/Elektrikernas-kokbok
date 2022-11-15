--- 
title: "Elektrikernas kokbok"
author: "Björn Ögren"
date: "2022-11-15"
output: pdf_document

documentclass: book
bibliography:
- book.bib
- packages.bib
description: |
  This is a minimal example of using the bookdown package to write a book.
  set in the _output.yml file.
  The HTML output format for this example is bookdown::gitbook,
link-citations: yes
github-repo: "rstudio/bookdown-demo"
site: bookdown::bookdown_site
extra_dependencies: awesomebox
---

# Introduction {-}

This book is a guide to authoring books and technical documents with R Markdown [@R-rmarkdown] and the R package **bookdown** [@R-bookdown]. It focuses on the features specific to writing books, long-form articles, or reports, such as:

- how to typeset equations, theorems, figures and tables, and cross-reference them;
- how to generate multiple output formats such as HTML, PDF, and e-books for a single book;
- how to customize the book templates and style different elements in a book;
- editor support (in particular, the RStudio IDE); and
- how to publish a book.

# Likströmskretsar {-}

# Seriekoppling
Seriekoppling innebär att alla komponenter genomlöps av hela den strömstyrka som flyter genom ledningen, medan den elektriska spänningen över seriekopplingen fördelas över komponenterna i förhållande till deras resistans.

Kirchhoffs första strömlag beskriver hur strömmar förgrenar sig i en pararellkrets.
Den andra beskriver hur spänningar fördelas i en seriekrets.

## Spänningsdelning

Kirchhoff andra lag
Summan av delspäningarna är lika med den totala spänningen.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_{tot} = U_{1} + U_{2} + U_{3} $$ | $$ U $$ | Spänning | Volt | $$ V $$ |

| Exempel uträkning spänningsdelning (1) |
|:-------------:|
| $$ U_{tot} = U_{1} + U_{2} + U_{3} $$ |
| $$ U_{tot} = 4 + 4 + 4 $$ |
| $$ U_{tot} = 12 \ V $$ |

## Okänd delspäning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_{tot} = U_{tot} - U_{3} - U_{2} $$ | $$ U $$ | Spänning | Volt | $$ V $$ |

| Exempel uträkning okänd delspäning (1) |
|:-------------:|
| $$ U_{tot} = U_{1} + U_{2} + U_{3} $$ |
| $$ U_{3} = 12 - 4 - 6  $$ |
| $$ U_{3} = 3 \ V $$ |

## Delresistans

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ {R}_{//}\frac{R_{tot}} {R} $$ | $$ R $$ | Delresistans | Omega | $$ \Omega $$ |

| Om alla delresistanser är lika |
|:-------------:|
| $$ {R}_{//}\frac{R_{tot}} {R} $$ |
| $$ R_{//} = \frac{100} {10} $$ |
| $$ R_{//} = 4,2  \ \Omega $$ |

| Om delresestanerna är olika |
|:-------------:|
| $$ R_1 = R_{tot} - R_1 $$ |
| $$ R_1 = 10 - 6 $$ |
| $$ R_1 = 6 \ \Omega $$ |

## Ersättningsresistans

Ersättningsresistans är den resistans vilken man kan ersätta två eller flera resistorer i en krets med.
För seriekopplingar är den totala resistansen $ R_T $ helt enkelt summan av de olika resistorernas resistans.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R_{ers} = R_{1} + R_{2} + R_{3} ... $$ | $$ R $$ | Ersättningsresistans | Omega | $$ \Omega $$ |

| Exempel uträkning ersättningsresistans |
|:-------------:|
| $$ R_{ers} = R_{1} + R_{2} + R_{3} $$ |
| $$ R_{ers} = 10 + 12 + 18 $$ |
| $$ R_{ers} = 40 \ \Omega $$ |

| Ersättningsresistansen går även att räkna ut från spänning totalt delat med strömen |
|:-------------:|
| $$ R_{ers} = \frac{U_{tot}} {I} $$ |
| $$ R_{ers} = \frac{U_{tot}} {I} $$ |
| $$ R_{ers} = 4,2 \ \Omega $$ |

# Pararellkoppling
Kirchhoffs första strömlag beskriver hur strömmar förgrenar sig i en pararellkrets. Den andra beskriver hur spänningar fördelas i en seriekrets.

## Huvudström
Huvudströmmen är lika med summan av grenströmmarna

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I_{h} = I_{1} + I_{2} + I_{3} $$ | $$ I_h $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning huvudström (1) |
|:-------------:|
| $$ I_{h} = I_{1} + I_{2} + I_{3} $$ |
| $$ I_{h} = 2 + 2 + 2 $$ |
| $$ I_{h} = 6 \ A $$ |

## Okänd grenström

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I_{3} = I_{h} - I_{1} - I_{2} $$ | $$ I $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning okänd grenström (1) |
|:-------------:|
| $$ I_{3} = I_{h} - I_{1} - I_{2} $$ |
| $$ I_{3} = 6 - 3 - 2 $$ |
| $$ I_{h} = 1 \ A $$ |

## Ersättningsresistans
Ersättningsresistans är den resistans vilken man kan ersätta två eller flera resistorer i en krets med.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ \frac{1} {R} = \frac{1} {R}_{1} + \frac{1} {R}_{2} + \frac{1} {R}_{3} ... $$ | $$ R $$ | Ersättningsresistans | Omega | $$ \Omega $$ |

| Exempel uträkning ersättningsresistans |
|:-------------:|
| $$ \frac{1} {R} = \frac{1} {R}_{1} + \frac{1} {R}_{2} + \frac{1} {R}_{3} $$ |
| $$ \frac{1} {R} = \frac{1} {10} + \frac{1} {12} + \frac{1} {18} $$ |
| $$ R_{ers} = 40 \ \Omega $$ |

| Ersättningsresistansen går även att räkna ut från spänning totalt delat med strömen |
|:-------------:|
| $$ R_{ers} = \frac{U_{tot}} {I} $$ |
| $$ R_{ers} = \frac{U_{tot}} {I} $$ |
| $$ R_{ers} = 4,2 \ \Omega $$ |

# Ledare

## Ledarrresistans

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R = \frac {p \times ^L }{A} $$ | $$ R $$ | Ledarresistans | Omega | $$ \Omega $$ |

| Exempel uträkning ledarresistans |
|:-------------:|
| $$ R = \frac {p \times ^L }{A} $$ |
| $$ R = \frac {0,0175 \times 10 }{1} $$ |
| $$ R = 0,0175 \ \Omega $$ |

### Area

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ A = \frac {p \times ^L }{R} $$ | $$ A $$ | Cirkel | Area | $$ mm^2 $$ |

| Exempel uträkning ledararea |
|:-------------:|
| $$ A = \frac {p \times ^L }{R} $$ |
| $$ A = \frac {0,0175 \times 20 }{0,466} $$ |
| $$ A = 0,75 \ mm^2 $$ |

### Ledarlängd

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ L = \frac {R \times ^A }{P} $$ | $$ L $$ | Ledarlängd | Längd | $$ m $$ |

| Exempel uträkning ledarlängd |
|:-------------:|
| $$ L = \frac {R \times ^A }{P} $$ |
| $$ L = \frac {1,75 \times 1,0 }{0,0175} $$ |
| $$ L = 100 \ m $$ |

### Ledarresistivitet

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ p = \frac {R \times ^A }{L} $$ | $$ p $$ | Ledarresistivitet | Omega | $$ \Omega $$ |

| Exempel uträkning ledarresistivitet |
|:-------------:|
| $$ p = \frac {R \times ^A }{L} $$ |
| $$ p = \frac {2,67 \times 0,75 }{20} $$ |
| $$ p = 0,0090,1 \ \Omega \ mm^2/m $$ |

# Ackumulatorer

## Polspänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U = E - {R_{i}} \times I $$ | $$ f $$ | Frekvens | Hertz | $$ Hz $$|

| Exempel uträkning tid (1) |
|:-------------:|
| $$ U = E - {R_{i}} \times I $$ |
| $$ U = 1,5 - 0,4 \times 0,9 $$ |
| $$ U = 1,14 \ V $$ |

## Spänningsfall 

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_{drop} = R_i \times I $$ | $$ U $$ | Spänning | Volt | $$ V $$|

| Exempel uträkning spänningsfall |
|:-------------:|
| $$ U_{drop} = R_i \times I $$ |
| $$ U_{drop} = 0,6 \times 2,2 $$ |
| $$ U_{drop} = 1,32 \ V $$ |

## EMK Total

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ E_{tot} = E_{batt} \times Antalet \ batterier \ i \ serie $$ | $$ U $$ | Spänning | Volt | $$ V $$ |

| Exempel uträkning EMK Total |
|:-------------:|
| $$ E_{tot} = E_{batt} \times Antalet \ batterier \ i \ serie $$  |
| $$ E_{tot} = 4,5 \times 3 $$  |
| $$ E_{tot} = 13,5 \ V $$ |

## Resistans total
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R_{tot} = R_y + R_i $$ | $$ R_{tot} $$ | Resistans total | Omega | $$ \Omega $$ |

| Exempel uträkning resistans total  |
|:-------------:|
| $$ R_{tot} = R_y + R_i $$ |
| $$ R_{tot} = 22 + 1,2 $$ |
| $$ R_{tot} = 23,2 \ \Omega $$ |

## Yttre resistans
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R_y = R_{tot} - R_i $$ | $$ R_{y} $$ | Resistans | Omega | $$ \Omega $$ |

| Exempel uträkning yttre resistans |
|:-------------:|
| $$ R_y = R_{tot} - R_i $$ |
| $$ R_y = 5 - 0,4 $$ |
| $$ R_y = 4,6 \ \Omega $$ |

## Seriekoppling

### Inre resistans
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R_{i \ tot} = Antal \ Batt \times R_{I \ Batt} $$ | $$ R_{i} $$ | Inre resistans | Omega | $$ \Omega $$ |

| Exempel uträkning inre resistans i strömkällan |
|:-------------:|
|  $$ R_{i \ tot} = Antal \ Batt \times R_{I \ Batt} $$ |
|  $$ R_{i \ tot} = 3 \times  0,3 $$  |
| $$ R_{i \ tot} = 0,9 \ \Omega $$ |
| Vid seriekoppling adderas reistanserna sig |

### Kortslutningsström
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I = I_{max} $$ | $$ I_{max} $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning kortslutningsström |
|:-------------:|
|  $$ I = I_{max} $$ |
|  $$ I = I_{max} = 0,5 \ A $$ |
| $$ I = I_{max} = 0,5 \ A $$ |
| Eftersom det vid seriekoppling är samma ström genom hela kretsen |

## Pararellkoppling

### Inre resistans
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ R_{i \ tot} = \frac {R_{i Batt}}{Batt_{Antal}} $$ | $$ R_{i \ \ tot} $$ | Inre resistans | Omega | $$ \Omega $$ |

| Exempel uträkning inre resistans i strömkällan |
|:-------------:|
| $$ R_{i \ tot} = \frac {R_{i / Batt}}{Batt_{Antal}} $$ |
| $$ R_{i \ tot} = \frac {0,3}{3} $$ |
| $$ R_{i \ tot} = 0,1 \ \Omega $$ |
| Vid parallelkoppling delas resistansen sig |

### Kortslutningsström 
| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:------------:|:-------------:|:-------------:|
| $$ I_{max} = Batt \ antal \times I_i $$ | $$ I_{max} $$ | Kortslutningsström | Ampere | $$ A $$|

| Exempel uträkning kortslutningsström |
|:-------------:|
| $$ I_{max} = Batt \ antal \times I_i $$ |
| $$ I_{max} = 3 \times 0,5 \ A $$ |
| $$ I_{max} = 1,5 \ A $$ |
| Eftersomm totalströmmen vid pararellkoppling blir summan av delströmmarna |

# Effekt
Effekt betecknas ofta med bokstaven P från engelskans power och kan bland annat yttra sig i form av ett
värmeflöde eller mekaniskt arbete. SI-enheten för effekt är watt (W), där en watt motsvarar en
energiomvandling på en joule per sekund (W=J/s). Utöver watt finns det ett flertal enheter som betecknar effekt, exempelvis enheten hästkraft, vilket i Sverige motsvarar en effekt på 735,5 watt.

Den momentana effektutvecklingen i en resistor är produkten av spänningen över komponenten och den elektriska strömmen genom komponenten.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ P = U \times I $$ | $$ P $$ | Effekt | Watt | $$ W $$ |

| Exemple uträkning Effekt |
|:-------------:|
| $$ P = U \times I $$ |
| $$ P = U \times I = 230 \times 0,5 $$ |
| $$ P= 115 \ W $$ |

## Watt tid

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ W = P \times t $$ | $$ P $$ | Effekt | Watt | $$ W $$ |

| Exemple uträkning watt tid |
|:-------------:|
| $$ W = P \times t $$ |
| $$ W = P \times t = 0,115 \times 10^3 \times 10 $$ |
| $$ W = 1,15 \ kWh$$ |

## Kostnadsberäkning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ Kostnad = kW \times Pris $$ | $$ Kostnad $$ | Effekt | Watt | $$ W $$ |

| Exemple uträkning kostnad |
|:-------------:|
| $$ Kostnad = kW \times Pris $$ |
| $$ Kostnad = kW \times Pris = 1,15 \times 1,10 $$ |
| $$ Kostnad = -:- \ Kr $$ |

# Växelströmskretsar  {-}

# Frekvenz

## Tidsintervall
Frekvens är en storhet för antalet
repeterande händelser inom ett givet
tidsintervall[1]. För att beräkna
frekvensen fixerar man ett
tidsintervall, räknar antalet
förekomster av händelsen och
dividerar detta antal med längden av
tidsintervallet. Resultatet anges i
enheten hertz (Hz) efter den tyske
fysikern Heinrich Rudolf Hertz, där
1 Hz är en händelse som inträffar en
gång per sekund. Alternativt kan man
mäta tiden mellan två förekomster av
händelsen ((tids)perioden) och
därefter beräkna frekvensens
reciproka värde.

### Frekvens

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ Frekvens = \frac{1}{Tid} $$ | $$ f $$ | Frekvens | Hertz | $$ Hz $$|

| Exempel uträkning frekvens (1) |
|:-------------:|
| $$ Frekvens = \frac{1}{Tid} $$ |
| $$ f =\frac{1}{38} \times 10^{3} $$ |
| $$ f = 26,3 \ Hz  $$ |

### Tid

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ Tid = \frac{1}{Frekvens} $$ | $$ f $$ | Frekvens | Hertz | $$ Hz $$|

| Exempel uträkning tid (1) |
|:-------------:|
| $$ Tid = \frac{1}{Frekvens} $$ |
| $$ Tid = \frac{1}{400} \times 10^{3} $$ |
| $$ T = 2,5 \ ms  $$ |

## Toppvärden

### Toppspänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ \widehat{u} = U_{eff} \times \sqrt{2} $$ | $$ \widehat{u} $$ | Toppspänning | Volt | $$ V $$|

| Exempel uträkning toppspänning |
|:-------------:|
| $$ \widehat{u} = U_{eff} \times \sqrt{2} $$ |
| $$ \widehat{u} = 415 \times \sqrt{2} $$ |
| $$ \widehat{u} \approx 587 \ V $$ |

### Toppström

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ \widehat{I} = I_{eff} \times \sqrt{2} $$ | $$ \widehat{I} $$ | Toppström | Amper | $$ A $$|

| Exempel uträkning toppström |
|:-------------:|
| $$ \widehat{I} = I_{eff} \times \sqrt{2} $$ |
| $$ \widehat{I} = 20 \times \sqrt{2} $$ |
| $$ \widehat{I} \approx 28,3 \ A  $$ |

### Topp till toppspänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ \widehat{\breve{u}} = \widehat{u} \times 2  $$ | $$ \widehat{\breve{u}} $$ | Toppspänning | Volt | $$ V $$|

| Exempel uträkning topp till toppspänning |
|:-------------:|
| $$ \widehat{\breve{u}} $$ |
| $$ \widehat{\breve{u}} = 587 \times 2 $$ |
| $$ \widehat{\breve{u}} = 1174 \ V $$ |

### Topp till toppvärde av ström

$$ \widehat{\breve{I}} = \widehat{I} \times 2 $$

Exemple

$$ \widehat{\breve{I}} = \widehat{I} \times 2 \approx 28,3 \times 2 = 56 \ A $$

Topp till toppvärd är således
$$ \widehat{\breve{I}} \approx 56 \ A $$

# Spänning

## Y-Koppling

### Linjespänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_L = U_f \times \sqrt{3} $$ | $$ U_l $$ | Spänning | Volt | $$ V $$|

| Exempel uträkning fasspänning |
|:-------------:|
| $$ U_L = U_f \times \sqrt{3}  $$ |
| $$ U_L = 230 \times \sqrt{3} $$ |
| $$ U_L = 400 \ V $$ |

### Fasspänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_f = \frac{U_L}{\sqrt{3}} $$ | $$ U_l $$ | Spänning | Volt | $$ V $$|

| Exempel uträkning fasspänning |
|:-------------:|
| $$ U_f = \frac{U_L}{\sqrt{3}}  $$ |
| $$ U_f = \frac{400}{\sqrt{3}} $$ |
| $$ U_f = 230 \ V $$ |

## D-koppling

### Linjespänning

### Fasspänning

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ U_f = U_L = 400V  $$ | $$ U_L $$ | Spänning | Volt | $$ V $$|

# Ström

## Y-Koppling

### Fasström

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I_f = \frac{U_f}{R} $$ | $$ I_f $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning fasström |
|:-------------:|
| $$ I_f = \frac{U_f}{R} $$ |
| $$ I_f \frac{400}{100} $$ |
| $$ I_f = 4 \ A $$ |

### Linjeström

$$ I_L = I_f = Faström $$

## D-koppling

### Fasström

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I_f = \frac{U_h}{R} $$ | $$ I_f $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning fasström |
|:-------------:|
| $$ I_f = \frac{U_h}{R} $$ |
| $$ I_f \frac{400}{100} $$ |
| $$ I_f = 4 \ A $$ |

### Linjeström

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ I_L = I_f \times \sqrt{3} $$ | $$ I_L $$ | Ström | Ampere | $$ A $$|
| $$ I_L = \frac {P}{ \sqrt{3} \times U_h } $$ | $$ I_L $$ | Ström | Ampere | $$ A $$|

| Exempel uträkning linjeström (1) |
|:-------------:|
| $$ I_L = I_f \times \sqrt{3} $$ |
| $$ I_L = 90 \times \sqrt{3} $$ |
| $$ I_L = 2,3 \ A $$ |

| Exempel uträkning linjeström (2) |
|:-------------:|
| $$ I_L = \frac {P}{ \sqrt{3} \times U_h} $$ |
| $$ I_L = \frac {6000}{ \sqrt{3} \times 400} $$ |
| $$ I_L = 8,7 \ A $$ |

# Effekt

## Trefaskretsar
Det finns en formel för beräkning av effekt och strömmar i trefaskretsar som gäller både för Y- och D-koppling. I praktiken är vi oftast intresserade av strömmarna som går i ledarna till en belastning, det vi kallar huvudström. Men i en D-koppling är det fasströmmarna genom belastningen som ger effektutvecklingen. Därför komplettear vi effektformeln med: $$ \sqrt{3} $$ som beskriver sambandet mellan huvudström och fasström. Formeln utgör även grunden för beräkningar av effekten i reaktiva belastningar och den kompletteras då med $$ cos \phi $$.


| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ P_{trefas}= \sqrt{3} \times U \times I_f $$ | $$ P $$ | Aktiv effekt | Watt | $$ W $$ |

| Effekt i tre D-kopplade resistorer |
|:-------------:|
| $$ P_{trefas}= \sqrt{3} \times U \times I_f $$ |
| $$ P_{trefas}= \sqrt{3} \times U \times I_f $$ |
| $$ P= 4800 \ W $$ |

## Reaktiva kretsar

### Aktiv
Det är den aktivs effekt som vi kan omsätta till ljus, värme eller mekansik rörelse. Aktiva effekten har enheten watt och betecknas med P i effektriangeln.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ P= U \times I \times cos  \phi $$ | $$ P $$ | Aktiv effekt | Watt | $$ W $$ |
| $$ P_{trefas}= \sqrt{3} \times U \times I \times cos  \phi $$ | $$ P $$ | Aktiv effekt | Watt | $$ W $$ |

| Exempel uträkning aktiv effekt |
|:-------------:|
| $$ P=U \times I \times cos  \phi $$ |
| $$ P=230 \times 0,78 \times 0,78 $$ |
| $$ P=1640 \ W $$ |

| Exempel uträkning aktiv effekt trefas|
|:-------------:|
| $$ P_{trefas}= \sqrt{3} \times U \times I \times cos  \phi $$ |
| $$ P_{trefas}= \sqrt{3} \times ? \times ? \times ? $$ |
| $$ P_{trefas}= \ W $$ |

### Skenbar
Skenbar effekt är produkten av strömmens och spänningens effektvärden. Skenbar effekt har enheten voltampere (VA).

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ S=U \times I = \sqrt{P^2 + Q^2} $$ | $$ S $$ | Skenbar effekt | Voltampere | $$ VA $$|
| $$ S_{trefas}= \sqrt{3} \times U \times I $$ | $$ S $$ | Skenbar effekt | Voltampere | $$ VA $$|

| Exempel uträkning skenbar effekt (1) |
|:-------------:|
| $$ S=U \times I $$ |
| $$ S=230 \times 9,05 $$ |
| $$ S=2081 \ W $$ |

| Exempel uträkning skenbar effekt (2) |
|:-------------:|
| $$ S= \sqrt{P^2 + Q^2} $$ |
| $$ S= \sqrt{2000^2 + 1000^2} $$ |
| $$ S=2,2 \ kVA $$ |

| Exempel uträkning skenbar effekt trefas |
|:-------------:|
| $$ S_{trefas}= \sqrt{3} \times U \times I $$ |
| $$ S_{trefas}= \sqrt{3} \times 230 \times 9,05 $$ |
| $$ S_{trefas}=2081 \ W $$ |

### Reaktiv
Den reaktiva effekten uppstår på grund av fasförskjutningen som det reaktiva motståndet åstakomer. Den reaktiva effekten har enheten voltampere, VAr. Tillläget r står för reaktiv.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ Q=U \times I \times sin  \phi = \sqrt{S^{2}-P^{2}} $$ | $$ Q $$ | Reaktiv effekt | Voltampere reakt | $$ VAr $$|

| Exempel uträkning reaktiv effekt (1) |
|:-------------:|
| $$ Q=U \times I \times sin  \phi $$ |
| $$ Q=U \times I \times sin  \phi $$ |
| $$ Q=  \ VAr $$ |

| Exempel uträkning reaktiv effekt (2) |
|:-------------:|
| $$ Q= \sqrt{S^{2}-P^{2}} $$ |
| $$ Q= \sqrt{1000^{2}-607^{2}} $$ |
| $$ Q= 795 \ VAr $$ |


# Växelströmsmotstånd

## Impedans

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ Z=\sqrt{R^2 + (X_{L} - X_{L})^2} $$ | $$ Z $$ | Impedans | Ohm | $$  \Omega $$ |
| $$ R = \frac{U}{I}  $$ | $$ R $$ | Resistans | Ohm | $$  \Omega $$ |
$$ X_L = 2 \pi fL $$ | $$ X_L $$ | Induktiv reaktans | Ohm | $$  \Omega $$ |
| $$ X_C =\frac{1} {2 \pi f C}  $$ | $$ X_C $$ | kapacitiv reaktans | Ohm | $$  \Omega $$ |

| Exempel uträkning impedans Z |
|:-------------:|
| $$ Z=\sqrt{R^2 + (X_{L})^2} $$ |
| $$ Z=\sqrt{20^2 + (15,7)^2} $$ |
| $$ Z= 25,4 \  \Omega $$ |


## Kondensatorer
Kondensatorns förmåga att lagra elektrisk laddning kallas kapacitans, och betecknas C. Enheten för kapacitans är farad som betecknas F.

|Prefixer | Förkortning| Tiopotens |
|----------|:-------------:|:-------------:|
| $$ 1 \ mikrofarad  $$ | $$  \mu F $$ | $$ 10^{-6} $$ |
| $$ 1 \ nanofarad  $$ | $$ nF $$ | $$ 10^{-9} $$ |
| $$ 1 \ picofarad  $$ | $$ pF $$ | $$ 10^{-12} $$ |

### Kapacitans
Kapacitans beskriver hur mycket energi kondensatorn kan innehålla vid en viss spänning.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ C=\frac{1}{(2 \pi f  X_c)} $$ | $$ C $$ | Kapacitans | Farad | $$ F^{As/V} $$ |
| $$ f = \frac{1}{T}   $$ | $$ f $$ | Hertz | $$ Hz $$ |
| $$ 2 \times \pi = 3.14  $$ | $$ Pi $$ | Omkrets | Radies | $$ \pi $$ |

| Exempel uträkning kapacitans |
|:-------------:|
| $$ L=\frac{X_L} {2 \pi f} $$ |
| $$ L=\frac{1000} {(2 \times 3.14 \times 1.0 \times 10^{3} \ \sqrt{3})} $$ |
| $$ L= 0.16 \ H $$ |

### Kapacitiv reaktans
Växelströmsmotståndet i kondensatorn minskar när frekvensen ökar. Då kommer ekvationen att minska när frekvesen ökar.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ X_C =\frac{1} {2 \pi f C}  $$ | $$ X_C $$ | kapacitiv reaktans | Ohm | $$  \Omega $$ |
| $$ f = \frac{1}{T}   $$ | $$ f $$ | Hertz | $$ Hz $$ |
| $$ 2 \times \pi = 3.14  $$ | $$ Pi $$ | Omkrets | Radies | $$ \pi $$ |

| Exempel uträkning kapacitiv reaktans |
|:-------------:|
| $$ X_C =\frac{1} {2 \pi f C} $$ |
| $$ X_C = \frac{1}{2 \times \pi \times 50 \times 0,0002} $$ |
| $$ X_C = 15,91 \  \Omega  $$ |

### Seriekopplade

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ C_{tot}=C_{1} + C_{2}... $$ | $$ C $$ | Kapacitans | Farad | $$ F^{As/V} $$ |

| Exempel uträkning kapacitiv reaktans |
|:-------------:|
| $$ C_{tot}=C_{1} + C_{2} $$ |
| $$ C_{tot}=12_{1} + 12_{2} $$ |
| $$ C_{tot}=24 \  \mu F $$ |

### Parallellkopplade

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ 
\frac{1}{C_{tot}} =
\frac{1}{C_{1}} +
\frac{1}{C_{2}} +
\frac{1}{C_{3}}
...
$$ | $$ C $$ | Kapacitans | Farad | $$ F^{As/V} $$ |

| Exempel uträkning kapacitiv reaktans |
|:-------------:|
| $$ 
\frac{1}{C_{tot}} =
\frac{1}{C_{1}} +
\frac{1}{C_{2}} +
\frac{1}{C_{3}}
...
$$ |
| $$ 
\frac{1}{C_{tot}} =
\frac{1}{1,8_{1}} +
\frac{1}{16_{2}} +
\frac{1}{32_{3}}
$$ |
| $$ C_{tot}=4.5 \ nF $$ |

## Spolar
Spolens egenskaper kallas induktans, betecknas i formler L och mäts i enheten Henry (H).

|Prefixer | Enhet | Förkostning| 
|----------|:-------------:|:-------------:|
| $$ 1 \ millihenry  $$ | $$ mH $$ | $$ 10^{-3} $$ |
| $$ 1 \ mikrohenry  $$ | $$  \mu H $$  | $$ 10^{-6} $$ |

### Induktans
Induktansen beror på hur många varv spolen har, diametern, avståndet mellan ledarna och om spolen är försedd med järnkärna. Flera lindningsvarv och större diameter ger spolen större indutans.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ L=\frac{X_L} {2\pi f} $$ | $$ L $$ | Induktans | Henry | $$ H^{Vs/A} $$ |
| $$ f = \frac{1}{T}   $$ | $$ f $$ | Frekvens | Hertz | $$ Hz $$ |
| $$ 2 \times \pi = 3.14  $$ | $$ Pi $$ | ? | ? | $$ \pi $$ |

::: {.latex}
$$ L=\frac{X_L} {2 \times \pi f} $$ 
$$ L=\frac{1000} {(2 \times 3.14 \times 1.0 \times 10^{3} \ \sqrt{3})} $$ 
$$ L= 0.16 \ H $$ 
:::
|

### Induktiv reaktans
Växelströmsmotståndet är
frekvensberoende och motståndet ökar när
frekvensen ökar.

| Samband | Beteckning | Storhet | Enhet | Förkortning | 
|----------|:-------------:|:-------------:|:-------------:|:-------------:|
| $$ X_L = 2 \pi fL $$ | $$ X_L $$ | Induktiv reaktans | Ohm | $$  \Omega $$ |
| $$ f = \frac{1}{T} $$ | $$ f $$ | Frekvens | Hertz | $$ Hz $$ |
| $$ 2 \times \pi = 3.14  $$ | $$ Pi $$ | ? | ? | $$ \pi $$ |

::: {.latex}

$$ X_L = 2 \pi fL $$
$$ X_L = 2 \times \pi \ 50 \ Hz \times 0,05 \ H  $$
$$ X_L=15,7 \  \Omega $$
:::

<!--chapter:end:index.Rmd-->
