# E-commerce API Testing – Postman

## Opis projektu

Projekt przedstawia testowanie REST API przykładowego sklepu internetowego z wykorzystaniem programu Postman.

Testy zostały przeprowadzone na publicznym API DummyJSON, które udostępnia przykładowe dane produktów oraz umożliwia symulowanie operacji dodawania, aktualizowania i usuwania produktów.

Celem projektu było praktyczne poznanie testowania API, tworzenia automatycznych testów odpowiedzi oraz uruchamiania całej kolekcji w Postman Runner.

## Wykorzystane technologie i narzędzia

- Postman
- REST API
- JSON
- JavaScript – podstawowe skrypty testowe
- Postman Collection Runner
- GitHub

**Testowane API:** https://dummyjson.com/

## Zakres testowania

W projekcie wykorzystano metody HTTP:

- **GET** – pobieranie i wyszukiwanie produktów.
- **POST** – symulowane dodawanie produktu.
- **PATCH** – symulowana aktualizacja ceny produktu.
- **DELETE** – symulowane usuwanie produktu.

Przeprowadzono testy pozytywne i negatywne.

## Wykonane testy

| ID | Nazwa testu | Metoda | Liczba testów PASS |
|---|---|---|---|
| API-001 | All Products | GET | 4 |
| API-002 | Single Product | GET | 3 |
| API-003 | Product Not Found | GET | 2 |
| API-004 | Search Products | GET | 4 |
| API-005 | Search No Results | GET | 2 |
| API-006 | Add Product | POST | 3 |
| API-007 | Update Product | PATCH | 2 |
| API-008 | Delete Product | DELETE | 2 |

## Automatyczne testy API

Do sprawdzania odpowiedzi wykorzystano skrypty JavaScript w Postmanie.

Testy obejmują:

- Sprawdzanie kodów odpowiedzi HTTP (200, 201, 404).
- Weryfikację struktury odpowiedzi JSON.
- Sprawdzanie typów danych.
- Sprawdzanie identyfikatorów produktów.
- Weryfikację nazw i cen produktów.
- Sprawdzanie pustych i niepustych list.
- Weryfikację komunikatu o nieistniejącym produkcie.
- Sprawdzanie odpowiedzi po symulowanym dodaniu, aktualizacji i usunięciu produktu.

Do automatycznych asercji wykorzystano `pm.test()` oraz `pm.expect()`.

## Wyniki testowania

Całą kolekcję uruchomiono za pomocą Postman Collection Runner.

| Wynik | Liczba |
|---|---|
| Liczba zapytań | 8 |
| Liczba testów automatycznych | 22 |
| PASS | 22 |
| FAIL | 0 |
| Błędy wykonania | 0 |
| Liczba iteracji | 1 |

**Wynik końcowy: 100% PASS podczas udokumentowanego uruchomienia.**

## Zmienne kolekcji

W projekcie zastosowano zmienną kolekcji:

`baseUrl = https://dummyjson.com`

Dzięki temu adresy zapytań wykorzystują wspólną wartość, np.:

`{{baseUrl}}/products`

Ułatwia to zarządzanie adresami API.

## Uruchomienie projektu

1. Pobierz kolekcję Postmana z repozytorium.
2. Uruchom program Postman.
3. Wybierz opcję Import i wskaż pobrany plik JSON.
4. Sprawdź, czy zmienna `baseUrl` ma wartość `https://dummyjson.com`.
5. Otwórz wybrane zapytanie i kliknij Send.
6. Aby wykonać wszystkie testy, uruchom kolekcję w Postman Runner.

**Plik kolekcji:** [E-commerce API Testing.postman_collection.json](E-commerce%20API%20Testing.postman_collection.json)

## Ograniczenia testowanego API

DummyJSON jest API demonstracyjnym. Operacje POST, PATCH i DELETE zwracają odpowiedzi symulujące zmiany, ale nie zapisują ich trwale na serwerze.

Testy tych operacji sprawdzają odpowiedzi serwera, a nie trwałość zmian w bazie danych.

## Wnioski

Projekt umożliwił praktyczne poznanie testowania REST API w Postmanie.

Podczas pracy przećwiczono wykonywanie zapytań HTTP, analizowanie odpowiedzi JSON, pisanie podstawowych skryptów testowych, wykorzystanie zmiennych kolekcji oraz automatyczne uruchamianie zestawu testów.
