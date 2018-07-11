---
title: Używanie języka R w Edytorze zapytań w usłudze Power BI
description: Używanie języka R w Edytorze zapytań programu Power BI Desktop do zaawansowanej analizy.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c4e9a3de86c3bc4e714baa1ff59e84ea8be60556
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2018
ms.locfileid: "37598845"
---
# <a name="using-r-in-query-editor"></a>Używanie języka R w Edytorze zapytań
W **Edytorze zapytań** programu Power BI Desktop możesz używać języka **R**, czyli języka programowania używanego powszechnie przez statystyków, naukowców i analityków danych. Dzięki integracji z językiem R **Edytor zapytań** umożliwia oczyszczanie danych przy użyciu języka R, a także zaawansowane kształtowanie i analizowanie danych w zestawach danych — na przykład uzupełnianie brakujących danych, przewidywanie i grupowanie danych. **R** to zaawansowany język, którego możesz używać w **Edytorze zapytań** do przygotowywania modelu danych i tworzenia raportów.

## <a name="installing-r"></a>Instalowanie języka R
Aby korzystać z języka **R** w **Edytorze zapytań** programu Power BI Desktop, musisz zainstalować język **R** na komputerze lokalnym. Język **R** możesz pobrać i zainstalować bezpłatnie z wielu miejsc, w tym ze [strony pobierania Revolution Open](https://mran.revolutionanalytics.com/download/) i [repozytorium CRAN](https://cran.r-project.org/bin/windows/base/).

## <a name="using-r-in-query-editor"></a>Używanie języka R w Edytorze zapytań
Sposób korzystania z języka **R** w **Edytorze zapytań** przedstawiono na przykładzie zestawu danych giełdowych opartego na pliku CSV, który możesz [pobrać tutaj](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv) i w którym możesz wykonywać czynności opisane w tym temacie. Podczas pracy z tym przykładem wykonasz następujące czynności:

1. Na początek załaduj dane do programu **Power BI Desktop**. Załaduj plik *EuStockMarkets_NA.csv* pochodzący z tego przykładu i wybierz polecenie **Pobierz dane > CSV** na karcie **Narzędzia główne** wstążki w programie **Power BI Desktop**.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_1.png)
2. Zaznacz plik i wybierz pozycję **Otwórz**. Plik CSV zostanie wyświetlony w oknie dialogowym **Plik CSV**.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_2.png)
3. Załadowane dane zostaną wyświetlone w okienku **Pola** w programie Power BI Desktop.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_3.png)
4. Otwórz **Edytor zapytań**, wybierając pozycję **Edytuj zapytania** na karcie **Narzędzia główne** w programie **Power BI Desktop**.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_4.png)
5. Na karcie **Przekształć** wybierz pozycję **Uruchom skrypt języka R**, aby otworzyć edytor **Uruchamianie skryptu języka R** (widoczny w następnym kroku). Zwróć uwagę, że w wierszach 15 i 20 brakuje danych, podobnie jak w innych wierszach niewidocznych na ilustracji. Wykonując poniższe czynności, możesz uzupełnić dane w tych wierszach przy użyciu języka R.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_5d.png)
6. W tym przykładzie wprowadź następujący kod skryptu:

       library(mice)
       tempData <- mice(dataset,m=1,maxit=50,meth='pmm',seed=100)
       completedData <- complete(tempData,1)
       output <- dataset
       output$completedValues <- completedData$"SMI missing values"

   > [!NOTE]
   > Aby powyższy kod skryptu działał prawidłowo, wymagane jest zainstalowanie biblioteki *mice* w środowisku języka R. Aby zainstalować bibliotekę mice, w instalacji języka R uruchom następujące polecenie: |      > install.packages('mice')
   > 
   > 

   Po umieszczeniu w oknie dialogowym **Uruchamianie skryptu języka R** kod wygląda następująco:

   ![](media/desktop-r-in-query-editor/r-in-query-editor_5b.png)
