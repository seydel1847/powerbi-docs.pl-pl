---
title: Lokalna brama danych — szczegóły
description: Ten artykuł zawiera szczegółowe omówienie lokalnej bramy danych. Analizuje sposób, w jaki usługa Azure Active Directory działa z lokalną usługą Active Directory podczas pracy z usługą Analysis Services
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 8b0121dbfe633eca9c438dfd272d3aeb56fd59a4
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298578"
---
# <a name="on-premises-data-gateway-in-depth"></a>Lokalna brama danych — szczegóły
Użytkownicy w organizacji mogą uzyskiwać dostęp do danych lokalnych (do których już mają autoryzację dostępu), ale zanim będą mogli połączyć się ze źródłem danych lokalnych, musi zostać zainstalowana i skonfigurowana lokalna brama danych. Brama ułatwia szybką i bezpieczną komunikację wewnętrzną między użytkownikiem w chmurze a lokalnym źródłem danych, a następnie z powrotem do chmury.

Instalowanie i konfigurowanie bramy jest zazwyczaj wykonywane przez administratora. Te czynności mogą wymagać specjalnej wiedzy o serwerach lokalnych, a w niektórych przypadkach mogą wymagać uprawnień administratora serwera.

Ten artykuł nie zawiera wskazówek krok po kroku dotyczących sposobu instalowania i konfigurowania bramy. Aby je znaleźć, zapoznaj się z artykułem [Lokalna brama danych](service-gateway-onprem.md). Celem niniejszego artykułu jest dostarczenie szczegółowego opisu sposobu działania bramy. Przedstawiono tutaj również niektóre informacje na temat nazw użytkowników oraz zabezpieczeń w usłudze Azure Active Directory i usługach Analysis Services, a także sposobu, w jaki usługa w chmurze używa adresu e-mail logowania użytkownika, bramy i usługi Active Directory w celu bezpiecznego łączenia się z lokalnymi danymi i wykonywania zapytań na tych danych.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>Konto logowania
Użytkownicy będą logować się za pomocą konta służbowego. Jest to Twoje konto organizacji. Jeśli zarejestrujesz się, aby skorzystać z oferty Office 365, ale nie podasz rzeczywistego służbowego adresu e-mail, może to być adres podobny do nancy@contoso.onmicrosoft.com. Twoje konto w usłudze w chmurze jest przechowywane w ramach dzierżawy w usłudze Azure Active Directory (AAD). W większości przypadków główna nazwa użytkownika konta usługi AAD jest zgodna z adresem e-mail użytkownika.

## <a name="authentication-to-on-premises-data-sources"></a>Uwierzytelnianie w lokalnych źródłach danych
Przechowywane poświadczenia będą używane do nawiązywania połączenia z lokalnymi źródłami danych z bramy, z wyjątkiem usług Analysis Services. Brama używa przechowywanych poświadczeń do nawiązania połączenia niezależnie od użytkownika.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Uwierzytelnianie na żywo w źródle danych usług Analysis Services
Za każdym razem, gdy użytkownik wchodzi w interakcję z usługami Analysis Services, obowiązująca nazwa użytkownika jest przekazywany do bramy, a następnie do lokalnego serwera usług Analysis Services. Główna nazwa użytkownika (UPN), zwykle adres e-mail używany do logowania w chmurze, będzie przekazywana do usług Analysis Services jako obowiązująca nazwa użytkownika. Nazwa UPN jest przekazywana we właściwości EffectiveUserName połączenia. Ten adres e-mail powinien być zgodny ze zdefiniowaną nazwa UPN w domenie lokalnej usługi Active Directory. Nazwa UPN jest właściwością konta usługi Active Directory. To konto systemu Windows musi być obecne w roli usługi Analysis Services, aby mieć dostęp do serwera. Logowanie nie powiedzie się, jeśli w usłudze Active Directory nie zostanie znalezione dopasowanie.

Usługi Analysis Services mogą również oferować filtrowanie oparte na tym koncie. Filtrowanie może wystąpić z użyciem zabezpieczeń opartych na rolach lub zabezpieczeń na poziomie wiersza.

## <a name="role-based-security"></a>Zabezpieczenia oparte na rolach
Modele oferują zabezpieczenia oparte na rolach użytkownika. Role są definiowane dla określonego projektu modelu podczas tworzenia w programie SQL Server Data Tools — Business Intelligence (SSDT BI) lub po wdrożeniu modelu, przy użyciu programu SQL Server Management Studio (SSMS). Role zawierają członków według nazwy użytkownika systemu Windows lub grupy systemu Windows. Role definiują uprawnienia użytkownika do wykonywania zapytań lub akcji na modelu. Większość użytkowników będzie należeć do roli z uprawnieniami do odczytu. Pozostałe role są przeznaczone dla administratorów z uprawnieniami do przetwarzania elementów, zarządzania funkcjami bazy danych oraz zarządzania innymi rolami.

