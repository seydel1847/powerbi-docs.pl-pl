---
title: Tworzenie zestawu danych
description: Przewodnik — wypychanie danych do zestawu danych — tworzenie zestawu danych w usłudze Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 004f1b16474f738f8354585c83cd7707799e6dbb
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54288594"
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>Krok 3. Tworzenie zestawu danych w usłudze Power BI
Ten artykuł jest częścią przewodnika krok po kroku dotyczącego [wypychania danych do zestawu danych](walkthrough-push-data.md).

W **kroku 2** procedury wypychania danych do zestawu danych [Uzyskiwanie tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md) przedstawiliśmy uwierzytelnianie w usłudze **Azure AD** za pomocą tokenu. W tym kroku przy użyciu tokenu wywołamy operację [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets).

Aby wywołać zasób interfejsu REST, należy użyć adresu URL umożliwiającego zlokalizowanie zasobu i wysłać ciąg JavaScript Object Notation (JSON) opisujący zestaw danych dla zasobu usługi Power BI. Zasób interfejsu REST identyfikuje części usługi Power BI, z którą chcesz pracować. Aby można było wypchnąć dane do zestawu danych, zasób docelowy musi być **zestawem danych**. Adres URL identyfikujący zestaw danych to https://api.PowerBI.com/v1.0/myorg/datasets. W przypadku wypychania danych w obrębie grupy adres URL to https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets.

Na potrzeby uwierzytelniania operacji w interfejsie REST usługi Power BI do nagłówka żądania dodaj token uzyskany w ramach procedury [Uzyskiwanie tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md):

Wywołanie operacji [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) powoduje utworzenie nowego zestawu danych. 

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

Oto procedura tworzenia zestawu danych w usłudze Power BI.

## <a name="create-a-dataset-in-power-bi"></a>Tworzenie zestawu danych w usłudze Power BI
> [!NOTE]
> Przed rozpoczęciem upewnij się, że wykonane zostały poprzednie kroki przewodnika [wypychania danych do zestawu danych](walkthrough-push-data.md).
> 
> 

1. W projekcie aplikacji konsoli utworzonym w [kroku 2 zawierającym wskazówki dotyczące uzyskiwania tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md) dodaj w pliku Program.cs ciągi **using System.Net;** i **using System.IO;**.
2. Dodaj poniższy kod w pliku Program.cs.
3. Uruchom aplikację konsoli i zaloguj się do konta usługi Power BI. W oknie konsoli powinna pojawić się opcja **Utworzono zestaw danych**. Możesz też zalogować się do usługi Power BI, aby wyświetlić nowy zestaw danych.

**Przykład wypychania danych do zestawu danych**

Dodaj ten kod w pliku Program.cs.

* W statycznej funkcji void Main(string[] args):
  
    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Dodaj metodę CreateDataset():
  
    ```
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

W następnym kroku przedstawiono, jak [umożliwić zestawowi danych dodawanie wierszy do tabeli usługi Power BI](walkthrough-push-data-get-datasets.md).

Poniżej znajduje się [kompletna lista kodu](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kompletna lista kodu
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in Power BI
                CreateDataset();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion


            #region Create a dataset in Power BI
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }


[Następny krok >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Następne kroki
[Umożliwienie zestawowi danych dodawania wierszy do tabeli usługi Power BI](walkthrough-push-data-get-datasets.md)  
[Uzyskiwanie tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md)  
[PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)  
[PostDatasetInGroup](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdatasetingroup)  
[Wypychanie danych do pulpitu nawigacyjnego usługi Power BI](walkthrough-push-data.md)  
[Omówienie interfejsu API REST usługi Power BI](overview-of-power-bi-rest-api.md)  
[Dokumentacja interfejsu API REST usługi Power BI](https://docs.microsoft.com/rest/api/power-bi/)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

