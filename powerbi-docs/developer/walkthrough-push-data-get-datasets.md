---
title: Pobieranie zestawu danych w celu dodania wierszy
description: Wskazówki dotyczące wypychania danych — umożliwienie zestawowi danych dodawania wierszy do tabeli usługi Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: c550b911eef43ade98b3bc771e3f13929b805e11
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287629"
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>Krok 4. Umożliwienie zestawowi danych dodawania wierszy do tabeli usługi Power BI
Ten artykuł jest częścią przewodnika krok po kroku dotyczącego [wypychania danych do zestawu danych](walkthrough-push-data.md).

W **kroku 3.** procedury wypychania danych do zestawu danych, [Tworzenie zestawu danych w usłudze Power BI](walkthrough-push-data-create-dataset.md), nastąpiło wywołanie operacji [Utwórz zestaw danych](https://msdn.microsoft.com/library/mt203562.aspx) w celu utworzenia zestawu danych w usłudze Power BI. W tym kroku uzyskasz identyfikator zestawu danych za pomocą operacji [Pobierz zestawy danych](https://msdn.microsoft.com/library/mt203567.aspx) i pakietu Newtonsoft.Json. Identyfikator zestawu danych umożliwi dodanie wierszy do zestawu danych w kroku 4. 

Wypychanie danych do zestawu danych usługi Power BI wymaga odwoływania się do tabeli w zestawie danych. Aby odwołać się do tabeli w zestawie danych, należy najpierw uzyskać **identyfikator zestawu danych**. **Identyfikator zestawu danych** można uzyskać przy użyciu operacji [Pobierz zestaw danych](https://msdn.microsoft.com/library/mt203567.aspx). Operacja **Pobierz zestaw danych** zwraca ciąg JSON zawierający listę wszystkich zestawów danych w usłudze Power BI. Jest to zalecany sposób deserializacji ciągu JSON za pomocą pakietu [Newtonsoft.Json](http://www.newtonsoft.com/json).

Poniżej przedstawiono sposób pobierania zestawu danych.

## <a name="get-a-power-bi-dataset"></a>Pobieranie zestawu danych usługi Power BI
> **UWAGA**: Przed rozpoczęciem upewnij się, że zostały wykonane poprzednie kroki przewodnika [wypychania danych do zestawu danych](walkthrough-push-data.md).
> 
> 

1. W projekcie aplikacji konsoli utworzonym w kroku 2 zawierającym wskazówki dotyczące wypychania danych, [Uzyskiwanie tokenu dostępu do uwierzytelniania](walkthrough-push-data-get-token.md), zainstaluj pakiet NuGet Newtonsoft.Json. Poniżej przedstawiono sposób instalacji pakietu:
   
     a. W programie Visual Studio 2015 wybierz pozycję **Narzędzia** > **Menedżer pakietów NuGet** > **Konsola menedżera pakietów**.
   
     b. W oknie **Konsola menedżera pakietów** wprowadź ciąg Install-Package Newtonsoft.Json.
2. Po zainstalowaniu pakietu dodaj ciąg **using Newtonsoft.Json;** do pliku Program.cs.
3. Dodaj poniższy kod w pliku Program.cs, aby uzyskać **identyfikator zestawu danych**.
4. Uruchom aplikację konsoli i zaloguj się do konta usługi Power BI. W oknie konsoli powinna zostać wyświetlona pozycja **Identyfikator zestawu danych**, a za nią identyfikator.

**Przykład pobierania zestawu danych**

Dodaj ten kod w pliku Program.cs.

* W statycznej funkcji void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* Dodaj metodę GetDataset():
  
  ```
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

W następnym kroku przedstawiono, jak [dodać wiersze do tabeli usługi Power BI](walkthrough-push-data-add-rows.md).

Poniżej znajduje się [kompletna lista kodu](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Kompletna lista kodu
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;
    using Newtonsoft.Json;

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

                //Get a dataset to add rows into a Power BI table
                string datasetId = GetDataset();

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

            #region Get a dataset to add rows into a Power BI table
            private static string GetDataset()
            {
                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "GET";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                string datasetId = string.Empty;
                //Get HttpWebResponse from GET request
                using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
                {
                    //Get StreamReader that holds the response stream
                    using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                    {
                        string responseContent = reader.ReadToEnd();

                        //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                        //and add using Newtonsoft.Json
                        var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                        //Get the first id
                        datasetId = results["value"][0]["id"];

                        Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                        Console.ReadLine();

                        return datasetId;
                    }
                }
            }
            #endregion
        }
    }

[Następny krok >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>Następne kroki
[Dodawanie wierszy do tabeli usługi Power BI](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[Pobieranie zestawów danych](https://msdn.microsoft.com/library/mt203567.aspx)  
[Wypychanie danych do usługi Power BI](walkthrough-push-data.md)  
[Omówienie interfejsu API REST usługi Power BI](overview-of-power-bi-rest-api.md)  
[Dokumentacja interfejsu API REST usługi Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  

Masz więcej pytań? [Odwiedź społeczność usługi Power BI](http://community.powerbi.com/)

