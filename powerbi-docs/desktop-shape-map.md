---
title: Używanie mapowań kształtów w programie Power BI Desktop (wersja zapoznawcza)
description: Tworzenie porównań względnych z innymi regionami przy użyciu mapowań kształtów w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 019aa1425d05fcfdc4415570acdc29e7a684dc25
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34290964"
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Mapowania kształtów w programie Power BI Desktop (wersja zapoznawcza)
Program Power BI Desktop umożliwia utworzenie wizualizacji **Mapowanie kształtów**, która pozwala wyświetlić porównania względne regionów na mapie za pomocą różnych kolorów. W przeciwieństwie do wizualizacji **Mapa** wizualizacja **Mapowanie kształtów** nie umożliwia wyświetlenia dokładnych lokalizacji geograficznych punktów danych. Służy ona głównie do pokazywania porównań względnych regionów na mapie przy użyciu różnych kolorów.

Wizualizacje **Mapowanie kształtów** są oparte na mapach ESRI/TopoJSON, które są bardzo przydatne, ponieważ pozwalają korzystać z niestandardowych, własnoręcznie utworzonych planów, na przykład map geograficznych, schematów rozmieszczenia siedzeń lub rozkładów pomieszczeń. Możliwość korzystania z niestandardowych map jest niedostępna w tej wersji zapoznawczej **Mapowania kształtów**.

## <a name="creating-shape-maps"></a>Tworzenie mapowań kształtów
Kontrolkę **Mapowanie kształtów** można przetestować na mapach dostarczanych z wersją zapoznawczą. Można też użyć własnej mapy, która spełnia wymagania opisane w sekcji **Używanie niestandardowych map**.

Wizualizacja **Mapowanie kształtów** jest dostępna w wersji zapoznawczej i musi zostać włączona w programie Power BI Desktop. Aby włączyć funkcję **Mapa kształtów**, wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje wersji zapoznawczej**, a następnie zaznacz pole wyboru **Wizualizacja mapy kształtu**. Po zaznaczeniu należy uruchomić ponownie program Power BI Desktop.

![](media/desktop-shape-map/shape-map_1a.png)

Po włączeniu opcji **Mapowanie kształtów** kliknij kontrolkę **Mapowanie kształtów** w okienku **Wizualizacje**.

![](media/desktop-shape-map/shape-map_2.png)

Program Power BI Desktop utworzy pustą kanwę projektu wizualizacji **Mapowanie kształtów**.

![](media/desktop-shape-map/shape-map_3.png)

Aby utworzyć wizualizację **Mapowanie kształtów**, wykonaj następujące kroki:

1. W okienku **Pola** przeciągnij pole danych, które zawiera nazwy (lub skróty) regionów do zasobnika **Lokalizacja**, a pole miary danych do zasobnika **Nasycenie koloru** (mapa nie będzie jeszcze widoczna).
   
   > [!NOTE]
> Aby dowiedzieć się, jak szybko uzyskać dane mapy do przetestowania wizualizacji **Mapowanie kształtów**, zobacz poniższą sekcję **Uzyskiwanie danych mapy**.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. W okienku ustawień **Format** rozwiń pozycję **Kształt** i wybierz pozycję z listy rozwijanej **Mapy standardowe**, aby wyświetlić dane. Pojawi się renderowanie, jak pokazano na poniższej ilustracji.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> Sekcja **Klucze regionów** znajdująca się na końcu tego artykułu zawiera zbiór tabel z kluczami mapowania regionów, których można używać do testowania wizualizacji **Mapowanie kształtów**.
   > 
   > 
3. W okienku ustawień **Format** można modyfikować ustawienia rzutowania mapy oraz kolory punktów danych. Można również zarządzać ustawieniami powiększania. Na przykład można zmieniać kolory oraz ustawiać wartości maksymalne i minimalne.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. Można również dodać kolumnę danych kategorii do zasobnika **Legenda** i klasyfikować regiony na mapie na podstawie kategorii.

