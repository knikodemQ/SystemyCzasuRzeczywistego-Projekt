## Inteligentny automat do napełniania wodą butelek wielokrotnego użytku

### Projekt realizowany w ramch przedmiotu systemy czasu rzeczywistego przy użyciu architektury AADL

#### Imię i Nazwisko:
Krzysztof Nikodem

#### Mail:

knikodem@student.agh.edu.pl

#### Opis projektu:

System umożliwia użytkownikowi napełnianie/uzupełnianie wodą butelki wielokrotnego użytku. Urządzenie rozpoznaje obecność butelki, jej typ, dobiera ilość i rodzaj wody (gazowana/niegazowana), kontroluje jej poziom i jakość przy pomocy sensorów. Automat wyposażony jest w interfejs użytkownika oraz możliwość zdalnego zarządzania przez aplikację mobilną.

#### Przykładowe wykorzystanie proponowanego systemu przez użytkownika:

Użytkownik podkłada butelkę pod dyszę. System rozpoznaje obecność i typ butelki, wyświetla opcje wyboru (typ wody, ilość, stopień gazowania) na ekranie automatu lub aplikacji. Po naciśnięciu przycisku start system napełnia butelkę wodą zgodnie z preferencjami, dodaje CO2 jeśli wybrano wodę gazowaną, informuje o zakończeniu procesu.

#### Data [Data]

- `BottlePresenceData:` flaga obecności butelki

- `BottleTypeData:` typ gwintu butelki

- `WaterLevelData:` poziom wody

- `WaterQualityData:` dane z sensorów jakości (pH, temp)

- `UserPreferencesData:` wybór użytkownika (gazowana/niegazowana, ilość)

- `CO2LevelData:` stan zasobnika CO2

- `SystemStatusData:` błędy, ostrzeżenia, statusy

- `UICommandData:` komendy z interfejsu użytkownika

- `MobileAppCommandData:` dane z aplikacji mobilnej

#### Urządzenia [Devices]

- `BottlePositionSensor:` Sensor pozycji/położenia butelki

- `BottleThreadSensor:` Czujnik typu gwintu butelki

- `StillWaterValve:` Zawór wody niegazowanej

- `SparklingWaterValve:` Zawór wody gazowanej

- `WaterPump:` Pompa ciśnienia

- `WaterLevelSensor:` Sensor poziomu wody w butelce

- `CO2Saturator:` Moduł saturatora CO2

- `WaterQualitySensor:` Sensor jakości wody (pH, temperatura)

- `LCDDisplay:` Wyświetlacz LCD

- `UserInterface:` Fizyczny interfejs użytkownika (przyciski)

- `BluetoothModule:` Moduł Bluetooth

#### Wątki [Threads]

- `BottlePositionCheckThread:`	Wykrywanie obecności butelki
  
- `BottleThreadTypeCheckThread:`	Rozpoznawanie typu gwintu butelki
  
- `WaterLevelMonitoringThread:`	Pomiar poziomu wody
  
- `WaterQualityMonitoringThread:`	Pomiar pH i temperatury wody
  
- `FillingControlThread:`	Koordynacja procesu napełniania
  
- `StillWaterValveControlThread:`	Obsługa zaworu wody niegazowanej
  
- `SparklingWaterValveControlThread:`	Obsługa zaworu wody gazowanej
  
- `CO2InjectionThread:`	Obsługa saturatora i nasycanie CO2
  
- `WaterPumpControlThread:`	Zarządzanie pompą ciśnienia
  
- `LCDDisplayThread:`	Wyświetlanie komunikatów na ekranie
  
- `PhysicalButtonHandlerThread:` Obsługa fizycznych przycisków automatu
  
- `BluetoothCommunicationThread:`	Komunikacja z aplikacją mobilną przez Bluetooth
  
#### Procesy [Processes]

- `FillingManagementProcess:` Odpowiada za realizację procesu napełniania butelki zgodnie z preferencjami.

- `SensorControlProcess:` Zajmuje się zbieraniem i analizą danych z czujników.

- `UserInterfaceProcess:` Zarządza interakcją z użytkownikiem lokalnie i zdalnie.

#### Magistrale [Bus]

- `Magistrala zasilania (PowerBus):` przypisanie źródeł zasilania do komponentów.
  
- `Magistrala danych (DataBus):` połączenie procesów, wątków i urządzeń.

#### Procesory [Processors]
- `MainController:` główny procesor sterujący pracą całego systemu.

#### Pamięć [Memory]
- `SystemMemory:` pamięć operacyjna dla systemu.

#### System [System] 
- `BottleRefillSystem:` kompletny system integrujący wszystkie komponenty.




