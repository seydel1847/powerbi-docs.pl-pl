---
title: "Tworzenie widoku pulpitu nawigacyjnego usługi Power BI dla telefonów komórkowych"
description: "Dowiedz się, jak tworzyć niestandardowy widok pulpitu nawigacyjnego w usłudze Power BI specjalnie do wyświetlenia na telefonach komórkowych."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/12/2017
ms.author: maggies
ms.openlocfilehash: fca163588801633ad3eac227ceea84be17089713
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-view-of-a-power-bi-dashboard-optimized-for-mobile-phones"></a>Tworzenie widoku pulpitu nawigacyjnego usługi Power BI zoptymalizowanego dla telefonów komórkowych
Podczas wyświetlania pulpitów nawigacyjnych w aplikacji mobilnej usługi Power BI na telefonie możesz zauważyć, że kafelki pulpitu nawigacyjnego zostały ułożone po kolei i mają ten sam rozmiar. W usłudze Power BI możesz utworzyć dostosowany widok dowolnego pulpitu nawigacyjnego, który należy do Ciebie, szczególnie dla telefonów.

Po obróceniu telefonu na boki zobaczysz pulpit nawigacyjny tak, jak został rozmieszczony w usłudze, a nie jak został zaprojektowany dla telefonu.

> [!NOTE]
> Podczas edytowania widoku telefonu każda osoba oglądająca pulpit nawigacyjny na telefonie zobaczy wprowadzane zmiany w czasie rzeczywistym. Na przykład, jeśli odpiąć wszystkie kafelki w widoku pulpitu nawigacyjnego telefonu, pulpit nawigacyjny w telefonie nagle nie będzie miał kafelków. 
> 
> 

## <a name="create-a-phone-view-of-a-dashboard"></a>Tworzenie widoku pulpitu nawigacyjnego dla telefonu
1. Otwórz pulpit nawigacyjny w usłudze Power BI.
2. Wybierz strzałkę obok pozycji **Widok internetowy** w prawym górnym rogu > wybierz **Widok telefonu**.

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-dashboard.png)

    Jeśli pulpit nawigacyjny nie należy do Ciebie, nie zobaczysz tej opcji.

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-canvas.png)

    Zostanie otwarty widok edycji pulpitu nawigacyjnego telefonu. W tym miejscu możesz odpiąć, zmienić rozmiar i zmienić układ kafelków, aby dopasować widok telefonu. Nie powoduje to zmiany internetowej wersji pulpitu nawigacyjnego.


1. Wybierz kafelek, aby go przeciągnąć, zmienić rozmiar lub odpiąć. Możesz zauważyć,że inne kafelki odsuną się z drogi podczas przeciągania kafelka.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-unpin-tile-phone-dashboard.png)
   
    Odpięte kafelki przechodzą do okienka odpiętych kafelków, gdzie zostają do chwili ich ponownego dodania.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-post-edit.png)
2. Jeśli zmienisz zdanie, wybierz pozycję **Resetuj kafelki**, aby przywrócić je w ich wcześniejszym rozmiarze i kolejności.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-reset-tiles.png)
   
    Samo otwarcie widoku Edycja telefonu w usłudze Power BI nieco zmienia rozmiar i kształt kafelków w telefonie. Dlatego przed otwarciem widoku Edycja telefonu przywrócić dokładny stan pulpitu nawigacyjnego i wybierz pozycję **Resetuj kafelki**.
3. Gdy układ pulpitu nawigacyjnego telefonu jest zadowalający, wybierz strzałkę obok pozycji **Widok telefonu** w prawym górnym rogu > Wybierz pozycję **Widok internetowy**.
   
    Usługa Power BI automatycznie zapisuje układ telefonu.

## <a name="next-steps"></a>Następne kroki
* [Tworzenie raportów zoptymalizowanych pod kątem aplikacji usługi Power BI na telefony](desktop-create-phone-report.md)
* [Tworzenie dynamicznych elementów wizualnych zoptymalizowanych pod kątem dowolnej wielkości](desktop-create-responsive-visuals.md)
* Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

