# Wymagane dokumenty

## 1. Charakterystyka oprogramowania 
<ul>
<li>Nazwa skrócona: Dashboard przestępczości </li>
<li>Nazwa pełna: Zidentyfikowanie obszarów wysokiego ryzyka przestępczości w Polsce</li>
<li>Krótki opis ze wskazaniem celów:
Projekt ma na celu stworzenie interaktywnego narzędzia analitycznego, które umożliwi ocenę poziomu przestępczości w różnych regionach Polski. Aplikacja, wyposażona w mapę Polski z podziałem na województwa i powiaty, pozwoli użytkownikom na szczegółową analizę danych historycznych dotyczących przestępczości, a także na przegląd rankingów regionów na podstawie wskaźnika kompozytowego obrazującego ryzyko przestępczości. Kluczowym celem projektu jest dostarczenie mieszkańcom, decydentom i badaczom narzędzia, które wspiera podejmowanie decyzji, np. w zakresie osiedlania się, planowania społecznego czy wdrażania polityk bezpieczeństwa. </li>
</ul>

## 2. Prawa autorskie
<ul>
<li>Autorzy:  Kacper Ossowski, Natalia Karpińska</li>
<li>Warunki licencyjne oprogramowania: GNU GENERAL PUBLIC LICENSE, Version 2</li>
</ul>

## 3. Specyfikacja wymagań aplikacji:
| ID | Nazwa | Opis | Priorytet | Kategoria |
| -- | -------------------- | --------------| ------- | ------------ |
|1|	Integracja z API Banku Danych Lokalnych |Pobieranie danych o przestępczości z API Banku Danych Lokalnych, aby zapewnić regularne odświeżanie danych w aplikacji.| Wymagane |Funkcjonalne|
|2|	Automatyczne aktualizowanie danych|	Umożliwienie aplikacji automatycznego odświeżania wskaźników przestępczości zgodnie z harmonogramem aktualizacji API Banku Danych Lokalnych.|Wymagane|Funkcjonalne|
|3|	Przetwarzanie danych|	Analiza i kategoryzacja zebranych danych pod kątem typów przestępstw, lokalizacji oraz czasu, aby umożliwić efektywne wizualizacje.|Wymagane|Funkcjonalne|
|4|	Dashboard z wskaźnikami przestępczości|	Wyświetlanie interaktywnego panelu z wskaźnikami przestępczości, przedstawiającego różne wskaźniki dla różnych regionów Polski.|Wymagane|Funkcjonalne|
|5|	Mapy interaktywne|Możliwość przeglądania wskaźników przestępczości na mapach interaktywnych z podziałem na województwa i powiaty.|Wymagane|Funkcjonalne|
|6|	Filtry i sortowanie|	Użytkownicy mogą filtrować dane według kategorii przestępstw, czasu, lokalizacji, itp.	| Przydatne|Funkcjonalne|
|7|	Ranking najbezpieczniejszych miejsc|	Generowanie listy najbezpieczniejszych miejsc do zamieszkania na podstawie wskaźników przestępczości.|Wymagane|Funkcjonalne|
|8|	Eksport danych|	Możliwość eksportowania danych do plików (np. CSV).|Opcjonalne|Funkcjonalne|
|9|	Responsywny interfejs użytkownika|	Zapewnienie, że interfejs dostosowuje się do różnych rozdzielczości i urządzeń (np. desktop, mobile).|Wymagane|Pozafunkcjonalne|
|10|	Dokumentacja aplikacji|	Dostarczenie dokumentacji technicznej.	|Opcjonalne|Pozafunkcjonalne|

## 4. Architektura systemu/oprogramowania
### a. Architektura rozwoju
| Stos technologiczny wykorzystywany podczas rozwoju oprogramowania | Przeznaczenie | Wersja |
| -- | -------------------- | --------------|
|Python|Główny język programowania do przetwarzania danych, obliczeń wskaźników i integracji z bibliotekami geoprzestrzennymi.|3.10 lub wyższa|
|Pandas|Przetwarzanie i analiza danych.| 1.5.0 lub wyższa|
|GeoPandas|Obsługa i analiza danych geoprzestrzennych.|0.12.0 lub wyższa|
|Streamlit|Tworzenie interaktywnego interfejsu użytkownika.|1.15.0 lub wyższa|
|Matplotlib|Wizualizacja danych i wykresy.|3.6.0 lub wyższa|
|Folium|Obsługa plików geoprzestrzennych w formacie GML, GeoJSON itp.|1.9.0 lub wyższa|

### b. Architektura uruchomieniowa

|Stos technologiczny wymagany do uruchomienia oprogramowania| Przeznaczenie | Wersja |
| -- | -------------------- | --------------|
|Python|Środowisko uruchomieniowe do przetwarzania danych i obsługi logiki aplikacji.|3.10 lub wyższa|
|Streamlit|Uruchamianie aplikacji w przeglądarce jako interaktywny dashboard.|1.15.0 lub wyższa|
|GeoPandas| Obsługa danych geoprzestrzennych w środowisku uruchomieniowym.|0.12.0 lub wyższa|
|System operacyjny|Hostowanie aplikacji.|Linux, macOS lub Windows 10/11|
|Przeglądarka internetowa|Wyświetlanie interfejsu użytkownika.|Google Chrome, Mozilla Firefox lub inna nowoczesna przeglądarka (z aktualnymi wersjami)|

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

