## <a name="update-to-the-latest-version"></a>Aktualizowanie do najnowszej wersji
Gdy wersja bramy jest nieaktualna, może pojawiać się wiele problemów.  Warto dbać o to, aby mieć zawsze najnowszą wersję.  Jeśli brama nie była aktualizowana przez miesiąc lub dłużej, warto rozważyć zainstalowanie najnowszej wersji bramy i sprawdzić, czy możliwe będzie odtworzenie problemu.

## <a name="common-issues"></a>Typowe problemy
Poniżej przedstawiono kilka typowych problemów i rozwiązań, które pomogły wielu klientom w środowiskach, gdzie dostęp do Internetu jest ograniczony.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>Uwierzytelnianie na serwerze proxy
Serwer proxy może wymagać uwierzytelniania konta użytkownika domeny. Domyślnie brama używa identyfikatora SID usługi w przypadku użytkowników logowania usługi systemu Windows. Zmiana użytkownika logowania na użytkownika domeny może pomóc w tym przypadku. Aby uzyskać więcej informacji, zobacz [Zmiana konta usługi bramy na użytkownika domeny](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>Serwer proxy zezwala na ruch tylko na portach 80 i 443
Niektóre serwery proxy ograniczają ruch tylko do portów 80 i 443. Domyślnie komunikacja z usługą Azure Service Bus odbywa się przy użyciu portów innych niż 443.

Istnieje możliwość wymuszenia na bramie komunikacji z usługą Azure Service Bus za pomocą protokołu HTTPS zamiast bezpośredniego połączenia TCP. Należy zmodyfikować plik *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*. Zmień wartość z `AutoDetect` na `Https`. Domyślna lokalizacja pliku to *C:\Program Files\On-premises data gateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Instalacja
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Błąd: Nie można dodać użytkownika do grupy.  (-2147463168   PBIEgwService   Użytkownicy dzienników wydajności   )
Ten błąd może występować w przypadku próby zainstalowania bramy na kontrolerze domeny. Wdrażanie na kontrolerze domeny nie jest obsługiwane. Należy wdrożyć bramę na maszynie, która nie jest kontrolerem domeny.

### <a name="installation-fails"></a>Instalacja kończy się niepowodzeniem
Jeśli oprogramowanie antywirusowe na maszynie z instalacją jest nieaktualne, mogą wystąpić błędy instalacji. Można zaktualizować instalację oprogramowania antywirusowego lub wyłączyć oprogramowanie antywirusowe tylko do czasu ukończenia instalacji bramy, a następnie ponownie je włączyć.

