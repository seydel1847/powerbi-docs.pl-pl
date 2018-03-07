---
title: "Power BI Gateway — Personal"
description: "Power BI Gateway — Personal"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 06ed973b3b16f5ac8ed8bef484d48af994a4e5f2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/24/2018
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway — Personal
> [!NOTE]
> Jest dostępna nowa wersja bramy osobistej dla usługi Power BI o nazwie **lokalna brama danych (tryb osobisty)**. W poniższym artykule opisano poprzednią wersję bramy osobistej o nazwie **Power BI Gateway — Personal**, która zostanie wycofana i przestanie działać po 31 lipca 2017 r. Aby uzyskać informacje na temat nowej wersji bramy osobistej, między innymi sposobu instalowania nowej wersji, zobacz artykuł [**Lokalna brama danych (tryb osobisty)**](service-gateway-personal-mode.md).
> 
> 

Brama **Power BI Gateway — Personal** działa jako mostek zapewniający szybki i bezpieczny transfer danych między usługą Power BI i lokalnymi źródłami danych, które obsługują [odświeżanie](refresh-data.md). Celem niniejszego artykułu jest dostarczenie szczegółowego opisu sposobu działania bramy i pomoc w ustaleniu, czy brama jest Ci potrzebna. Dołączyliśmy także ten [przydatny film wideo](https://www.youtube.com/watch?v=de58vROLqZI) na temat bramy osobistej. 

Brama jest instalowana i uruchamiana jako usługa na komputerze. Jako usługa działa, korzystając z konta systemu Windows określonego podczas konfiguracji. W pewnych przypadkach brama działa jako aplikacja. Bardziej szczegółowo omówimy ten temat później.

Gdy usługa Power BI odświeża dane z lokalnego źródła danych, brama zapewnia kontu Power BI odpowiednie uprawnienia do nawiązywania połączeń i wysyłania zapytań dotyczących danych.

Transfer danych między usługą Power BI a bramą jest zabezpieczony za pomocą usługi [Azure Service Bus](http://azure.microsoft.com/documentation/services/service-bus/). Usługa Service Bus tworzy bezpieczny kanał między usługą Power BI i komputerem. Ponieważ brama zapewnia to bezpieczne połączenie, zazwyczaj nie trzeba otwierać portu w zaporze.

Zanim przejdziemy do szczegółowych informacji na temat bramy, spójrzmy na niektóre pojęcia używane w usłudze Power BI:

*Zestaw danych* to dane przekazane do usługi Power BI ze źródła danych online lub lokalnego źródła danych. Zestaw danych jest tworzony wtedy, gdy używasz funkcji Pobierz dane w celu nawiązania połączenia i przekazania danych. Zestawy danych są wyświetlane w okienku Mój obszar roboczy w obszarze roboczym usługi Power BI w przeglądarce. Gdy tworzysz raporty i przypinasz kafelki do pulpitów nawigacyjnych, widzisz dane ze swoich zestawów danych.

*Źródło danych* to miejsce przechowywania danych, które są przekazywane do zestawu danych. To może być cokolwiek: baza danych, arkusz programu Excel, usługa internetowa itd. W przypadku skoroszytów programu Excel możesz utworzyć prosty arkusz zawierający wiersze danych i będzie on uznawany za źródło danych. W tym samym skoroszycie możesz także użyć funkcji Power Query lub Power Pivot programu Excel, aby nawiązywać połączenia i wysyłać zapytania dotyczące danych zarówno ze źródeł danych online, jak i lokalnych źródeł danych. W programie Power BI Desktop możesz nawiązywać połączenia i wysyłać zapytania dotyczące danych zarówno ze źródeł danych online, jak i lokalnych źródeł danych, używając funkcji Pobierz dane.

Bramę osobistą instaluje się za pośrednictwem lokalnej bramy danych. Możesz ją pobrać na [stronie bramy Power BI Gateway](https://powerbi.microsoft.com/gateway/).

## <a name="do-i-need-a-gateway"></a>Czy potrzebuję bramy?
Zanim zainstalujesz bramę, musisz dowiedzieć się, czy na pewno jej potrzebujesz. Tak naprawdę zależy to od źródeł danych:

### <a name="on-premises-data-sources"></a>Lokalne źródła danych
Brama osobista *jest niezbędna* do odświeżania zestawów danych, które uzyskują dane z obsługiwanego lokalnego źródła danych w Twojej organizacji.

Funkcje ODŚWIEŻ TERAZ i ZAPLANUJ ODŚWIEŻANIE są obsługiwane za pośrednictwem bramy w przypadku zestawów danych przekazanych z takich źródeł, jak:

* Skoroszyty programu Microsoft Excel 2013 (lub nowszego), w których do nawiązywania połączeń i wysyłania zapytań dotyczących danych z obsługiwanego lokalnego źródła danych jest używana funkcja Power Query lub Power Pivot. Odświeżanie obsługują wszystkie lokalne źródła danych widoczne w obszarze Pobierz dane zewnętrzne funkcji Power Query lub Power Pivot z wyjątkiem źródeł danych Plik usługi Hadoop (HDFS) i Microsoft Exchange.
* Pliki programu Microsoft Power BI Desktop, w których do nawiązywania połączeń i wysyłania zapytań dotyczących danych z obsługiwanego lokalnego źródła danych jest używana funkcja Pobierz dane. Odświeżanie obsługują wszystkie lokalne źródła danych widoczne w obszarze Pobierz dane z wyjątkiem źródeł danych Plik usługi Hadoop (HDFS) i Microsoft Exchange.

### <a name="online-data-sources"></a>Źródła danych online
Brama *jest wymagana tylko wtedy*, gdy używasz funkcji [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx). W pozostałych przypadkach brama *nie* jest wymagana do odświeżania zestawów danych, które uzyskują dane tylko ze źródła danych online.

> [!NOTE]
> Jeśli używasz funkcji [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx), potrzebujesz bramy tylko w przypadku, gdy zestaw danych lub raport opublikowano ponownie po 18 listopada 2016 r.
> 
> 

Funkcje ODŚWIEŻ TERAZ i ZAPLANUJ ODŚWIEŻANIE są obsługiwane bez bramy w przypadku zestawów danych przekazanych z takich źródeł, jak:

* Pakiety zawartości ze źródeł danych online (pakiety zawartości\\usługi). Domyślnie zestawy danych z pakietów zawartości są automatycznie odświeżane raz dziennie, ale można także odświeżać je ręcznie lub skonfigurować harmonogram odświeżania.
* Skoroszyty programu Microsoft Excel 2013 (lub nowszego), w których do nawiązywania połączeń i wysyłania zapytań dotyczących danych ze źródła danych online jest używana funkcja Power Query lub Power Pivot.
* Pliki programu Microsoft Power BI Desktop, w których do nawiązywania połączeń i wysyłania zapytań dotyczących danych ze źródła danych online jest używana funkcja Pobierz dane.

**Pytanie:** Co w przypadku, gdy skoroszyt programu Excel lub plik programu Power BI Desktop uzyskuje dane zarówno ze źródeł danych online, jak i lokalnych źródeł danych?

**Odpowiedź:** Brama *jest* wymagana. Aby odświeżać dane z lokalnych źródeł danych, musisz zainstalować i skonfigurować bramę.

**Pytanie:** Co w przypadku, gdy skoroszyt programu Excel zawiera tylko wiersze danych ręcznie wpisane przeze mnie?**

**Odpowiedź:** Brama *nie jest* wymagana. Zainstalowanie i skonfigurowanie bramy jest konieczne tylko wtedy, gdy w skoroszycie do wysyłania zapytań oraz ładowania danych do modelu danych z obsługiwanego lokalnego źródła danych jest używana funkcja Power Query lub Power Pivot

## <a name="setting-up-a-gateway-for-the-first-time"></a>Konfigurowanie bramy po raz pierwszy
Konfigurowanie bramy po raz pierwszy to proces składający się z trzech etapów:

1. Pobieranie i instalowanie bramy
2. Konfigurowanie bramy
3. Logowanie się do źródeł danych w usłudze Power BI

Przyjrzyjmy się bliżej poszczególnym etapom.

### <a name="download-and-install-a-gateway"></a>Pobieranie i instalowanie bramy
> [!NOTE]
> Istnieje nowa wersja bramy osobistej dla usługi Power BI nazywana **lokalną bramą danych (tryb osobisty)**. W tym artykule opisano poprzednią wersję bramy osobistej o nazwie **Power BI Gateway — Personal**, która zostanie wycofana i przestanie działać po 31 lipca 2017 r. Aby uzyskać informacje na temat nowej wersji bramy osobistej, między innymi sposobu instalowania nowej wersji, zobacz artykuł [**Lokalna brama danych (tryb osobisty)**](service-gateway-personal-mode.md).
> 
> 

Po kliknięciu po raz pierwszy pozycji ODŚWIEŻ TERAZ lub ZAPLANUJ ODŚWIEŻANIE dla obsługiwanego zestawu danych zostanie wyświetlony monit o zainstalowanie bramy. W celu pobrania bramy możesz również wybrać pozycję **Brama danych** w menu Pliki do pobrania. Pobierz [lokalną bramę danych](http://go.microsoft.com/fwlink/?LinkID=820925).

Możesz wybrać pozycję **Brama osobista**, zamiast **Lokalna brama danych**, aby zainstalować bramę tylko dla siebie.

Instalowanie bramy nie jest skomplikowane. Musisz wybrać lokalizację, w której zostaną zainstalowane pliki, oraz przeczytać i zaakceptować umowę licencyjną, tak jak w przypadku każdej innej aplikacji. Jednak trzeba wiedzieć kilka ważnych rzeczy. W szczególności musisz znać typ komputera, na którym instalujesz bramę, oraz typ konta, za pomocą którego logujesz się do systemu Windows na tym komputerze.

> [!NOTE]
> Brama musi mieć dostęp do źródła danych. Jeśli Twój komputer osobisty nie może połączyć się ze źródłem danych, rozważ zainstalowanie [lokalnej bramy danych](service-gateway-onprem.md) na komputerze, który ma dostęp do źródła danych. Przykładem takiej sytuacji może być program SQL Server zainstalowany na maszynie wirtualnej hostowanej na platformie Azure. Twój komputer osobisty może nie mieć dostępu do maszyny wirtualnej. Zamiast tego możesz zainstalować lokalną bramę danych na maszynie wirtualnej i skonfigurować źródło danych w usłudze Power BI.
> 
> 

### <a name="computer-type"></a>Typ komputera
Typ komputera, na którym instalujesz bramę, ma znaczenie.

> [!NOTE]
> Brama osobista jest obsługiwana tylko w 64-bitowych systemach operacyjnych Windows.
> 
> 

Na laptopie — aby zostało przeprowadzone zaplanowane odświeżanie, brama musi działać. Laptopy na ogół częściej są wyłączone lub w trybie uśpienia niż w trybie pracy. Jeśli instalujesz bramę na laptopie, ustaw czas zaplanowanego odświeżania w godzinach, w których komputer pracuje. W przeciwnym razie próba odświeżenia nie będzie ponawiana aż do następnej godziny zaplanowanego odświeżania.

Na komputerze stacjonarnym — w tym przypadku nie ma zbyt wielu problemów. Wystarczy się upewnić, że komputer i brama działają w godzinach zaplanowanego odświeżania. Wiele komputerów stacjonarnych przechodzi w tryb uśpienia. W takim przypadku nie można przeprowadzić zaplanowanego odświeżania.

Po zainstalowaniu bramy nie musisz instalować kolejnej. Jedna brama działa z dowolną liczbą obsługiwanych zestawów danych. Nie musisz również instalować bramy na komputerze, z którego przekazujesz skoroszyt i pliki programu Power BI Desktop. Oto przykład: powiedzmy, że masz skoroszyt programu Excel, który łączy się ze źródłem danych SQL Server w Twojej organizacji. Do przekazania skoroszytu z laptopa została użyta funkcja Pobierz dane. Masz również komputer stacjonarny, który działa przez cały czas i na którym została zainstalowana i skonfigurowana brama. W usłudze Power BI logujesz się do źródeł danych i konfigurujesz harmonogram odświeżania zestawu danych.  O godzinie zaplanowanego odświeżania usługa Power BI nawiązuje bezpieczne połączenie z bramą zainstalowaną na Twoim komputerze stacjonarnym. Następnie bezpiecznie łączy się ze źródłami danych, aby pobrać aktualizacje. W przypadku odświeżania nie ma komunikacji z oryginalnym skoroszytem, który został przekazany z laptopa.

> [!NOTE]
> Na jednym komputerze możesz zainstalować bramę osobistą i bramę przedsiębiorstwa.
> 
> 

### <a name="windows-account"></a>Konto systemu Windows
Po zainstalowaniu bramy logujesz się do swojego komputera, używając konta systemu Windows. Typ uprawnień Twojego konta systemu Windows ma wpływ na sposób instalowania i działania bramy w systemie Windows.

Jeśli logujesz się do systemu Windows:

|  | Z uprawnieniami administratora | Bez uprawnień administratora |
| --- | --- | --- |
| **Power BI Gateway — Personal działa jako** |Usługa |Aplikacja |
| **Zaplanowane odświeżanie** |O ile komputer i usługa bramy są uruchomione, zalogowanie się na czas wykonywania zaplanowanego odświeżania nie jest wymagane. |Trzeba się zalogować do komputera na czas wykonywania zaplanowanego odświeżania. |
| **Zmiana hasła do konta systemu Windows** |Musisz zmienić hasło w usłudze bramy. Jeśli hasło używane przez bramę jest już nieaktualne, odświeżanie zakończy się niepowodzeniem. |Brama zawsze działa, korzystając z konta i hasła, które zostały użyte do zalogowania. W przypadku niezalogowania się do systemu Windows brama nie działa i odświeżanie kończy się niepowodzeniem. |

### <a name="configure-the-gateway"></a>Konfigurowanie bramy
Po zakończeniu pracy Kreatora instalacji zostanie wyświetlony monit o uruchomienie Kreatora konfiguracji. Konfigurowanie bramy nie jest skomplikowane. Musisz zalogować się do usługi Power BI z poziomu kreatora. Kreator potrzebuje tego do nawiązania połączenia z kontem Power BI w usłudze Power BI.

W przypadku zalogowania się do systemu Windows za pomocą konta z uprawnieniami administratora zostanie wyświetlony monit o wprowadzenie poświadczeń konta systemu Windows. Możesz określić inne konto systemu Windows, ale pamiętaj, że uprawnienia decydują o sposobie działania bramy. Usługa bramy zostanie uruchomiona przy użyciu tego konta.

### <a name="sign-in-to-data-sources"></a>Logowanie się do źródeł danych
Po zakończeniu pracy Kreatora konfiguracji oraz skonfigurowaniu i uruchomieniu bramy musisz określić typ uwierzytelniania i zalogować się do każdego ze źródeł danych zestawu danych. Ten krok wykonasz w usłudze Power BI.

![](media/personal-gateway/pg_dataset_settings_signin.png)

Wystarczy tylko raz określić typ uwierzytelniania i zalogować się do źródła danych. Logujesz się w sekcji **Zarządzanie źródłami danych** na ekranie Ustawienia zestawu danych. Jeśli masz wiele źródeł danych, musisz zalogować się do każdego z nich. Brama określa domyślny typ uwierzytelniania w zależności od źródła danych. W większości przypadków jest to uwierzytelnianie systemu Windows, jednak czasami źródło danych może wymagać innego typu uwierzytelniania. Jeśli nie masz pewności, skonsultuj się z administratorem zestawu danych.

## <a name="up-and-running"></a>Działa!
Gdy brama jest skonfigurowana i uruchomiona, możesz kliknąć pozycję ZAPLANUJ ODŚWIEŻANIE dla zestawu danych w miejscu, w którym jest widoczna strona Ustawienia zestawu danych.

![](media/personal-gateway/pg_awintsales_settings.png)

Na tej stronie są wyświetlane następujące informacje:

1. Stan odświeżania — pokazuje pomyślne odświeżanie i następny czas zaplanowanego odświeżania.
2. **Brama** — pokazuje, czy brama jest zainstalowana i w trybie online. Jeśli brama jest zainstalowana, ale nie jest w trybie online, ustawienia Zarządzaj źródłami danych i Zaplanuj odświeżanie są wyłączone.
3. **Zarządzaj źródłami danych** — pokazuje źródła danych, z którymi łączy się zestaw danych. Możesz się zalogować lub zmienić typ uwierzytelniania. Do każdego źródła danych wystarczy zalogować się tylko raz.
4. **Zaplanuj odświeżanie** — w tym miejscu możesz skonfigurować ustawienia harmonogramu odświeżania. Jeśli brama nie jest w trybie online, te ustawienia są wyłączone.
5. Powiadomienia o niepowodzeniu odświeżania — ta opcja (domyślnie zaznaczona) powoduje wysłanie wiadomości e-mail w przypadku niepowodzenia zaplanowanego odświeżania.

## <a name="updating-your-windows-account-password"></a>Aktualizowanie hasła do konta systemu Windows
Zalogowanie się do komputera za pomocą konta systemu Windows z uprawnieniami administratora po zainstalowaniu bramy powoduje, że brama jest uruchamiana jako usługa korzystająca z konta systemu Windows określonego w Kreatorze konfiguracji. Najczęściej jest to konto systemu Windows, za pomocą którego logujesz się do komputera. Gdy zmienisz hasło do konta systemu Windows, musisz także zmienić je w bramie. W przeciwnym razie usługa może nie zostać uruchomiona i odświeżanie zakończy się niepowodzeniem. Aby zmienić hasło do konta systemu Windows dla bramy, wybierz ikonę bramy osobistej na pasku zadań na pulpicie systemu Windows lub w aplikacjach.

![](media/personal-gateway/pg_programicon.png)

W tym miejscu możesz zaktualizować swoje hasło i sprawdzić stan połączenia bramy.

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>Porty
Brama komunikuje się za pomocą następujących portów wychodzących: TCP 443 (domyślnie), 5671 i 5672 oraz od 9350 do 9354.  Brama nie wymaga portów przychodzących.

| Nazwy domen | Porty wychodzące | Opis |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671–5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350–9354 |Odbiorniki usługi Service Bus Relay korzystające z protokołu TCP (wymaga portu 443 w celu uzyskania tokenu kontroli dostępu) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

Jeśli na liście dozwolonych adresów konieczne jest umieszczenie adresów IP zamiast domen, możesz pobrać listę zakresów adresów IP centrum danych platformy Microsoft Azure i skorzystać z niej. [Pobierz](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>Następne kroki
[Lokalna brama danych (tryb osobisty) — nowa wersja bramy osobistej](service-gateway-personal-mode.md)
[Konfigurowanie ustawień serwera proxy dla bram usługi Power BI](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

