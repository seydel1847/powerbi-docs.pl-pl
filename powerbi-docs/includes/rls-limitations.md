## <a name="limitations"></a>Ograniczenia
Oto lista bieżących ograniczeń dotyczących zabezpieczeń na poziomie wiersza w modelach chmury.

* Jeśli role/reguły były zdefiniowane wcześniej w usłudze Power BI, musisz utworzyć je ponownie w programie Power BI Desktop.
* Zabezpieczenia na poziomie wiersza można zdefiniować tylko na zestawach danych utworzonych za pomocą klienta programu Power BI Desktop. Jeśli chcesz włączyć zabezpieczenia na poziomie wiersza dla zestawów danych utworzonych za pomocą programu Excel, najpierw musisz przekonwertować pliki na pliki PBIX. [Dowiedz się więcej](../desktop-import-excel-workbooks.md)
* Obsługiwane są tylko połączenia ETL i zapytań bezpośrednich. Połączenia na żywo z usługami Analysis Services są obsługiwane w modelu lokalnym.
* Zabezpieczenia na poziomie wiersza w tej chwili nie obsługują pytań i odpowiedzi oraz Cortany. Jeśli we wszystkich modelach skonfigurowano zabezpieczenia na poziomie wiersza, pole wprowadzania pytań i odpowiedzi dla pulpitów nawigacyjnych nie będzie widoczne. Ta funkcja jest w planach, ale data jej wprowadzenia nie jest znana.
* Udostępnianie zewnętrzne nie jest obecnie obsługiwane w przypadku zestawów danych, które korzystają z zabezpieczeń na poziomie wiersza.
* W przypadku dowolnego modelu maksymalna liczba podmiotów zabezpieczeń usługi Azure AD (tj. poszczególnych użytkowników lub grup zabezpieczeń), które można przypisać do ról zabezpieczeń, wynosi 1000. Aby przypisać wielu użytkowników do ról, przypisuj grupy zabezpieczeń, zamiast poszczególnych użytkowników.

## <a name="known-issues"></a>Znane problemy
Istnieje znany problem polegający na tym, że próba publikacji z programu Power BI Desktop, gdy raport został już wcześniej opublikowany, powoduje wyświetlenie komunikatu o błędzie. Scenariusz może wyglądać jak poniższy.

1. Anna ma zestaw danych, który został opublikowany w usłudze Power BI i w którym skonfigurowano zabezpieczenia na poziomie wiersza.
2. Anna aktualizuje raport w programie Power BI Desktop i publikuje go ponownie.
3. Wyświetlany jest komunikat o błędzie.

**Obejście problemu:** Dopóki ten problem nie zostanie rozwiązany, opublikuj ponownie plik programu Power BI Desktop z usługi Power BI. Możesz to zrobić, wybierając pozycję **Pobierz dane** > **Pliki**. 

