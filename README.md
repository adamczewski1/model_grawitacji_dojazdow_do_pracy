# model_grawitacji_dojazdow_do_pracy
Projekt dotyczy analizy dojazdów do pracy w aglomeracji bydgoskiej z wykorzystaniem modelu grawitacji. Celem badania jest sprawdzenie, jakie czynniki wpływają na natężenie przepływów pracowników między gminami oraz czy klasyczny model dobrze odwzorowuje rzeczywiste zachowania przestrzenne.

Patrzę na to, jak ludzie przemieszczają się do pracy między gminami w regionie Bydgoszczy. Zakładam, że:
	•	im większa liczba ludności (lub potencjał ekonomiczny), tym większe przepływy,
	•	im większa odległość, tym mniejsze przepływy.

Czyli klasyczna intuicja modelu grawitacji: „bliżej i większe = więcej ruchu”.

W analizie wykorzystałem:
	•	dane o przepływach między gminami (origin–destination),
	•	dane o liczbie ludności (jako przybliżenie „masy”),
	•	dane przestrzenne (shapefile gmin),
	•	odległości między gminami (liczone na podstawie centroidów).

Dane pochodzą głównie z GUS (BDL) oraz opracowań własnych.

Model estymowany był w dwóch podejściach:
	•	klasyczna regresja liniowa (OLS) w postaci log-log,
	•	model Poisson Pseudo-Maximum Likelihood (PPML), który lepiej radzi sobie z zerami i heteroskedastycznością.

Uwzględnione zmienne:
	•	masa origin (np. liczba ludności),
	•	masa destination,
	•	odległość między jednostkami.

Dodatkowo:
	•	testowałem heteroskedastyczność,
	•	badałem autokorelację przestrzenną reszt (statystyka Morana),
	•	analizowałem dopasowanie modelu.

Sprawdzam:
	•	czy model grawitacji dobrze opisuje rzeczywiste dojazdy,
	•	czy odległość faktycznie ogranicza przepływy,
	•	czy większe gminy generują/przyciągają więcej pracowników,
	•	czy w modelu występują zależności przestrzenne (czyli czy „sąsiedzi mają znaczenie”).

W projekcie znajdują się mapy przedstawiające:
	•	natężenie przepływów,
	•	rozkład zmiennych,
	•	różnice między wartościami rzeczywistymi a oszacowanymi.

Wykorzystywałem: 
	•	R (tidyverse, sf, tmap)
	•	pakiet gravity
	•	analiza przestrzenna i ekonometryczna
