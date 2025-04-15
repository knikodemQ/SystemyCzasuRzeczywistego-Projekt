## Inteligentny automat do napełniania wodą butelek wielokrotnego użytku

### Projekt realizowany w ramch przedmiotu systemy czasu rzeczywistego przy użyciu architektury AADL

#### Opis projektu:

System umożliwia użytkownikowi napełnianie/uzupełnianie wodą butelki wielokrotnego użytku. Urządzenie rozpoznaje obecność butelki, jej typ, dobiera ilość i rodzaj wody (gazowana/niegazowana), kontroluje jej poziom i jakość przy pomocy sensorów. Automat wyposażony jest w interfejs użytkownika oraz możliwość zdalnego zarządzania przez aplikację mobilną.

#### Przykładowe wykorzystanie proponowanego systemu przez użytkownika:

Użytkownik podkłada butelkę pod dyszę. System rozpoznaje obecność i typ butelki, wyświetla opcje wyboru (typ wody, ilość, stopień gazowania) na ekranie automatu lub aplikacji. Po naciśnięciu przycisku start system napełnia butelkę wodą zgodnie z preferencjami, dodaje CO2 jeśli wybrano wodę gazowaną, informuje o zakończeniu procesu.

#### Wykorzystane komponenty i zaproponowane rozwiązania:

1. Sensor pozycji/położenia butelki [device]

  - Wykrywa fizyczną obecność butelki.
  - Zwraca informacje o poprawnym bądź niepoprawnym położeniu butelki.

2. Czujnik typu gwintu butelki [device]

  - Optyczny sensor sprawdzający rozmiar i typ gwintu butelki.
  - Dopasowuje złącze gwintowe w zależności od jego typu.

3. Zawór wody gazowanej/Zawór wody niegazowanej [device]

  - Zawór doprowadzający wodę niegazowaną.
  - Zawór doprowadzający wodę gazowaną w zależności od sprawności saturatora.

4. Pompa ciśnienia utrzymująca przepływ wody [device]

  - Podtrzymuje odpowiednie ciśnienie w systemie wodnym.
  - Informuje o krytycznych błędach uniemożliwiających działanie systemu.
 
5. Sensor poziomu wody w butelce [device]

  - Zapewnia optyczny pomiar poziomu wody w napelnianej butelce.
  - Informacja o poziomie wpływa na poprawne uzupełnianie butelki.

6. Moduł saturatora CO2 [device]

  - Wstrzykuje CO2 do wody w określonym przez użytkownika stopniu.
  - Zwraca informacje o ewentualnym wyczerpaniu CO2 w saturatorze.
    
7. Sensor jakości wody [device]
  - Czujniki pH, temperatury.
  - Informacja dla użytkonika o jakości wody.

8. Moduł sterujący czujników [process]

  - Moduł odpowiadający za zbieranie, zarządzanie danymi i pomiarami z czujników.
  - Spójność zebranych i przekazanych danych.

9. Wyświetlacz LCD dla autoamtu [device]

  - Wyświetla komunikaty, wybór wody, błędy, status.
  - Informacja dla użytkownika.

10. Interfejs użytkownika [device]

  - Fizyczne przyciski do obsługi autoamtu.
  - Decyzja o typie uzupełnianej wody i jej ilości.

11. Moduł Bluetooth [device]

  - Obsługa aplikacji mobilnej i zdalnego monitorowania.
  - Komunikacja użytkownik, automat.

12. Magistrale [bus]

  - Magistrala danych (DataBus) połączenie procesów, wątków i urządzeń.
  - Magistrala zasilania (PowerBus) przypisanie źródeł zasilania do komponentów.

