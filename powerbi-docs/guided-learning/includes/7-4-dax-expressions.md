Używanie **zmiennych** to wyjątkowo zaawansowana część wyrażenia języka DAX.

![](media/7-4-dax-expressions/dax-variables_1.png)

Zmienną możesz zdefiniować w dowolnym miejscu wyrażenia języka DAX, używając następującej składni:

    VARNAME = RETURNEDVALUE

Zmienne mogą być dowolnego typu danych, łącznie z całymi tabelami.

Należy pamiętać, że przy każdym odwołaniu do zmiennej w wyrażeniu języka DAX usługa Power BI musi ponownie obliczyć jej wartość zgodnie z definicją. Z tego powodu dobrze jest unikać powtarzania zmiennych w funkcji.

> Zawartość wideo dzięki uprzejmości [Alberta Ferrariego, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

