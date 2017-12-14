## <a name="using-the-username-or-userprincipalname-dax-function"></a>Używanie funkcji username() lub userprincipalname() języka DAX
W ramach zestawu danych można użyć funkcji *username()* lub *userprincipalname()* języka DAX. Można ich używać w wyrażeniach w programie Power BI Desktop. Po opublikowaniu modelu będzie on używany w usłudze Power BI.

W programie Power BI Desktop funkcja *username()* zwraca użytkownika w formacie *DOMENA\Użytkownik*, a funkcja *userprincipalname()* zwraca użytkownika w formacie *user@contoso.com*.

W usłudze Power BI funkcje *username()* i *userprincipalname()* zwracają główną nazwę użytkownika (UPN, User Principal Name). Wygląda ona podobnie do adresu e-mail.

