# Time-Series-Forcasting
# Projekt ASR: Prognoza pogody w Rzeszowie
Plik .pdf zawiera dokładny opis całego projektu
## Krótkie streszczenie

Projekt polegał na analizie i prognozowaniu temperatury w Rzeszowie z wykorzystaniem różnych modeli szeregów czasowych. Dane meteorologiczne pochodziły ze strony NASA [https://power.larc.nasa.gov/data-access-viewer/](https://power.larc.nasa.gov/data-access-viewer/) i obejmowały lata 1982-2024.

### Modele użyte w projekcie:

1. **Model AR (Autoregressive Model)**: 
   - Testowanie liczby lagów i wybór modelu na podstawie najniższego AIC.
   - Model okazał się zbyt prosty dla naszych danych.

2. **Model MA (Moving Average Model)**: 
   - Podobna metoda do AR, ale iteracja po liczbie lagów MA.
   - Model nie poradził sobie dobrze z autokorelacją danych.

3. **Model ARIMA (Autoregressive Integrated Moving Average Model)**: 
   - Użycie funkcji auto_arima do wyboru najlepszych parametrów.
   - Model był przeładowany informacjami i miał problemy z sezonowością.

4. **Model SARIMA (Seasonal ARIMA)**:
   - Problemy z dużymi wymaganiami pamięciowymi przy dużej liczbie sezonowych danych.

5. **Model Facebook Prophet**:
   - Użycie modelu Prophet do radzenia sobie z sezonowością.
   - Dobre wyniki w przewidywaniu sezonowych wzorców.

### Dodatkowe analizy:

- **Regresja Liniowa i Seasonal Decompose**:
   - Użycie regresji liniowej i dekompozycji sezonowej do wyodrębnienia trendów.
   - Testowanie modeli AR, MA i ARIMA na zmodyfikowanych danych.

## Uruchamianie kodu

1. **Załadowanie danych**: Połączenie kolumn daty i ustawienie indeksu na częstotliwość dzienną.
2. **Czyszczenie danych**: Usuwanie i interpolowanie wartości anomalii.
3. **Podział na zbiory train/test**: Funkcje do podziału danych na różne proporcje.
4. **Wizualizacja wyników**: Funkcje do tworzenia wykresów i oceny dokładności modeli.

## Wyniki

Model Facebook Prophet wykazał się najlepszą dokładnością, szczególnie w radzeniu sobie z sezonowością danych. Modele AR, MA i ARIMA miały trudności z przewidywaniem złożonych wzorców temperatur.
