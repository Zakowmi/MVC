CineVault – Katalog Kolekcji Filmów

Spis treści

1. Opis projektu
2. Funkcjonalności
3. Instrukcja uruchomienia
4. Technologie
5. Struktura MVC

Opis projektu

CineVault to prosta aplikacja internetowa do zarządzania osobistą kolekcją filmów,
zbudowana z wykorzystaniem wzorca architektonicznego MVC (Model-View-Controller).

Projekt realizuje Zadanie 12 – Katalog kolekcji filmów.

Funkcjonalności

-> Wyświetlanie listy filmów – wszystkie filmy prezentowane są w czytelnej tabeli z tytułem, reżyserem i oceną.
-> Dodawanie nowego filmu – formularz umożliwia wprowadzenie tytułu, reżysera oraz oceny (1–10).
-> Usuwanie filmu – każdy wpis można usunąć przyciskiem „Usuń".
-> Walidacja formularza – sprawdzane są wymagane pola oraz poprawność oceny (liczba 1–10).
-> Tryb ciemny / jasny – przycisk w nagłówku przełącza motyw aplikacji.
-> Responsywny układ – aplikacja działa poprawnie na urządzeniach mobilnych i desktopowych.

Instrukcja uruchomienia

Aplikacja jest statyczną stroną HTML – nie wymaga instalacji żadnych pakietów ani serwera.

Uruchomienie lokalne

1. Pobierz plik katalog-filmow.html.
2. Otwórz go w dowolnej nowoczesnej przeglądarce (Chrome, Firefox, Edge, Safari).

Nie są potrzebne żadne dodatkowe zależności. Czcionki ładowane są z Google Fonts (wymagany
dostęp do internetu).

Technologie
HTML5 - Struktura semantyczna
CSS3 - Stylowanie i układ responsywny
Vanilla JavaScript - Logika MVC
Google Fonts – DM Sans - Typografia

Aplikacja nie korzysta z żadnych zewnętrznych bibliotek JS ani frameworków.

Struktura MVC

Cała logika aplikacji zawarta jest w pliku katalog-filmow.html.
Kod JavaScript podzielony jest na trzy wyraźnie oddzielone moduły:

Model (const Model)

Zarządza danymi aplikacji (kolekcją filmów). Przechowuje listę filmów w pamięci i udostępnia
metody:

-> getAll() – zwraca listę wszystkich filmów
-> add({ title, director, rating }) – dodaje nowy film
-> remove(id) – usuwa film o podanym id

View (const View)

Odpowiada za renderowanie interfejsu użytkownika:

-> renderFilms(films) – generuje tabelę filmów lub komunikat pustego stanu
-> showError(msg) / clearError() – obsługa komunikatów błędów
-> getFormValues() – odczytuje wartości z formularza
-> resetForm() – czyści formularz po dodaniu filmu

Controller (const Controller)

Łączy Model i View. Obsługuje zdarzenia użytkownika:

-> handleAdd(e) – waliduje dane z formularza, wywołuje Model.add() i odświeża widok
-> handleDelete(id) – wywołuje Model.remove() i odświeża widok
