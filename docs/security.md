1. How [https works](https://howhttps.works/)
2. How JWT Works

Other:

Podejście do bezpieczeństwa aplikacji backendowej opiera się na następujących zasadach:

Weryfikacja danych wejściowych: Ważne jest, aby zawsze weryfikować i filtrować dane wejściowe, takie jak parametry żądania,
dane przesyłane przez formularze czy dane pochodzące z zewnętrznych źródeł. Weryfikacja powinna obejmować
sprawdzanie poprawności formatu, walidację wartości, ograniczenia długości i inne aspekty zgodne z oczekiwaniami biznesowymi.

Używanie bezpiecznych mechanizmów uwierzytelniania i autoryzacji: Aplikacje backendowe powinny stosować solidne
metody uwierzytelniania, takie jak uwierzytelnianie oparte na tokenach (np. JWT) lub protokoły takie jak OAuth.
Mechanizmy autoryzacji powinny być stosowane w celu kontroli dostępu do poszczególnych zasobów i funkcji systemu.

Zabezpieczanie komunikacji: Wszystkie komunikacje między klientem a serwerem powinny być zabezpieczone za pomocą
protokołu HTTPS, co zapewnia szyfrowanie danych podczas ich transmisji.

Zabezpieczanie danych w bazach danych: Wrażliwe dane przechowywane w bazach danych powinny być zabezpieczone
za pomocą odpowiednich mechanizmów, takich jak hashowanie haseł i przechowywanie tylko niezbędnych informacji. Ważne jest również regularne stosowanie łatek bezpieczeństwa i aktualizacji systemu zarządzania bazą danych.

Ograniczanie ataków typu OWASP Top 10: Aplikacje backendowe powinny być zabezpieczone przed popularnymi atakami,
takimi jak wstrzykiwanie SQL, ataki XSS, CSRF itp. Bezpieczne kodowanie i walidacja danych wejściowych oraz odpowiednie
konfiguracje serwera mogą pomóc w ograniczeniu tych ataków.

Audyt i monitorowanie: Ważne jest, aby monitorować i analizować logi systemowe oraz przeprowadzać audyty
bezpieczeństwa w celu wykrywania nieprawidłowości, prób ataków czy błędów bezpieczeństwa.
Regularne przeglądy i aktualizacje procedur bezpieczeństwa są kluczowe dla utrzymania wysokiego poziomu bezpieczeństwa
aplikacji.

Edukacja i świadomość: Wszyscy członkowie zespołu powinni być świadomi podstawowych zasad bezpieczeństwa i praktyk,
tak aby unikać podatności na ataki. Regularne szkolenia i edukacja w dziedzinie bezpieczeństwa informatycznego są
ważne dla zwiększenia świadomości i dbałości o bezpieczeństwo
