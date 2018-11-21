## <a name="limitations"></a>Ograniczenia

Poniżej znajduje się lista bieżących ograniczeń dotyczących zabezpieczeń na poziomie wiersza w modelach chmury.

* Jeśli w usłudze Power BI wcześniej zdefiniowano role i reguły, musisz utworzyć je ponownie w programie Power BI Desktop.

* Zabezpieczenia na poziomie wiersza można zdefiniować tylko dla zestawów danych utworzonych za pomocą programu Power BI Desktop. Jeśli chcesz włączyć zabezpieczenia na poziomie wiersza dla zestawów danych utworzonych za pomocą programu Excel, najpierw musisz przekonwertować pliki na pliki programu Power BI Desktop (PBIX). [Dowiedz się więcej](../desktop-import-excel-workbooks.md)

* Obsługiwane są tylko połączenia ETL i zapytań bezpośrednich. Połączenia na żywo z usługami Analysis Services są obsługiwane w modelu lokalnym.

* Zabezpieczenia na poziomie wiersza w tej chwili nie obsługują funkcji Pytania i odpowiedzi ani Cortany. Jeśli we wszystkich modelach skonfigurowano zabezpieczenia na poziomie wiersza, pole wprowadzania pytań i odpowiedzi dla pulpitów nawigacyjnych nie będzie widoczne. Ta funkcja jest w planach, ale data jej wprowadzenia nie jest znana.

## <a name="known-issues"></a>Znane problemy

Istnieje znany problem polegający na tym, że próba publikacji z poziomu programu Power BI Desktop raportu, który został już wcześniej opublikowany, powoduje wyświetlenie komunikatu o błędzie. Scenariusz może wyglądać jak poniższy.

1. Anna ma zestaw danych, który został opublikowany w usłudze Power BI i w którym skonfigurowano zabezpieczenia na poziomie wiersza.

1. Anna aktualizuje raport w programie Power BI Desktop i publikuje go ponownie.

1. Anna otrzymuje komunikat o błędzie.

**Obejście problemu:** dopóki ten problem nie zostanie rozwiązany, publikuj ponownie pliki programu Power BI Desktop z poziomu usługi Power BI. Możesz to zrobić, wybierając pozycję **Pobierz dane** > **Pliki**.