## <a name="use-custom-maps"></a>Używanie niestandardowych map
Wizualizacji **Mapowanie kształtów** można używać z niestandardowymi mapami w formacie **TopoJSON**. Jeśli format mapy jest inny, można skorzystać z narzędzi online, takich jak [**Map Shaper**](http://mapshaper.org/), aby przekonwertować *pliki kształtów* lub mapy *GeoJSON* na format **TopoJSON**.

Aby użyć pliku mapy **TopoJSON**, dodaj wizualizację ShapeMap do raportu, a następnie dodaj dane do zasobników *Lokalizacja* i *Nasycenie koloru*. Następnie przy wybranej sekcji **Format** (oznaczona jako (1) na poniższej ilustracji) w okienku **Wizualizacje** rozwiń sekcję **Kształt** i wybierz pozycję **+ Dodaj mapę**.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="sample-custom-map"></a>Przykładowa mapa niestandardowa
W witrynie *Offices of the United States Attorneys* są publikowane roczne raporty obrachunkowe na podstawie danych z postępowań sądowych i rozpatrywanych spraw.  Wszystkie te raporty można uzyskać, korzystając z poniższego linku.

https://www.justice.gov/usao/resources/annual-statistical-reports

Poszczególne stany można podzielić na wiele okręgów, dlatego musimy użyć niestandardowej mapy kształtów.  Po zaimportowaniu mapy **TopoJSON** okręgów sądowych Stanów Zjednoczonych do programu **Power BI Desktop** możemy zwizualizować roczne dane obrachunkowe dotyczące okręgów sądowych.  Na poniższym obrazie przedstawiono przykład takiej mapy.

![](media/desktop-shape-map/shape-map_7a.png)

Korzystając z map stanów, można również przeprowadzić interesujące analizy i przedstawić bardziej szczegółowe dane na podstawie okręgów wchodzących w skład poszczególnych stanów. 

![](media/desktop-shape-map/shape-map_7b.png)

Jeśli chcesz poeksperymentować z tym zestawem danych i tą wizualizacją, możesz pobrać oryginalny plik PBIX użyty do wygenerowania tego raportu, korzystając z następującego linku.

* [Plik PBIX demonstracji niestandardowej mapy kształtów](http://download.microsoft.com/download/1/2/8/128943FB-9231-42BD-8A5D-5E2362C9D589/DistrictAttorneyFiscalReport.pbix)

## <a name="getting-map-data"></a>Uzyskiwanie danych mapy
Aby szybko wprowadzić dane do modelu w celu przetestowania wizualizacji **Mapowanie kształtów**, możesz skopiować jedną z tabel znajdujących się na końcu tego artykułu, a następnie wybrać pozycję **Wprowadź dane** na wstążce **Narzędzia główne**.

![](media/desktop-shape-map/shape-map_4.png)

Jeśli dane zawierają wiele kolumn, należy posłużyć się edytorem, takim jak program Excel, aby wkleić dane, a następnie oddzielnie skopiować każdą kolumnę danych. Następnie można wkleić tabelę do programu Power BI Desktop. Pierwszy wiersz jest automatycznie rozpoznawany jako nagłówek.

![](media/desktop-shape-map/shape-map_5.png)

Możesz dodać nową kolumnę, po prostu wpisując jej nazwę (w pustej kolumnie z prawej strony), a następnie dodać wartości w poszczególnych komórkach tak jak w programie Excel. Gdy skończysz, wybierz pozycję **Załaduj**. Tabela zostanie dodana do modelu danych w programie Power BI Desktop.

> [!NOTE]
> Podczas pracy z krajami lub regionami używaj skrótów trzyliterowych, aby geokodowanie działało prawidłowo w wizualizacjach w postaci map. *Nie* używaj skrótów dwuliterowych, ponieważ niektóre kraje lub regiony mogą nie być prawidłowo rozpoznawane.
> 
> Jeśli masz tylko skróty dwuliterowe, zapoznaj się z [tym wpisem na blogu zewnętrznym](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp), aby uzyskać informacje na temat kroków, które musisz wykonać w celu skojarzenia dwuliterowych skrótów krajów/regionów z trzyliterowymi skrótami krajów/regionów.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Działanie i wymagania wersji zapoznawczej
Jest kilka kwestii i wymagań, które dotyczą wersji zapoznawczej wizualizacji **Mapowanie kształtów**:

* Wizualizacja **Mapowanie kształtów** jest dostępna w wersji zapoznawczej i musi zostać włączona w programie Power BI Desktop. Aby włączyć funkcję **Mapa kształtów**, wybierz pozycję **Plik > Opcje i ustawienia > Opcje > Funkcje wersji zapoznawczej**, a następnie zaznacz pole wyboru **Wizualizacja mapy kształtu**.
* Należy teraz ustawić również zasobnik **Nasycenie koloru**, aby klasyfikacja **Legenda** działała poprawnie.
* Ostateczna wersja funkcji **Mapa kształtów** będzie wyposażona w interfejs użytkownika, na którym będą prezentowane klucze mapy aktualnie wybranych map (wciąż nie została ustalona data wersji ostatecznej i funkcja **Mapa kształtów** jest ciągle w wersji zapoznawczej). W tej wersji zapoznawczej możesz posługiwać się kluczami regionów mapy z tabel znajdujących się w następującej sekcji **Klucze regionów** tego artykułu.
* Wizualizacja **Mapowanie kształtów** wykreśli maksymalnie 1000 punktów danych.

## <a name="region-keys"></a>Klucze regionów
Aby przetestować wizualizację **Mapowanie kształtów** w wersji zapoznawczej, skorzystaj z następujących **kluczy regionów**.

### <a name="australia-states"></a>Australia: stany
| Identyfikator | Skrót | Kod ISO | Nazwa | Kod pocztowy |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Australia Zachodnia |WA |
| au-vic |Vic |AU-VIC |Wiktoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |Australia Południowa |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Terytorium Północne |NT |
| au-nsw |NSW |AU-NSW |Nowa Południowa Walia |NSW |
| au-act |ACT |AU-ACT |Australijskie Terytorium Stołeczne |ACT |

### <a name="austria-states"></a>Austria: stany
| Identyfikator | Kod ISO | Nazwa | Nazwa (j. polski) | Kod pocztowy |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Wiedeń |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tyrol |TR |
| at-st |AT-6 |Steiermark |Styria |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Górna Austria |OO |
| at-no |AT-3 |Niederösterreich |Dolna Austria |NO |
| at-ka |AT-2 |Kärnten |Karyntia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brazylia: stany
| Identyfikator |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Kanada: prowincje
| Identyfikator | Kod ISO | Nazwa | Kod pocztowy |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Terytoria Północno-Zachodnie |NT |
| ca-yt |CA-YT |Jukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Wyspa Księcia Edwarda |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nowa Szkocja |NS |
| ca-nl |CA-NL |Nowa Fundlandia i Labrador |NL |
| ca-nb |CA-NB |Nowy Brunszwik |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |Kolumbia Brytyjska |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>Francja: regiony
| Identyfikator | Nazwa | Nazwa (j. polski) |
| --- | --- | --- |
| Alsace |Alsace |Alzacja |
| Rhone-Alpes |Rhône-Alpes |Rodan-Alpy |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Prowansja-Alpy-Lazurowe Wybrzeże |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Pikardia |
| Pays de la Loire |Pays de la Loire |Kraj Loary |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pireneje |
| Lorraine |Lorraine |Lotaryngia |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Langwedocja-Roussillon |
| Ile-del-France |Île-de-France |Ile-de-France |
| Haute-Normandie |Haute-Normandie |Górna Normandia |
| Franche-Comte |Franche-Comté |Franche-Comte |
| Corse |Corse |Korsyka |
| Champagne-Ardenne |Champagne-Ardenne |Szampania-Ardeny |
| Centre-Val de Loire |Centre-Val de Loire |Region Centralny-Dolina Loary |
| Bretagne |Bretagne |Bretania |
| Bourgogne |Bourgogne |Burgundia |
| Basse-Normandie |Basse-Normandie |Dolna Normandia |
| Auvergne |Auvergne |Owernia |
| Aquitaine |Aquitaine |Akwitania |

### <a name="germany-states"></a>Niemcy: landy
| Identyfikator | Kod ISO | Nazwa | Nazwa (j. polski) | Kod pocztowy |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlin |BE |
| de-th |DE-TH |Thüringen |Turyngia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saksonia-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saksonia |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Meklemburgia-Pomorze Przednie |MV |
| de-bb |DE-BB |Brandenburg |Brandenburgia |BB |
| de-sh |DE-SH |Schleswig-Holstein |Szlezwik-Holsztyn |SH |
| de-sl |DE-SL |Saarland |Saara |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Nadrenia-Palatynat |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |Nadrenia Północna-Westfalia |NW |
| de-ni |DE-NI |Niedersachsen |Dolna Saksonia |NI |
| de-he |DE-HE |Hessen |Hesja |HE |
| de-hh |DE-HH |Hamburg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Brema |HB |
| de-by |DE-BY |Bayern |Bawaria |BY |
| de-bw |DE-BW |Baden-Württemberg |Badenia-Wirtembergia |BW |

### <a name="ireland-counties"></a>Irlandia: hrabstwa
| Identyfikator |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Włochy: regiony
| Identyfikator | Kod ISO | Nazwa | Nazwa (j. polski) | Kod pocztowy |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Wenecja Euganejska |VN |
| it-vd |IT-23 |Valle d'Aosta |Dolina Aosty |VD |
| it-um |IT-55 |Umbria |Umbria |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trydent-Górna Adyga |TT |
| it-tc |IT-52 |Toscana |Toskania |TC |
| it-sc |IT-82 |Sicilia |Sycylia |SC |
| it-sd |IT-88 |Sardegna |Sardynia |SD |
| it-pm |IT-21 |Piemonte |Piemont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardia |Lombardia |LM |
| it-lg |IT-42 |Liguria |Liguria |LG |
| it-lz |IT-62 |Lazio |Lacjum |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Wenecja Julijska |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romania |ER |
| it-cm |IT-72 |Campania |Kampania |CM |
| it-lb |IT-78 |Calabria |Kalabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Apulia |PU |
| it-ab |IT-65 |Abruzzo |Abruzja |AB |

### <a name="mexico-states"></a>Meksyk: stany
| Identyfikator | Skrót | Kod ISO | Nazwa | Nazwa (j. polski) | Kod pocztowy |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Jukatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosi |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Queretaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo Leon |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacan |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Meksyk |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Meksyk |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Kalifornia Dolna Południowa |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Kalifornia Dolna |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Holandia: prowincje
| Identyfikator | Kod ISO | Nazwa | Nazwa (j. polski) |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |Holandia Południowa |
| nl-ze |NL-ZE |Zeeland |Zelandia |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |Holandia Północna |
| nl-nb |NL-NB |Noord-Brabant |Brabancja Północna |
| nl-li |NL-LI |Limburg |Limburgia |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Geldria |
| nl-fr |NL-FR |Fryslân |Fryzja |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>Zjednoczone Królestwo: kraje
| Identyfikator | Kod ISO | Nazwa |
| --- | --- | --- |
| gb-wls |GB-WLS |Walia |
| gb-sct |GB-SCT |Szkocja |
| gb-nir |GB-NIR |Irlandia Północna |
| gb-eng |GB-ENG |Anglia |

### <a name="usa-states"></a>Stany Zjednoczone: stany
| Identyfikator | Nazwa | Kod pocztowy |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaje |HI |
| us-fl |Floryda |FL |
| us-la |Luizjana |LA |
| us-ar |Arkansas |AR |
| us-sc |Karolina Południowa |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |Nowy Meksyk |NM |
| us-tx |Teksas |TX |
| us-tn |Tennessee |TN |
| us-nc |Karolina Północna |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Wirginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Kolorado |CO |
| us-md |Maryland |MD |
| us-wv |Wirginia Zachodnia |WV |
| us-de |Delaware |DE |
| us-dc |Dystrykt Kolumbii |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |Kalifornia |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pensylwania |PA |
| us-ny |Nowy Jork |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |Dakota Południowa |SD |
| us-nd |Dakota Północna |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Waszyngton |WA |

