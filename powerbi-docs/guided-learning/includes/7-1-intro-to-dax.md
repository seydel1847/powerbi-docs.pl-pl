Witamy w dotyczącej usługi Power BI sekcji **Nauka z przewodnikiem**, która została zaprojektowana w celu wprowadzenia do języka **DAX**.

Rozwinięcie skrótu **DAX** to **Data Analysis Expressions** i jest to nazwa języka formuł używanego w usłudze Power BI (jest on również używany przez usługę Power BI w tle). Język DAX można również znaleźć w innych ofertach firmy Microsoft, takich jak dodatek Power Pivot i widok tabelaryczny SSAS, ale ten zbiór tematów nauki z przewodnikiem koncentruje się na używaniu języka DAX — i jak może on być przez Ciebie używany — w usłudze Power BI.

## <a name="dax-and-this-guided-learning-video-series"></a>Język DAX i ta seria filmów wideo Nauka z przewodnikiem
Celem tej sekcji **Nauka z przewodnikiem** jest nauczenie Cię podstaw i zasad języka DAX — jak myśleć o języku DAX, o tym, jak on działa, i o najbardziej przydatnych funkcjach objaśnionych (i opartych na wiedzy zdobytej na podstawie dużego doświadczenia) przez znanego eksperta z zakresu języka DAX, [Alberta Ferrariego](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit).

![Zdjęcie Alberta Ferrariego](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

Filmy wideo w tej sekcji **Nauka z przewodnikiem** dotyczącej języka **DAX** nauczą Cię podstaw języka DAX z perspektywy sposobu działania języka formuł DAX. Jest to przydatne podczas tworzenia formuł języka DAX od podstaw, ale jest również bardzo przydatne dla zrozumienia, jak usługa Power BI tworzy te formuły języka DAX w miarę tworzenia przez Ciebie zapytań w **Edytorze zapytań**.

## <a name="in-this-video---introduction-to-dax"></a>W tym filmie wideo — wprowadzenie do języka DAX
Pojęcia języka DAX są proste i oczywiste, ale język DAX jest zaawansowany. Język DAX używa pewnych unikatowych pojęć i wzorców programowania, które mogą utrudnić pełne jego wykorzystanie i zrozumienie. Tradycyjne sposoby nauki języków mogą nie być najlepszym podejściem do języka DAX, więc celem tego filmu wideo jest nauczenie Cię pojęć i teorii, które będą pomocne później podczas pracy z usługą Power BI.

Język DAX jest *językiem funkcjonalnym*, co oznacza, że pełny wykonywany kod znajduje się wewnątrz funkcji.

W języku DAX funkcje mogą zawierać inne, zagnieżdżone funkcje, instrukcje warunkowe i odwołania do wartości. Wykonywanie w języku DAX zaczyna się od najbardziej wewnętrznej funkcji lub parametru i postępuje na zewnątrz. W usłudze Power BI formuły języka DAX są zapisywane w jednym wierszu, dlatego poprawne sformatowanie funkcji jest ważne dla czytelności.

Język DAX jest przeznaczony do pracy z tabelami, dlatego ma tylko dwa typy danych podstawowych: **Liczbowe** i **Inne**. Dane **Liczbowe** mogą obejmować *liczby całkowite*, *liczby dziesiętne* i *waluty*. **Inne** dane mogą obejmować *ciągi* i *obiekty binarne*. Oznacza to, że jeśli utworzysz swoją funkcję języka DAX do działania na jednym typie liczby, możesz mieć pewność, że będzie ona działać na każdych innych danych liczbowych.

Język DAX używa przeładowania operatora, co oznacza, że możesz mieszać typy danych w obliczeniach i wyniki zmienią się na podstawie typu danych użytych w danych wejściowych. Konwersja odbywa się automatycznie. Oznacza to, że nie musisz znać typów danych kolumn, z którymi pracujesz w usłudze Power BI, ale oznacza to również, że czasami konwersja może nastąpić w nieoczekiwany sposób. Należy dobrze zrozumieć dane, których używasz, aby upewnić się, że Twoje operatory zachowują się zgodnie z przewidywaniami.

W szczególności istnieje jeden typ danych, z którym prawdopodobnie będziesz najwięcej pracować w usłudze Power BI: **DateTime**. Typ **DateTime** jest przechowywany jako wartość zmiennoprzecinkowa zarówno z częścią całkowitą, jak i dziesiętną. Typu DateTime można dokładnie używać do obliczeń dowolnego okresu czasu po 1 marca 1900 roku.

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

