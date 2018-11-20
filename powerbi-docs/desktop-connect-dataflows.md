---
title: Łączenie z danymi utworzonymi przez przepływy danych usługi Power BI w programie Power BI Desktop (wersja beta)
description: Łatwo nawiązuj połączenie z przepływami danych i korzystaj z nich w programie Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f87db1f715118f346e3b8069897e92fd157f881c
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265937"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-beta"></a>Łączenie z danymi utworzonymi przez przepływy danych usługi Power BI w programie Power BI Desktop (wersja beta)
W programie **Power BI Desktop** możesz nawiązać połączenie z danymi utworzonymi przez **przepływy danych usługi Power BI** w taki sam sposób, jak w przypadku dowolnego innego źródła danych w programie Power BI Desktop.

![Łączenie się z przepływami danych](media/desktop-connect-dataflows/connect-dataflows_01.png)

Łącznik **Przepływy danych usługi Power BI (wersja beta)** umożliwia łączenie z jednostkami utworzonymi przez przepływy danych w usłudze Power BI. 

## <a name="considerations-and-limitations"></a>Istotne zagadnienia i ograniczenia

Aby korzystać z tej wersji beta **łącznika przepływów danych usługi Power BI**, musisz mieć uruchomioną najnowszą wersję programu **Power BI Desktop**. Zawsze możesz [pobrać program Power BI Desktop](desktop-get-the-desktop.md) i zainstalować go na komputerze, aby upewnić się, że masz najnowszą wersję.  

> [!NOTE]
> Poprzednia wersja łącznika przepływów danych usługi Power BI wymagała pobrania pliku MEZ i umieszczenia go w folderze. Bieżące wersje programu **Power BI Desktop** obejmują łącznik przepływów danych usługi Power BI, dzięki czemu plik nie jest już wymagany i może powodować konflikt z uwzględnioną wersją łącznika. Jeśli plik MEZ został ręcznie umieszczony w folderze, *musisz* usunąć pobrany plik MEZ z folderu **Dokumenty > Power BI Desktop > Łączniki niestandardowe** w celu uniknięcia konfliktów. 

## <a name="desktop-performance"></a>Wydajność programu Desktop
Program **Power BI Desktop** działa lokalnie na komputerze, na którym został zainstalowany. Wydajność pozyskiwania przepływów danych zależy od różnych czynników. Obejmują one rozmiar danych, procesor i pamięć RAM komputera, przepustowość sieci, odległość od centrum danych oraz inne czynniki.

Wydajność pozyskiwania danych dla przepływów danych można poprawić. Jeśli na przykład rozmiar pozyskiwanych danych jest zbyt duży, aby program **Power BI Desktop** mógł zarządzać nimi na komputerze, można w przepływach danych użyć jednostek połączonych i obliczonych do agregowania danych (w ramach przepływów danych) i pozyskiwania tylko wstępnie przygotowanych, zagregowanych danych. Dzięki temu przetwarzanie dużych ilości danych będzie wykonywane w trybie online w przepływach danych, a nie lokalnie w uruchomionym wystąpieniu programu **Power BI Desktop**. Takie podejście umożliwia programowi Power BI Desktop pozyskiwanie mniejszej ilości danych i zapewnia szybkie i dynamiczne środowisko przepływów danych.


## <a name="next-steps"></a>Następne kroki
Istnieje wiele interesujących czynności, które można wykonać przy użyciu przepływów danych usługi Power BI. Więcej informacji możesz uzyskać w następujących zasobach:

* [Przygotowywanie danych samoobsługi przy użyciu przepływów danych](service-dataflows-overview.md)
* [Tworzenie i używanie przepływów danych w usłudze Power BI](service-dataflows-create-use.md)
* [Używanie obliczonych jednostek w usłudze Power BI Premium (wersja zapoznawcza)](service-dataflows-computed-entities-premium.md)
* [Używanie przepływów danych z lokalnymi źródłami danych (wersja zapoznawcza)](service-dataflows-on-premises-gateways.md)
* [Zasoby dla deweloperów dotyczące przepływów danych usługi Power BI (wersja zapoznawcza)](service-dataflows-developer-resources.md)

Dostępne są także artykuły dotyczące programu **Power BI Desktop**, które mogą się okazać przydatne:

* [Źródła danych w programie Power BI Desktop](desktop-data-sources.md)
* [Kształtowanie i łączenie danych w programie Power BI Desktop](desktop-shape-and-combine-data.md)
* [Wprowadzanie danych bezpośrednio w programie Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

