---
title: "Wyłączanie ustawień prywatności"
description: "Jak włączyć funkcję szybkiego łączenia w ramach bramy osobistej w celu wyłączenia ustawień prywatności na potrzeby odświeżania."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
ms.openlocfilehash: 5d754dbdd5d52e7a5b123755015e656d9fb2cea2
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Wyłączanie ustawień prywatności w bramie Power BI Gateway — Personal
> [!NOTE]
> Jest dostępna nowa wersja bramy osobistej dla usługi Power BI o nazwie **lokalna brama danych (tryb osobisty)**. W poniższym artykule opisano poprzednią wersję bramy osobistej o nazwie **Power BI Gateway — Personal**, która zostanie wycofana i przestanie działać po 31 lipca 2017 r. Aby uzyskać informacje na temat nowej wersji bramy osobistej, między innymi sposobu instalowania nowej wersji, zobacz artykuł [**Lokalna brama danych (tryb osobisty)**](service-gateway-personal-mode.md). Funkcja szybkiego łączenia jest również dostępna w nowej wersji bramy osobistej i również jest opisana w tym artykule.
> 
> 

Podczas korzystania z bramy osobistej może występować następujący błąd, w zależności od ustawień prywatności źródeł danych.

> *Wystąpił błąd podczas przetwarzania danych w zestawie danych.*
> 
> *[Nie można połączyć danych] &lt;część zapytania&gt;/&lt;...&gt;/&lt;...&gt; uzyskuje dostęp do źródeł danych z poziomami prywatności, które nie mogą być używane razem. Skompiluj ponownie tę kombinację danych.*
> 
> 

Aby obejść ten błąd, można włączyć funkcję **szybkiego łączenia**. Funkcja **szybkiego łączenia** zignoruje ustawienia prywatności, co umożliwi łączenie różnych źródeł danych.

> [!NOTE]
> Podczas łączenia danych nie są uwzględniane poziomy prywatności. Może to spowodować ujawnienie danych wrażliwych lub poufnych innym źródłom danych podczas łączenia danych.
> 
> 

## <a name="what-is-fast-combine"></a>Co to jest szybkie łączenie?
Aby dowiedzieć się więcej na temat poziomów prywatności i funkcji szybkiego łączenia, zapoznaj się z artykułem [Poziomy prywatności](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540). Domyślnie ustawiony jest poziom prywatności Prywatne, co może skutkować pojawieniem się błędu omówionego powyżej. Dzieje się tak, ponieważ ustawienie Prywatne izoluje źródło danych od innych źródeł. Przykładem sytuacji, w której może być to problemem, jest zapytanie sparametryzowane otrzymujące dane wejściowe z innego źródła danych.

Włączenie funkcji szybkiego łączenia spowoduje zignorowanie ustawienia Prywatne i umożliwi wykonanie zapytania.

## <a name="turn-on-fast-combine"></a>Włączanie funkcji szybkiego łączenia
Aby włączyć funkcję szybkiego łączenia dla bramy osobistej, wykonaj następujące czynności. Lokalna brama danych nie ma tego ustawienia.

1. Otwórz plik **ConnectorConfig.xml**.  Może on znajdować się w jednej z dwóch lokalizacji na maszynie.  Jeśli jesteś administratorem na komputerze, będzie to następująca lokalizacja.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Jeśli nie jesteś administratorem, będzie to następująca lokalizacja.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. Dodaj element **&lt;EnableFastCombine&gt;** z wartością „true” do pliku konfiguracji. Dodanie tego elementu spowoduje włączenie funkcji **szybkiego łączenia**.
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. Zamknij i ponownie uruchom ekran konfiguracji bramy.
4. Zostanie wyświetlony stan, dzięki czemu będzie wiadomo, że funkcja szybkiego łączenia została włączona.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>Wyłączanie funkcji szybkiego łączenia
1. Otwórz plik **ConnectorConfig.xml**.  Może on znajdować się w jednej z dwóch lokalizacji na maszynie.  Jeśli jesteś administratorem na komputerze, będzie to następująca lokalizacja.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Jeśli nie jesteś administratorem, będzie to następująca lokalizacja.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. Usuń element **&lt;EnableFastCombine&gt;** z pliku konfiguracji. Usunięcie tego elementu spowoduje wyłączenie funkcji **szybkiego łączenia**.
3. Zamknij i ponownie uruchom ekran konfiguracji bramy.
4. Stan informujący, że funkcja **szybkiego łączenia** jest włączona, nie będzie już wyświetlany.

## <a name="next-steps"></a>Następne kroki
[Lokalna brama danych (tryb osobisty) —nowa wersja bramy osobistej](service-gateway-personal-mode.md)
[Poziomy prywatności](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Typowe zadania dotyczące zapytań w programie Power BI Desktop](desktop-common-query-tasks.md)  
Więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