7. Po wybraniu przycisku **OK** w **Edytorze zapytań** zostanie wyświetlone ostrzeżenie dotyczące prywatności danych.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_6.png)
8. Aby skrypty języka R działały prawidłowo w usłudze Power BI, wszystkie źródła danych muszą być ustawione jako *publiczne*. Aby uzyskać więcej informacji na temat ustawień prywatności i ich skutków, zobacz [Poziomy prywatności](desktop-privacy-levels.md).

   ![](media/desktop-r-in-query-editor/r-in-query-editor_7.png)

   W okienku **Pola** zostanie wyświetlona nowa kolumna o nazwie *completedValues* (Uzupełnione wartości). Zwróć uwagę na brakujące elementy danych, na przykład w wierszach 15 i 18. W następnej sekcji przedstawiono, jak język R sobie z nimi radzi.


Wystarczy pięć wierszy skryptu języka R, aby **Edytor zapytań** uzupełnił brakujące wartości przy użyciu modelu predykcyjnego.

## <a name="creating-visuals-from-r-script-data"></a>Tworzenie wizualizacji na podstawie danych skryptu języka R
Teraz można utworzyć wizualizację, aby zobaczyć, w jaki sposób skrypt języka R korzystający z biblioteki *mice* uzupełnił brakujące wartości, co pokazano na poniższej ilustracji:

![](media/desktop-r-in-query-editor/r-in-query-editor_8a.png)

Po utworzeniu tej i wszelkich innych wymaganych wizualizacji w programie **Power BI Desktop** można zapisać plik programu **Power BI Desktop** (w formacie pbix), a następnie używać tego modelu danych, wraz z zawartymi w nim skryptami języka R, w usłudze Power BI.

> [!NOTE]
> Chcesz zobaczyć gotowy plik pbix po wykonaniu tych czynności? Masz szczęście — możesz pobrać gotowy plik programu **Power BI Desktop** używany w tych przykładach [tutaj](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/Complete%20Values%20with%20R%20in%20PQ.pbix).

Po przekazaniu pliku pbix do usługi Power BI należy wykonać kilka dodatkowych czynności w celu włączenia odświeżania danych (w usłudze Power BI) oraz aktualizowania wizualizacji w usłudze (co wymaga włączenia dostępu do języka R dla danych). Poniżej opisano te dodatkowe czynności:

* **Włącz zaplanowane odświeżanie dla zestawu danych** — aby włączyć zaplanowane odświeżanie skoroszytu zawierającego zestaw danych ze skryptami języka R, zobacz artykuł [Konfigurowanie zaplanowanego odświeżania](refresh-scheduled-refresh.md), który zawiera również informacje o **bramie osobistej**.
* **Zainstaluj bramę osobistą** — na komputerze, na którym znajduje się plik i na którym zainstalowano język R, należy zainstalować **bramę osobistą**. Usługa Power BI musi uzyskać dostęp do tego skoroszytu w celu ponownego renderowania zaktualizowanych wizualizacji. Możesz uzyskać więcej informacji na temat [instalowania i konfigurowania bramy osobistej](service-gateway-personal-mode.md).

## <a name="limitations"></a>Ograniczenia
Zapytania zawierające skrypty języka R utworzone w **Edytorze zapytań** podlegają pewnym ograniczeniom:

* Wszystkie źródła danych dla języka R muszą być ustawione jako *Publiczne*, tak samo jak wszystkie pozostałe kroki zapytania utworzone w **Edytorze zapytań**. Aby przejść do ustawień źródła danych, w programie **Power BI Desktop** wybierz kolejno pozycje **Plik > Opcje i ustawienia > Ustawienia źródła danych**.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_9.png)

  W oknie dialogowym **Ustawienia źródła danych** zaznacz źródła danych, a następnie wybierz pozycję **Edytuj uprawnienia** i upewnij się, że **Poziom prywatności** został ustawiony na *Publiczne*.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_10.png)    
* Aby włączyć zaplanowane odświeżanie wizualizacji lub zestawu danych ze skryptami języka R, należy włączyć **Zaplanowane odświeżanie** oraz zainstalować **Bramę osobistą** na komputerze, na którym znajduje się skoroszyt oraz instalacja języka R. Aby dowiedzieć się więcej o obu tych czynnościach, zobacz poprzednią sekcję tego artykułu zawierającą linki do dodatkowych informacji.

Przy użyciu języka R i zapytań niestandardowych można wykonywać wiele różnorodnych czynności — poznaj je i kształtuj dane dokładnie tak, jak chcesz.

