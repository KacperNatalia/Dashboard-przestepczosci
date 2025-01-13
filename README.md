Wymagane dokumenty
1. Charakterystyka oprogramowania 
a)	Nazwa skrócona :Dashboard przestępczości 
b)	Nazwa pełna: Zidentyfikowanie obszarów wysokiego ryzyka przestępczości w Polsce
c)	Krótki opis ze wskazaniem celów 
Projekt ma na celu stworzenie interaktywnego narzędzia analitycznego, które umożliwi ocenę poziomu przestępczości w różnych regionach Polski. Aplikacja, wyposażona w mapę Polski z podziałem na województwa i powiaty, pozwoli użytkownikom na szczegółową analizę danych historycznych dotyczących przestępczości, a także na przegląd rankingów regionów na podstawie wskaźnika kompozytowego obrazującego ryzyko przestępczości. Kluczowym celem projektu jest dostarczenie mieszkańcom, decydentom i badaczom narzędzia, które wspiera podejmowanie decyzji, np. w zakresie osiedlania się, planowania społecznego czy wdrażania polityk bezpieczeństwa. 
2. Prawa autorskie
a)	Autorzy:  Kacper Ossowski, Natalia Karpińska
b)	Warunki licencyjne oprogramowania:
Oprogramowanie korzysta z danych pochodzących z API Banku Danych Lokalnych (BDL) Głównego Urzędu Statystycznego, co zobowiązuje do przestrzegania warunków licencji BDL, w tym uznania autorstwa poprzez wskazanie GUS jako źródła danych. Licencja powinna określać, czy dane mogą być wykorzystywane do celów komercyjnych, oraz uwzględniać limity techniczne API opisane w dokumentacji BDL. Oprogramowanie może być udostępniane na licencji otwartej (np. MIT, Apache 2.0), komercyjnej lub mieszanej, w zależności od założeń dotyczących otwartości projektu i możliwości komercjalizacji. Licencja powinna precyzować warunki użytkowania, np. ograniczenie do celów badawczych lub niekomercyjnych, oraz zakazy, takie jak modyfikowanie kodu bez zgody autorów. Konieczne jest zamieszczenie klauzuli wyłączającej odpowiedzialność za błędne interpretacje danych lub szkody wynikające z użytkowania oprogramowania. Autorzy oprogramowania muszą być wskazani w widocznym miejscu aplikacji, np. w stopce, a dane opatrzone informacją: „Źródło danych: GUS, Bank Danych Lokalnych”. W przypadku udostępnienia na licencji open source należy jednoznacznie określić warunki korzystania, kopiowania i modyfikacji oprogramowania. Wszelkie licencje powinny być dostosowane do specyfiki projektu, uwzględniając zarówno ochronę praw autorskich, jak i dostępność narzędzia dla użytkowników.
3. Specyfikacja wymagań aplikacji: 1 – wymagane 2 – przydatne 3 - opcjonalne
ID	Nazwa	Opis	Priorytet	Kategoria
1	Integracja z API Banku Danych Lokalnych	Pobieranie danych o przestępczości z API Banku Danych Lokalnych, aby zapewnić regularne odświeżanie danych w aplikacji.	1	Funkcjonalne
2	Automatyczne aktualizowanie danych	Umożliwienie aplikacji automatycznego odświeżania wskaźników przestępczości zgodnie z harmonogramem aktualizacji API Banku Danych Lokalnych.	1	Funkcjonalne
3	Przetwarzanie danych	Analiza i kategoryzacja zebranych danych pod kątem typów przestępstw, lokalizacji oraz czasu, aby umożliwić efektywne wizualizacje.	1	Funkcjonalne
4	Dashboard z wskaźnikami przestępczości	Wyświetlanie interaktywnego panelu z wskaźnikami przestępczości, przedstawiającego różne wskaźniki dla różnych regionów Polski.	1	Funkcjonalne
5	Mapy interaktywne	
Możliwość przeglądania wskaźników przestępczości na mapach interaktywnych z podziałem na województwa i powiaty.
	1	Funkcjonalne
