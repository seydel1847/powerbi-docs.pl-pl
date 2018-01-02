---
title: "Jak znaleźć klucz produktu serwera raportów"
description: "Dowiedz się, jak znaleźć klucz produktu serwera raportów usługi Power BI, aby zainstalować serwer w środowisku produkcyjnym."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: 64bf842bec0598210e54d73ee2697586fce96a1f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-find-your-report-server-product-key"></a>Jak znaleźć klucz produktu serwera raportów
Dowiedz się, jak znaleźć klucz produktu serwera raportów usługi Power BI, aby zainstalować serwer w środowisku produkcyjnym.

<iframe width="640" height="360" src="https://www.youtube.com/embed/6CQnf-NGtpU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

Masz pobrany serwer raportów usługi Power BI i umowę SQL Server Enterprise Software Assurance. Lub masz zakupioną usługę Power BI Premium. Chcesz zainstalować serwer w środowisku produkcyjnym, ale potrzebujesz klucza produktu, aby to zrobić. Gdzie jest klucz produktu? 

Klucz produktu jest w jednym z dwóch miejsc, w zależności od tego, co zostało zakupione.

## <a name="purchased-power-bi-premium"></a>Zakupiona usługa Power BI Premium
Jeśli zakupiono usługę Power BI Premium, na karcie **Ustawienia pojemności** w portalu administracyjnym usługi Power BI będzie dostępny klucz produktu serwera raportów usługi Power BI. Jest on dostępny tylko dla administratorów globalnych lub użytkowników z przypisaną rolą administratora usługi Power BI.

![Klucz serwera raportów usługi Power BI w obszarze Ustawienia wersji Premium](media/find-product-key/pbirs-product-key.png)

Wybranie pozycji **Klucz serwera raportów usługi Power BI** spowoduje wyświetlenie okna dialogowego z Twoim kluczem produktu. Możesz skopiować go i użyć podczas instalacji.

![Klucz produktu serwera raportów usługi Power BI](media/find-product-key/pbirs-product-key-dialog.png)

## <a name="purchased-software-assurance-agreeemnt"></a>Zakupiona umowa Software Assurance
Jeśli masz licencję programu SQL Server Enterprise z programem SA, możesz uzyskać kod produktu w witrynie [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/). Sprawdź w obszarze najnowszego dodatku service pack, aby uzyskać najnowszą wersję programu SQL Server. Jeśli nie widzisz jej tam, sprawdź w obszarze wydania RTM najnowszej wersji programu SQL Server.

> [!NOTE]
> Musisz szukać w sekcji pobierania. Nie w sekcji kluczy.
> 
> 

![](media/find-product-key/vlsc-download.png "Volume Licensing Service Center")

## <a name="next-steps"></a>Następne kroki
[Szybki start: instalowanie serwera raportów usługi Power BI](quickstart-install-report-server.md)  
[Instalowanie programu Power BI Desktop zoptymalizowanego pod kątem serwera raportów usługi Power BI](install-powerbi-desktop.md)  
[Instalowanie programu Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Pobieranie programu SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](https://community.powerbi.com/)

