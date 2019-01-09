---
title: Nawiązywanie połączenia z usługą Zuora przy użyciu usługi Power BI
description: Usługa Zuora dla usługi Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 605cd2f135ff6d8626586abbd503bcb44687931d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008608"
---
# <a name="connect-to-zuora-with-power-bi"></a>Nawiązywanie połączenia z usługą Zuora przy użyciu usługi Power BI
Usługa Zuora dla usługi Power BI pozwala wizualizować ważne informacje dotyczące przychodów, rozliczeń i subskrypcji. Za pomocą domyślnego pulpitu nawigacyjnego i raportów można analizować trendy użycia, śledzić rozliczenia i płatności oraz monitorować przychody cykliczne. Pulpit nawigacyjny można również dostosować do własnych potrzeb związanych z raportowaniem.

Połącz się z usługą [Zuora](https://app.powerbi.com/getdata/services/Zuora) dla usługi Power BI.

## <a name="how-to-connect"></a>Jak nawiązać połączenie
1. Wybierz pozycję **Pobierz dane** w dolnej części okienka nawigacji po lewej stronie.

   ![](media/service-connect-to-zuora/getdata.png)
2. W polu **Usługi** wybierz pozycję **Pobierz**.

   ![](media/service-connect-to-zuora/services.png)
3. Wybierz pozycję **Zuora** \> **Pobierz**.

   ![](media/service-connect-to-zuora/zuora.png)
4. Podaj adres URL usługi Zuora. Zwykle adres URL to „<https://www.zuora.com>”. Poniżej znajdują się szczegółowe informacje dotyczące [znajdowania tych parametrów](#FindingParams).

   ![](media/service-connect-to-zuora/params.png)
5. W polu **Metoda uwierzytelniania** wybierz opcję **Podstawowa**, podaj nazwę użytkownika i hasło (z rozróżnianiem wielkości liter), a następnie wybierz pozycję **Zaloguj**.

    ![](media/service-connect-to-zuora/creds.png)
6. Po zatwierdzeniu proces importowania rozpocznie się automatycznie. Po zakończeniu nowy pulpit nawigacyjny, raport i model zostaną wyświetlone w okienku nawigacji. Wybierz pulpit nawigacyjny, aby wyświetlić zaimportowane dane.

     ![](media/service-connect-to-zuora/dashboard.png)

**Co teraz?**

* Spróbuj [zadać pytanie w polu funkcji Pytania i odpowiedzi](consumer/end-user-q-and-a.md) w górnej części pulpitu nawigacyjnego
* [Zmień kafelki](service-dashboard-edit-tile.md) na pulpicie nawigacyjnym.
* [Wybierz kafelek](consumer/end-user-tiles.md), aby otworzyć raport źródłowy.
* Dla zestawu danych jest zaplanowane codzienne odświeżanie, ale możesz zmienić harmonogram odświeżania lub odświeżyć go na żądanie przy użyciu polecenia **Odśwież teraz**

## <a name="whats-included"></a>Zawartość pakietu
Pakiet zawartości umożliwia pobieranie poniższych tabel przy użyciu interfejsu API Zuora AQUA:

| Tabele |  |  |
| --- | --- | --- |
| Account |InvoiceItemAdjustment |Refund |
| AccountingCode |Payment |RevenueSchedule |
| AccountingPeriod |PaymentMethod |RevenueScheduleItem |
| BillTo |Product |Subscription |
| DateDim |ProductRatePlan |TaxationItem |
| Invoice |ProductRatePlanCharge |Usage |
| InvoiceAdjustment |RatePlan | |
| InvoiceItem |RatePlanCharge | |

Pakiet zawartości udostępnia również następujące miary obliczeniowe:

| Miara | Opis | Obliczenia przykładowe |
| --- | --- | --- |
| Konto: Płatności |Łączna kwota płatności w danym okresie na podstawie daty płatności. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND    Payment.EffectiveDate >= TimePeriod.StartDate |
| Konto: Zwroty |Łączna kwota zwrotów w danym okresie na podstawie daty zwrotu. Kwota jest podawana jako liczba ujemna. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate =< TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Konto: Płatności netto |Płatności oraz zwroty na koncie w danym okresie. |Account.Payments + Account.Refunds |
| Konto: Aktywne konta |Liczba kont, które były aktywne w danym okresie. Rozpoczęcie korzystania z subskrypcji musi przypadać przed datą początkową tego okresu (lub w dzień odpowiadający tej dacie). |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>OR<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Konto: Średni przychód cykliczny |Miesięczny przychód cykliczny brutto na aktywnym koncie w danym okresie. |Miesięczny przychód cykliczny brutto / Account.ActiveAccounts |
| Konto: Anulowane subskrypcje |Liczba kont, na których anulowano subskrypcję w danym okresie. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Konto: Błędy płatności |Łączna wartość błędów płatności. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Element planu przychodów: Ujęty przychód |Łączny ujęty przychód w okresie księgowym. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Subskrypcja: Nowe subskrypcje |Liczba nowych subskrypcji w danym okresie. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = "1"<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Faktura: Invoice Items |Łączna kwota opłat za pozycje faktur w danym okresie. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Faktura: Taxation Items |Łączna kwota pozycji podatku w danym okresie. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Faktura: Invoice Item Adjustments |Łączna kwota korekt pozycji faktur w danym okresie. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Faktura: Invoice Adjustments |Łączna kwota korekt faktur w danym okresie. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Faktura: Net Billings |Suma pozycji faktur, pozycji podatku, korekt pozycji faktur i korekt faktur w danym okresie. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Faktura: Saldo zaległości faktur |Suma zaksięgowanych sald faktur. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Faktura: Rozliczenia brutto |Suma opłat za pozycje zaksięgowanych faktur w danym okresie. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND    Invoice.InvoiceDate >= TimePeriod.StartDate |
| Faktura: Suma korekt |Suma przetworzonych korekt faktur i korekt pozycji faktur skojarzonych z zaksięgowanymi fakturami. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND    invoiceItemAdjustment.Status = "Processed" |
| Opłata za plan taryfowy: Miesięczny przychód cykliczny brutto |Łączny miesięczny przychód cykliczny z subskrypcji w danym okresie. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND        RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Wymagania systemowe
Wymagany jest dostęp do interfejsu API Zuora.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Znajdowanie parametrów
Podaj adres URL, którego zwykle używasz do uzyskania dostępu do danych usługi Zuora. Prawidłowe opcje to:  

* https://www.zuora.com  
* Adres URL odpowiadający wystąpieniu usługi  

## <a name="troubleshooting"></a>Rozwiązywanie problemów
Pakiet zawartości Zuora umożliwia pobieranie wielu różnych informacji z konta Zuora. W przypadku niekorzystania z pewnych funkcji odpowiednie kafelki lub raporty są puste. Jeśli podczas ładowania wystąpią problemy, skontaktuj się z pomocą techniczną usługi Power BI.

## <a name="next-steps"></a>Następne kroki
[Wprowadzenie do usługi Power BI](service-get-started.md)

[Pobieranie danych w usłudze Power BI](service-get-data.md)
