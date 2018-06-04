---
title: Rejestrowanie aplikacji w usłudze Azure AD
description: Przewodnik — Wypychanie danych do zestawu danych — Rejestrowanie aplikacji w usłudze Azure AD
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 660f79eab32ae7ade5cea990c6fc152bb9507297
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34285973"
---
# <a name="step-1-register-an-app-with-azure-ad"></a>Krok 1. Rejestrowanie aplikacji w usłudze Azure AD
Ten artykuł jest częścią przewodnika krok po kroku dotyczącego [wypychania danych do zestawu danych](walkthrough-push-data.md).

Pierwszym krokiem wypychania danych do zestawu danych usługi Power BI jest zarejestrowanie aplikacji w usłudze Azure AD. Ten krok należy wykonać jako pierwszy, aby uzyskać **Identyfikator klienta** identyfikujący aplikację w usłudze Azure AD. Bez **identyfikatora klienta** usługa Azure AD nie będzie mogła uwierzytelnić aplikacji.

> **UWAGA**: Przed zarejestrowaniem aplikacji w usłudze Power BI musisz [utworzyć konto w usłudze Power BI](create-an-azure-active-directory-tenant.md).
> 
> 

Poniżej przedstawiono kroki, które należy wykonać, aby zarejestrować aplikację w usłudze Azure AD.

## <a name="register-an-app-in-azure-ad"></a>Rejestrowanie aplikacji w usłudze Azure AD
1. Przejdź do witryny dev.powerbi.com/apps.
2. Kliknij przycisk **Zaloguj się przy użyciu istniejącego konta** i zaloguj się na swoim koncie usługi Power BI.
3. W polu **Nazwa aplikacji** wprowadź nazwę, na przykład „Przykładowa aplikacja do wypychania danych”.
4. W polu **Typ aplikacji** wybierz pozycję **Aplikacja natywna**.
5. Wprowadź **adres URL przekierowania**, taki jak **https://login.live.com/oauth20_desktop.srf**. W przypadku **natywnej aplikacji klienckiej** identyfikator URI przekierowania udostępnia usłudze **Azure AD** więcej informacji na temat konkretnej aplikacji, która będzie w tej usłudze uwierzytelniana. Standardowy identyfikator URI aplikacji klienta to https://login.live.com/oauth20_desktop.srf.
6. W kroku **Wybór interfejsów API na potrzeby uzyskiwania dostępu** wybierz pozycję **Odczytuj i zapisuj wszystkie zestawy danych**. Aby uzyskać informacje o wszystkich uprawnieniach aplikacji usługi Power BI, zobacz [Uprawnienia usługi Power BI](power-bi-permissions.md).
7. Kliknij przycisk **Rejestracja aplikacji** i zapisz wygenerowany **identyfikator klienta**. **Identyfikator klienta** identyfikuje aplikację w usłudze Azure AD.

Poniżej przedstawiono, jak powinna wyglądać strona **Rejestrowanie aplikacji na potrzeby usługi Power BI**:

![](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

W następnych krokach przedstawiono sposób [uzyskiwania tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md).

[Następny krok >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>Następne kroki
[Tworzenie konta w usłudze Power BI](create-an-azure-active-directory-tenant.md)  
[Uzyskiwanie tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md)  
[Przewodnik: Wypychanie danych do zestawu danych](walkthrough-push-data.md)  
[Rejestrowanie aplikacji](register-app.md)  
[Omówienie interfejsu API REST usługi Power BI](overview-of-power-bi-rest-api.md)  

Masz więcej pytań? [Zadaj pytanie społeczności usługi Power BI](http://community.powerbi.com/)

