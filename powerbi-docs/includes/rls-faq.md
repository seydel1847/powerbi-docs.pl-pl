## <a name="faq"></a>Często zadawane pytania
**Pytanie:** Co w sytuacji, gdy role/reguły dla zestawu danych zostały utworzone wcześniej w usłudze Power BI? Czy nadal będą działały, jeśli nic nie zrobię?  
**Odpowiedź:** Nie. Wizualizacje nie będą poprawnie renderowane. Musisz utworzyć ponownie role/reguły w programie Power BI Desktop, a następnie opublikować je w usłudze Power BI.

**Pytanie:** Czy mogę utworzyć te role dla źródeł danych usług Analysis Services?  
**Odpowiedź:** Możesz, jeśli dane zostały zaimportowane do programu Power BI Desktop. Jeśli używasz połączenia na żywo, nie możesz skonfigurować zabezpieczeń na poziomie wiersza w usłudze Power BI. Są one definiowane w modelu usług Analysis Services lokalnie.

**Pytanie:** Czy używając zabezpieczeń na poziomie wiersza, mogę ograniczyć dostępność kolumn lub miar moim użytkownikom?  
**Odpowiedź:** Nie. Jeśli użytkownik ma dostęp do określonego wiersza danych, może zobaczyć wszystkie kolumny danych dla tego wiersza.

**Pytanie:** Czy zabezpieczenia na poziomie wiersza pozwalają na ukrywanie szczegółowych danych, zapewniając jednocześnie dostęp do podsumowania danych w wizualizacjach?  
**Odpowiedź:** Nie. Zabezpieczasz poszczególne wiersze danych, ale użytkownicy zawsze widzą zarówno szczegóły, jak i podsumowanie danych.

