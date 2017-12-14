---
title: "Zmniejszanie rozmiaru skoroszytu programu Excel w celu wyświetlenia go w usłudze Power BI"
description: "Zmniejszanie rozmiaru skoroszytu programu Excel w celu wyświetlenia go w usłudze Power BI"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 2d6d55b8b93ce23528490a3e72616806ebc09beb
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Zmniejszanie rozmiaru skoroszytu programu Excel w celu wyświetlenia go w usłudze Power BI
Do usługi Power BI można przekazać dowolny skoroszyt programu Excel o rozmiarze mniejszym niż 1 GB. Skoroszyt programu Excel może składać się z dwóch części: modelu danych oraz reszty raportu — podstawowej zawartości skoroszytu. Jeśli raport spełnia następujące ograniczenia dotyczące rozmiaru, można zapisać go w usłudze **OneDrive dla Firm**, połączyć się z nim z usługi Power BI i wyświetlać go w usłudze Excel Online:

* Maksymalny rozmiar całego skoroszytu wynosi 1 GB.
* Podstawowa zawartość arkusza może mieć rozmiar do 10 MB.

## <a name="what-makes-core-worksheet-contents-larger-than-10-mb"></a>Co sprawia, że rozmiar podstawowej zawartości arkusza przekracza 10 MB
Poniżej przedstawiono pewne elementy, które mogą sprawić, że rozmiar podstawowej zawartości arkusza przekracza 10 MB:

* Obrazy.
* Cieniowane komórki. [Usuwanie formatowania cieniowania komórki](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Arkusze oznaczone kolorami. [Usuwanie tła arkusza](https://support.office.com/en-US/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Pola tekstowe.
* Obiekty clipart.

Rozważ usunięcie tych elementów, jeśli to możliwe. 

Jeśli raport zawiera model danych, dostępne są także inne opcje: 

* Usuń dane z arkuszy programu Excel i zamiast tego zapisz je w modelu danych. Szczegółowe informacje zawiera sekcja „Usuwanie danych z arkuszy” poniżej. 
* [Utwórz model danych zapewniający wydajną obsługę pamięci](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70), aby zmniejszyć ogólny rozmiar raportu.

Aby wprowadzić te zmiany, należy edytować skoroszyt w programie Excel.

Przeczytaj więcej na temat [limitów rozmiaru plików dla skoroszytów programu Excel w usłudze SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Usuwanie danych z arkuszy
W przypadku importowania danych do programu Excel z poziomu karty dodatku Power Query lub karty Dane programu Excel skoroszyt może zawierać te same dane w tabeli programu Excel, jak i w modelu danych. Duże tabele w arkuszach programu Excel mogą sprawić, że rozmiar podstawowej zawartości arkusza będzie przekraczać 10 MB. Usunięcie tabeli z programu Excel i zachowanie danych w modelu danych może znacznie zmniejszyć rozmiar podstawowej zawartości arkusza raportu. 

Podczas importowania danych do programu Excel należy postępować zgodnie z następującymi wskazówkami:

* **W dodatku Power Query**: wyczyść zaznaczenie pola **Załaduj do arkusza**.
  
  Dane będą importowane tylko do modelu danych, a w arkuszach programu Excel nie zostaną umieszczone żadne dane.
* **Na karcie Dane programu Excel**, jeśli wcześniej zaznaczono pole **Tabela** w kreatorze importowania: wybierz opcję **Istniejące połączenia** \> kliknij połączenie \> **Utwórz tylko połączenie**. Usuń oryginalną tabelę lub tabele utworzone podczas początkowego importowania.
* **Na karcie Dane programu Excel**: nie zaznaczaj pola **Tabela** w obszarze **Importowanie danych**.

## <a name="workbook-size-optimizer"></a>Workbook Size Optimizer
Jeśli skoroszyt zawiera model danych, można uruchomić optymalizator rozmiaru skoroszytu, aby zmniejszyć rozmiar skoroszytu. [Pobierz narzędzie Workbook Size Optimizer](https://www.microsoft.com/en-us/download/details.aspx?id=38793).

## <a name="related-info"></a>Powiązane informacje
[Tworzenie modelu danych zapewniającego wydajną obsługę pamięci](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Używanie linków usługi OneDrive dla Firm w programie Power BI Desktop](desktop-use-onedrive-business-links.md)