6	Filtry i sortowanie	Użytkownicy mogą filtrować dane według kategorii przestępstw, czasu, lokalizacji, itp.		Funkcjonalne
7	Ranking najbezpieczniejszych miejsc	Generowanie listy najbezpieczniejszych miejsc do zamieszkania na podstawie wskaźników przestępczości.	1	Funkcjonalne
8	Eksport danych	Możliwość eksportowania danych do plików (np. CSV).	3	Funkcjonalne
9	Responsywny interfejs użytkownika	Zapewnienie, że interfejs dostosowuje się do różnych rozdzielczości i urządzeń (np. desktop, mobile).	1	Pozafunkcjonalne
10	Dokumentacja aplikacji	Dostarczenie dokumentacji technicznej.	3	Pozafunkcjonalne

4. Architektura systemu/oprogramowania
a. Architektura rozwoju
Stos technologiczny wykorzystywany podczas rozwoju oprogramowania:

  1) Python
Przeznaczenie: Główny język programowania do przetwarzania danych, obliczeń wskaźników i integracji z bibliotekami geoprzestrzennymi.
Wersja: 3.10 lub wyższa.

  2) Pandas
Przeznaczenie: Przetwarzanie i analiza danych.
Wersja: 1.5.0 lub wyższa.

  3)GeoPandas
Przeznaczenie: Obsługa i analiza danych geoprzestrzennych.
Wersja: 0.12.0 lub wyższa.

  4)Streamlit
Przeznaczenie: Tworzenie interaktywnego interfejsu użytkownika.
Wersja: 1.15.0 lub wyższa.

  5)Matplotlib
Przeznaczenie: Wizualizacja danych i wykresy.
Wersja: 3.6.0 lub wyższa.

  6)Folium
Przeznaczenie: Obsługa plików geoprzestrzennych w formacie GML, GeoJSON itp.
Wersja: 1.9.0 lub wyższa.

b. Architektura uruchomieniowa
Stos technologiczny wymagany do uruchomienia oprogramowania:

  1)Python
Przeznaczenie: Środowisko uruchomieniowe do przetwarzania danych i obsługi logiki aplikacji.
Wersja: 3.10 lub wyższa.

  2)Streamlit
Przeznaczenie: Uruchamianie aplikacji w przeglądarce jako interaktywny dashboard.
Wersja: 1.15.0 lub wyższa.
  
  3)GeoPandas
Przeznaczenie: Obsługa danych geoprzestrzennych w środowisku uruchomieniowym.
Wersja: 0.12.0 lub wyższa.

  4)System operacyjny
Przeznaczenie: Hostowanie aplikacji.
Wersja: Linux, macOS lub Windows 10/11.
  
  5)Przeglądarka internetowa
Przeznaczenie: Wyświetlanie interfejsu użytkownika.
Wersja: Google Chrome, Mozilla Firefox lub inna nowoczesna przeglądarka (z aktualnymi wersjami).

5. Testy
a. Scenariusze testów

  1)Test poprawności wskaźników kompozytowych:
Cel: Sprawdzenie, czy wskaźniki kompozytowe dla województw i powiatów są prawidłowo obliczane.
Kroki:
Wprowadzenie danych testowych z różnymi wartościami przestępstw.
Obliczenie wskaźników według zaimplementowanych wag.
Porównanie wyników z oczekiwanymi wartościami.
  
  2)Test interfejsu użytkownika:
Cel: Weryfikacja, czy dashboard Streamlit poprawnie wyświetla dane dla województw i powiatów.
Kroki:
Uruchomienie aplikacji i załadowanie danych testowych.
Sprawdzenie poprawności kolorów i wartości na mapach.
Test funkcjonalności przejścia między województwami a powiatami.

  3)Test wydajności aplikacji:
Cel: Sprawdzenie, czy aplikacja działa płynnie z dużą ilością danych.
Kroki:
Zaimportowanie dużego zestawu danych przestępstw.
Monitorowanie czasu ładowania i wydajności interfejsu.

b. Sprawozdanie z wykonania scenariuszy testów
Test poprawności wskaźników kompozytowych:
Wynik pozytywny. Wskaźniki kompozytowe dla wszystkich danych testowych zgadzają się z oczekiwanymi wartościami.

Test interfejsu użytkownika:
Wynik pozytywny. Kolory i wartości na mapach są zgodne z obliczonymi wskaźnikami. Przejście między województwami a powiatami działa poprawnie.

Test wydajności aplikacji:
Wynik pozytywny. Aplikacja działa, lecz przy obciążeniu danymi o rozmiarze powyżej 100 tysięcy rekordów następuje spowolnienie działania.

