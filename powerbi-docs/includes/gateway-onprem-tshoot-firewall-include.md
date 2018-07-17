## <a name="firewall-or-proxy"></a>Zapora czy serwer proxy
Więcej informacji na temat podawania danych dotyczących serwera proxy dla bramy zawiera artykuł [Konfigurowanie ustawień serwera proxy dla bram Power BI Gateway](../service-gateway-proxy.md).

Możesz sprawdzić, czy zapora lub serwer proxy blokuje połączenia, uruchamiając polecenie [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) z poziomu wiersza polecenia programu PowerShell. To polecenie przetestuje połączenie z usługą Azure Service Bus. Służy ono tylko do testowania połączenia sieciowego i nie ma nic wspólnego z usługą serwera w chmurze ani z bramą. Pomaga ono ustalić, czy komputer może łączyć się z Internetem.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Polecenie Test-NetConnection jest dostępne tylko w systemie Windows Server 2012 R2 i nowszych wersjach. Istnieje również dostępne w systemie Windows 8.1 i nowszych wersjach. We wcześniejszych wersjach tego systemu operacyjnego można używać programu Telnet w celu testowania połączeń przez porty.
> 
> 

Wynik powinien wyglądać mniej więcej tak, jak poniżej. Różnica będzie widoczna w elemencie TcpTestSucceeded. Jeśli **TcpTestSucceeded** nie ma wartości *true*, możliwe, że połączenie jest blokowane przez zaporę.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Jeśli chcesz sprawdzić to dokładnie, zastąp wartości **ComputerName** i **Port** wartościami podanymi dla [portów](../service-gateway-onprem.md#ports).

Zapora może także blokować połączenia, które usługa Azure Service Bus nawiązuje z centrami danych platformy Azure. Jeśli tak jest, musisz dodać do listy dozwolonych adresów IP adresy IP tych centrów danych w Twoim regionie, co spowoduje odblokowanie ich adresów IP. Listę adresów IP platformy Azure można uzyskać [tutaj](https://www.microsoft.com/download/details.aspx?id=41653).

