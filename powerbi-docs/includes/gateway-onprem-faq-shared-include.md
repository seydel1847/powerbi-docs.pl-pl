## <a name="general"></a>Ogólne
**Pytanie:** Jaka jest nazwa rzeczywistej usługi systemu Windows?  
**Odpowiedź:** Brama ma w usługach nazwę „lokalna brama danych”

**Pytanie:** Jakie są wymagania dotyczące bramy?  
**Odpowiedź:** Zajrzyj do sekcji wymagań w głównym [artykule na temat bramy](../service-gateway-onprem.md).

**Pytanie:** Jakie źródła danych są obsługiwane z użyciem bramy?  
**Odpowiedź:** Zobacz tabelę źródeł danych w głównym [artykule na temat bramy](../service-gateway-onprem.md).

**Pytanie:** Czy brama jest potrzebna dla źródeł danych w chmurze, takich jak Azure SQL Database?  
**Odpowiedź:** Nie. Usługa będzie mogła łączyć się ze źródłem danych bez bramy.

**Pytanie:** Czy istnieją połączenia przychodzące do bramy z chmury?  
**Odpowiedź:** Nie. Brama używa połączeń wychodzących do usługi Azure Service Bus.

**Pytanie:** Co zrobić, jeśli zablokuję połączenia wychodzące? Co muszę otworzyć?  
**Odpowiedź:** Sprawdź [listę portów](../service-gateway-onprem.md#ports) i hosty, których używa brama.

**Pytanie:** Czy brama musi być zainstalowana na tym samym komputerze co źródło danych?  
**Odpowiedź:** Nie. Brama będzie łączyć się ze źródłem danych, korzystając z podanych informacji dotyczących połączenia. W tym sensie bramę należy traktować jako aplikację kliencką. Brama musi mieć po prostu możliwość łączenia się z serwerem o podanej nazwie.

**Pytanie:** Jakie jest opóźnienie przed wykonaniem zapytań do źródła danych z bramy? Jaka jest najlepsza architektura?  
**Odpowiedź:** Zaleca się, aby brama była jak najbliżej źródła danych w celu wyeliminowania opóźnień sieciowych. Jeśli bramę można zainstalować w rzeczywistym źródle danych, zminimalizuje to opóźnienia. Weź także pod uwagę centra danych. Na przykład jeśli usługa korzysta z centrum danych w zachodnich stanach USA, a Twój serwer SQL Server jest hostowany na maszynie wirtualnej platformy Azure, wówczas ta maszyna wirtualna platformy Azure powinna również znajdować się zachodnich stanach USA. Dzięki temu opóźnienie zostanie zminimalizowane i unikniesz opłat za ruch wychodzący na maszynie wirtualnej platformy Azure.

**Pytanie:** Czy istnieją jakiekolwiek wymagania dotyczące przepustowości sieci?  
**Odpowiedź:** Zalecane jest korzystanie z połączenia sieciowego o dobrej przepływności. Każde środowisko jest inne, a znaczenie ma też ilość wysyłanych danych. Usługa ExpressRoute może pomóc w zapewnieniu poziomu przepływności między lokalnymi centrami danych a centrami danych platformy Azure.

W celu zmierzenia przepływności można użyć aplikacji [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) innej firmy.

**Pytanie:** Czy usługa bramy w systemie Windows może być uruchamiana przy użyciu konta usługi Azure Active Directory?  
**Odpowiedź:** Nie. Usługa systemu Windows musi mieć prawidłowe konto systemu Windows. Domyślnie ta usługa będzie uruchamiana z identyfikatorem SID usługi *NT SERVICE\PBIEgwService*.

**Pytanie:** W jaki sposób wyniki są odsyłane do chmury?  
**Odpowiedź:** Odbywa się to w oparciu o usługę Azure Service Bus. Więcej informacji znajduje się w temacie [Jak to działa](../service-gateway-onprem.md#how-the-gateway-works).

**Pytanie:** Gdzie przechowywane są moje poświadczenia?  
**Odpowiedź:** Poświadczenia wprowadzone dla źródła danych są przechowywane w postaci zaszyfrowanej w usłudze bramy w chmurze. Poświadczenia są odszyfrowywane w lokalnej bramie.

**Pytanie:** Czy mogę umieścić bramę w sieci obwodowej (określanej także jako DMZ, strefa zdemilitaryzowana i podsieć ekranowana)?  
**Odpowiedź:** Brama wymaga połączenia ze źródłem danych. Jeśli źródło danych nie jest dostępne w sieci obwodowej, możliwe jest, że brama nie będzie mogła się z nim łączyć. Na przykład serwer SQL Server może nie być w sieci obwodowej. Nie można wtedy łączyć się z serwerem SQL Server z sieci obwodowej. Jeśli brama zostanie umieszczona w sieci obwodowej, nie będzie mogła uzyskiwać dostępu do serwera SQL Server.

**Pytanie:** Czy istnieje możliwość wymuszenia na bramie korzystanie z ruchu sieciowego HTTPS z usługą Azure Service Bus zamiast TCP?  
**Odpowiedź:** Tak. Chociaż spowoduje to znaczne obniżenie wydajności. Konieczne będzie zmodyfikowanie pliku *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Wartość `AutoDetect` trzeba będzie zastąpić wartością `Https`. Domyślna lokalizacja tego pliku to *C:\Program Files\On-premises data gateway*.

**Pytanie:** Czy trzeba dodawać do listy dozwolonych adresów IP listę adresów IP centrów danych platformy Azure? Skąd wziąć taką listę?  
**Odpowiedź:** Jeśli blokujesz wychodzący ruch IP, dodanie do listy dozwolonych adresów IP listy adresów IP centrów danych platformy Azure może być konieczne. Obecnie brama komunikuje się z usługą Azure Service Bus przy użyciu adresu IP wraz z w pełni kwalifikowaną nazwą domeny. Lista adresów IP centrów danych platformy Azure jest aktualizowana co tydzień. Możesz pobrać [listę adresów IP centrów danych platformy Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653).

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Wysoka dostępność/odzyskiwanie po awarii
**Pytanie:** Czy istnieją plany realizacji scenariuszy wysokiej dostępności z bramą?  
**Odpowiedź:** Tak, jest to obszar, nad którym zespół usługi Power BI aktywnie pracuje. Obserwuj [blog usługi Power BI](https://powerbi.microsoft.com/blog/), aby być na bieżąco z wiadomościami na temat tej funkcji.

**Pytanie:** Jakie są dostępne opcje odzyskiwania po awarii?  
**Odpowiedź:** W celu przywrócenia lub przeniesienia bramy można użyć klucza odzyskiwania. Klucz odzyskiwania jest podawany podczas instalowania bramy.

**Pytanie:** Jaka jest korzyść z posiadania klucza odzyskiwania?  
**Odpowiedź:** Umożliwia on migrację lub odzyskiwanie ustawień bramy. Jest również używany do odzyskiwania po awarii.

## <a name="troubleshooting"></a>Rozwiązywanie problemów
**Pytanie:** Gdzie są zapisywane dzienniki bramy?  
**Odpowiedź:** Zajrzyj do sekcji narzędzi w [artykule na temat rozwiązywania problemów](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting).

**Pytanie:** Jak sprawdzić zapytania wysyłane do lokalnego źródła danych?  
**Odpowiedź:** Możesz włączyć śledzenie zapytań.  Obejmuje to śledzenie wysyłanych zapytań. Pamiętaj, że po zakończeniu rozwiązywania problemów należy przywrócić pierwotną wartość tego ustawienia. Pozostawienie włączonego śledzenia zapytań spowoduje, że dzienniki będą większe.

Można także zapoznać się z narzędziami, którymi posługuje się źródło danych w celu śledzenia zapytań. Na przykład dla serwera SQL Server i usług Analysis Services można użyć narzędzia Extended Events lub SQL Profiler.