## <a name="row-level-security"></a>Zabezpieczenia na poziomie wiersza
Zabezpieczenia na poziomie wiersza są specyficzne dla zabezpieczeń na poziomie wiersza usług Analysis Services. Modele mogą zapewnić dynamiczne zabezpieczenia na poziomie wiersza. Zabezpieczenia dynamiczne, w odróżnieniu od posiadania co najmniej jednej roli, do której należą użytkownicy, nie są wymagane dla żadnego modelu tabelarycznego. Na wysokim poziomie zabezpieczenia dynamiczne definiują dostęp użytkownika do odczytu danych w określonym wierszu określonej tabeli. Podobnie jak role, zabezpieczenia dynamiczne na poziomie wiersza polegają na nazwie użytkownika systemu Windows.

Uprawnienia użytkownika do wyświetlania danych modelu i wykonywania względem nich zapytań są określane najpierw przez role, których członkiem jest konto użytkownika systemu Windows tego użytkownika, a następnie przez dynamiczne zabezpieczenia na poziomie wiersza, jeśli je skonfigurowano.

Implementowanie zabezpieczeń opartych na rolach i dynamicznych zabezpieczeń na poziomie wiersza w modelach wykracza poza zakres tego artykułu.  Aby dowiedzieć się więcej, zobacz [Role (SSAS — tabelaryczne)](https://msdn.microsoft.com/library/hh213165.aspx) i [Role zabezpieczeń (Analysis Services — dane wielowymiarowe)](https://msdn.microsoft.com/library/ms174840.aspx) w witrynie MSDN. Aby uzyskać najbardziej szczegółowy opis zabezpieczeń modelu tabelarycznego, pobierz i przeczytaj [oficjalny dokument na temat zabezpieczania tabelarycznego semantycznego modelu analizy biznesowej](https://msdn.microsoft.com/library/jj127437.aspx).

## <a name="what-about-azure-active-directory"></a>Co z usługą Azure Active Directory?
Usługi w chmurze firmy Microsoft używają [usługi Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) do obsługi uwierzytelniania użytkowników. Usługa Azure Active Directory jest dzierżawą, która zawiera nazwy użytkowników i grupy zabezpieczeń. Zazwyczaj adres e-mail, przy użyciu którego loguje się użytkownik, jest taki sam jak nazwa UPN konta.

Jaka jest rola mojej lokalnej usługi Active Directory?

Aby usługi Analysis Services mogły określić, czy użytkownik nawiązujący z nimi połączenie należy do roli z uprawnieniami do odczytu danych, serwer musi przekonwertować obowiązującą nazwę użytkownika przekazaną z usługi AAD do bramy i na serwer usług Analysis Services. Serwer usług Analysis Services przekazuje obowiązującą nazwę użytkownika do kontrolera domeny usługi Active Directory systemu Windows. Następnie kontroler domeny usługi Active Directory weryfikuje obowiązującą nazwę użytkownika na koncie lokalnym, sprawdzając, czy jest to prawidłowa nazwa UPN, i zwraca nazwę użytkownika systemu Windows tego użytkownika z powrotem do serwera usług Analysis Services.

Właściwość EffectiveUserName nie może być używana na serwerze usług Analysis Services, który nie jest przyłączony do domeny. Serwer usług Analysis Services musi należeć do domeny, aby uniknąć błędów logowania.

## <a name="how-do-i-tell-what-my-upn-is"></a>Jak mogę sprawdzić swoją nazwę UPN?
Możesz nie znać swojej nazwy UPN i nie być administratorem domeny. Aby sprawdzić nazwę UPN dla swojego konta, możesz użyć następującego polecenia z poziomu swojej stacji roboczej.

    whoami /upn

Wynik będzie wyglądał podobnie do adresu e-mail, ale jest to nazwa UPN przechowywana na koncie domeny lokalnej. Jeśli używasz źródła danych usługi Analysis Services dla połączeń na żywo, musi on być zgodny z tym, który został przekazany do elementu EffectiveUserName z bramy.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Mapowanie nazw użytkowników dla źródeł danych usługi Analysis Services
Usługa Power BI umożliwia mapowanie nazw użytkowników dla źródeł danych usługi Analysis Services. Możesz skonfigurować reguły, aby zamapować nazwę użytkownika zalogowanego w usłudze Power BI na nazwę przekazywaną dla elementu EffectiveUserName w ramach połączenia usługi Analysis Services. Funkcja mapowania nazwy użytkownika jest świetnym sposobem obejścia problemu, gdy nazwa użytkownika w usłudze AAD nie jest zgodna z nazwą UPN w lokalnej usłudze Active Directory. Na przykład adres e-mail nancy@contoso.onmicrsoft.com możesz zamapować na nancy@contoso.com i ta wartość zostanie przekazana do bramy. Możesz dowiedzieć się więcej na temat sposobu [mapowania nazw użytkowników](service-gateway-enterprise-manage-ssas.md#map-user-names).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Synchronizowanie lokalnej usługi Active Directory z usługą Azure Active Directory
Jeśli zamierzasz używać połączenia na żywo usługi Analysis Services, konta lokalnej usługi Active Directory muszą być zgodne z usługą Azure Active Directory. Nazwa UPN na kontach musi być zgodna.

Usługi w chmurze wiedzą tylko o kontach w usłudze Azure Active Directory. Nie ma znaczenia, czy konto zostało dodane w lokalnej usłudze Active Directory — jeśli nie istnieje ono w usłudze AAD, nie można go używać. Istnieją różne sposoby uzgodnienia lokalnych kont usługi Active Directory z usługą Azure Active Directory.

1. Można ręcznie dodać konta do usługi Azure Active Directory.
   
   Można utworzyć konto w portalu Azure lub w portalu administratora usługi Office 365, a nazwa konta będzie zgodna z nazwą UPN lokalnego konta usługi Active Directory.
2. Można użyć narzędzia [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), aby zsynchronizować konta lokalne z dzierżawą usługi Azure Active Directory.
   
   Narzędzie Azure AD Connect oferuje opcje synchronizacji katalogów i konfigurowania uwierzytelniania, w tym synchronizacji skrótów haseł, uwierzytelniania przekazywanego i federacji. Jeśli nie jesteś administratorem dzierżawy ani lokalnym administratorem domeny, skontaktuj się z administratorem IT w celu skonfigurowania tej funkcji.

Korzystanie z programu Azure AD Connect zapewnia zgodność nazwy UPN w usłudze AAD i lokalnej usłudze Active Directory.

> [!NOTE]
> Synchronizowanie kont za pomocą narzędzia Azure AD Connect spowoduje utworzenie nowych kont w dzierżawie usługi AAD.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>Teraz miejsce na bramę
Brama działa jako mostek między chmurą a serwerem lokalnym. Transfer danych między chmurą a bramą jest zabezpieczony za pomocą usługi [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/). Usługa Service Bus tworzy bezpieczny kanał między chmurą a serwerem lokalnym za pośrednictwem połączenia wychodzącego w bramie.  Nie trzeba otwierać żadnych połączeń przychodzących w lokalnej zaporze.

W przypadku źródła danych usługi Analysis Services konieczne będzie zainstalowanie bramy na komputerze przyłączonym do tego samego lasu/domeny co serwer usługi Analysis Services.

Im bliżej serwera znajduje się brama, tym szybsze będzie połączenie. Jeśli możesz zainstalować bramę na tym samym serwerze, na którym znajduje się źródło danych, jest to najlepsze rozwiązanie, aby jest uniknąć opóźnienia sieciowego między bramą a serwerem.

## <a name="what-to-do-next"></a>Co zrobić dalej?
Po zainstalowaniu bramy należy utworzyć źródła danych dla tej bramy. Źródła danych można dodać z poziomu ekranu **Zarządzanie bramami**. Aby uzyskać więcej informacji, zobacz artykuły dotyczące zarządzania źródłami danych.

[Zarządzanie źródłami danych — usługi Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Zarządzanie źródłem danych — SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Zarządzanie źródłami danych — SQL Server](service-gateway-enterprise-manage-sql.md)  
[Zarządzanie źródłami danych — Oracle](service-gateway-onprem-manage-oracle.md)  
[Zarządzanie źródłami danych — importowanie/zaplanowane odświeżanie](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>Gdzie mogą wystąpić problemy
Czasami instalowanie bramy kończy się niepowodzeniem. Ewentualnie wydaje się, że brama została pomyślnie zainstalowana, ale usługa nadal nie może z nią pracować. W wielu przypadkach przyczyną jest coś prostego, na przykład hasło dla poświadczeń, których brama używa do logowania się do źródła danych.

W innych przypadkach mogą występować problemy związane z typem adresu e-mail, przy użyciu którego użytkownicy się logują, lub niezdolnością usługi Analysis Service do rozpoznania obowiązującej nazwy użytkownika. W przypadku wielu domen z relacjami zaufania między nimi, jeśli brama znajduje się w jednej z nich, podczas gdy usługa Analysis Services w innej, może to czasami powodować pewne problemy.

Zamiast przechodzić w tym miejscu do rozwiązywania problemów z bramą, szereg kroków rozwiązywania problemów zamieściliśmy w innym artykule: [Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md). Mamy nadzieję, że napotkasz żadnych problemów. Jeśli jednak się pojawią, zrozumienie, jak to wszystko działa, oraz artykuł dotyczący rozwiązywania problemów powinny być pomocne.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>Następne kroki
[Rozwiązywanie problemów z lokalną bramą danych](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

