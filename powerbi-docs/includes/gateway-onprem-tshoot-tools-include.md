## <a name="tools-for-troubleshooting"></a>Narzędzia do rozwiązywania problemów
<a name="logs" />

### <a name="collecting-logs-from-the-gateway-configurator"></a>Zbieranie dzienników z konfiguratora bramy
Istnieje kilka dzienników, które można zebrać dla bramy, i zawsze należy zaczynać od dzienników. Najprostszym sposobem zbierania dzienników po zainstalowaniu bramy jest użycie interfejsu użytkownika. W interfejsie użytkownika bramy **Lokalna brama danych** wybierz pozycję **Diagnostyka**, a następnie wybierz link **Eksportuj dzienniki** w dolnej części strony, jak pokazano na poniższej ilustracji.

![On-prem-data-gateway-UI-logs](./media/gateway-onprem-tshoot-tools-include/gateway-onprem-UI-logs.png)

**Dzienniki instalatora**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Dzienniki konfiguracji**

    %localappdata%\Microsoft\On-premises Data Gateway\GatewayConfigurator*.log

**Dzienniki usługi lokalnej bramy danych**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\On-premises Data Gateway\Gateway*.log

### <a name="event-logs"></a>Dzienniki zdarzeń
Dzienniki zdarzeń **usługi lokalnej bramy danych** znajdują się w obszarze **Dzienniki aplikacji i usług**.

![On-prem-data-gateway-event-logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />

### <a name="fiddler-trace"></a>Śledzenie za pomocą narzędzia Fiddler
[Fiddler](http://www.telerik.com/fiddler) to bezpłatne narzędzie firmy Telerik, które monitoruje ruch HTTP.  Dzięki niemu można sprawdzić ruch przychodzący i wychodzący w ramach usługi Power BI z maszyny klienckiej. W ten sposób można ujawnić błędy i inne istotne informacje.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)

