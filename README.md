# Dane SmartHome – zbiór danych do uczenia maszynowego

Zbiór rzeczywistych danych z systemu inteligentnego domu (SmartHome), zebranych przez urządzenia LuON.  
Dane przeznaczone są do ćwiczeń z uczenia maszynowego i analizy szeregów czasowych.

## Struktura

```
chata/          – dane z jednej lokalizacji (dom jednorodzinny)
```

Każdy plik CSV odpowiada jednemu urządzeniu. Nazwa pliku: `lu_<ID>_<typ>.csv`

## Typy urządzeń

| Typ w nazwie | Opis | Kolumny |
|---|---|---|
| `temp` | Czujnik temperatury / wilgotności / ciśnienia | `Czas; Temperatura [C]; Wilgotnosc [%]; Cisnienie [hPa]; Nr prob.` |
| `light` | Inteligentna żarówka / oprawa | `Czas; Zrodlo; Stan; Jasnosc; Barwa [deg]; Saturacja; CT [Mired]; Tryb; Scena` |
| `switch` | Przełącznik / przekaźnik | `Czas; Zrodlo; Stan; Czas powrotu; Odliczanie; Rewert; Tryb startu` |
| `outlet` | Gniazdko smart | `Czas; Zrodlo; Stan; ...` |
| `power` | Miernik mocy | `Czas; Moc czynna [W]; Moc pozorna [VA]; Prad [A]; Napiecie [V]; Energia kw. [kWh]` |
| `presence` | Czujnik obecności / ruchu | `Czas; Zrodlo; Obecnosc; Szum otoczenia` |

## Format danych

- Separator: **średnik** (`;`)
- Kodowanie: **UTF-8**
- Znacznik czasu: `RRRR-MM-DD GG:MM:SS` (czas lokalny, Europa/Warszawa)
- Rekordy ułożone **od najnowszego do najstarszego**
- Łącznie: ~4 200 000 rekordów

## Kolumna `Zrodlo`

Wskazuje inicjatora zmiany stanu:

| Wartość | Znaczenie |
|---|---|
| `DEV` | Zmiana z urządzenia (fizyczny przycisk, czujnik) |
| `HK` | Polecenie z Apple HomeKit |
| `AUTO` | Automatyzacja wewnętrzna |

## Przykładowe zastosowania

- Klasyfikacja wzorców użytkowania urządzeń
- Prognozowanie zużycia energii
- Anomaly detection (wykrywanie awarii)
- Analiza komfortu cieplnego
- Klastrowanie urządzeń wg zachowania

## Licencja

Dane udostępnione do celów edukacyjnych i badawczych.  
Przy publikacji wyników prosimy o podanie źródła.
