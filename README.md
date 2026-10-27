# Core (prosty szablon second brain)

**Core** to Twoja prywatna, nadrzędna pamięć dla AI: kilka plików tekstowych w repozytorium na GitHubie. Rozmawiasz z AI jak zwykle, a ono samo czyta i uzupełnia Twoją wiedzę. Nie ma bazy danych, aplikacji ani wtyczek — tylko pliki Markdown.

Dlaczego „Core", a nie kolejny second brain? Większość rozwiązań tego typu to osobne aplikacje z notatkami, które sam porządkujesz. Core działa odwrotnie: to jedno źródło prawdy o Tobie, którym zarządza AI w trakcie rozmowy, a Ty tylko je kontrolujesz.

## Dlaczego tak prosto

- **Rozmowa to jedyny interfejs.** Nie musisz niczego porządkować ręcznie.
- **Niezależność od modelu.** To zwykły tekst. Dziś Claude, jutro ChatGPT lub Gemini — Twoja wiedza zostaje u Ciebie.
- **Zadania i kalendarz w jednym miejscu.** Lista zadań w Core plus opcjonalny konektor kalendarza: AI zna Twój plan i pomaga go ułożyć.
- **Kontrola.** Każda zmiana zapisana przez AI jest w historii Git. Widzisz, co i kiedy się zmieniło, i możesz to cofnąć.
- **Prywatność.** Repozytorium jest prywatne i tylko Ty decydujesz, kto ma do niego dostęp.

## Instalacja krok po kroku (ok. 15 minut)

### 1. Załóż konto na GitHubie
Wejdź na [github.com](https://github.com) i zarejestruj się (darmowe konto wystarczy).

### 2. Utwórz własną kopię szablonu
1. Na stronie tego repozytorium kliknij zielony przycisk **Use this template** → **Create a new repository**.
2. W polu *Repository name* wpisz np. `core`.
3. **Ważne:** zaznacz **Private**. Twoje dane mają być widoczne tylko dla Ciebie.
4. Kliknij **Create repository**.

### 3. Uzupełnij podstawy
Otwórz plik `profil.md`, kliknij ikonę ołówka i wpisz kilka zdań o sobie. Resztę AI uzupełni w trakcie rozmów. Zapisz przyciskiem **Commit changes**.

### 4. Połącz AI z repozytorium
Wybierz jedną drogę:

**Claude (claude.ai):** *Settings → Connectors → GitHub* i połącz konto. Przy tworzeniu rozmowy lub projektu wskaż swoje repozytorium `core`.

**ChatGPT:** *Settings → Connectors → GitHub*, połącz konto i wskaż repozytorium `core`.

**Inne narzędzia (Claude Code, Cursor, Codex itp.):** sklonuj repozytorium na komputer i otwórz ten folder w narzędziu.

### 5. Dodaj instrukcję stałą dla AI
To najważniejszy krok: sprawia, że AI zagląda do Core w każdej rozmowie, a nie tylko wtedy, gdy o tym pamiętasz. W ustawieniach AI wklej:

- **Claude:** *Settings → Profile → Personal preferences* albo instrukcje projektu.
- **ChatGPT:** *Settings → Personalization → Custom instructions* albo instrukcje projektu.

> Przed każdą odpowiedzią dotyczącą mnie lub mojego życia sprawdź moje prywatne repozytorium GitHub "TWOJ-LOGIN/core" (wpisz tu swój login i nazwę repozytorium). Najpierw przeczytaj "CORE.md", następnie tylko pliki potrzebne do odpowiedzi. Stosuj opisane w nim zasady odczytu, zapisu i organizacji wiedzy.
>
> Core jest nadrzędnym źródłem trwałej wiedzy o mnie. Moja najnowsza jednoznaczna informacja z bieżącej rozmowy ma pierwszeństwo przed wcześniejszym zapisem w Core.
>
> Nowe, jednoznaczne informacje o mnie i moim życiu zapisuj automatycznie, bez każdorazowego pytania o zgodę. Dotyczy to również drobnych faktów, zdarzeń, preferencji, opinii, planów, rozważań, decyzji i zmian stanu. Zachowuj charakter informacji oraz jej niepewność. Nie zapisuj transkrypcji ani zwykłych pytań o wiedzę ogólną.
>
> Przed zapisem odczytaj właściwy plik, unikaj duplikatów i wykonuj najmniejszą potrzebną zmianę. Po zapisie ponownie odczytaj plik i zweryfikuj rezultat. Większe zmiany struktury, przenoszenie danych między obszarami, zmiany uprawnień i reorganizacja repozytorium wymagają mojej wyraźnej zgody.

Pamiętaj, żeby w tekście podmienić `TWOJ-LOGIN/core` na swoje dane. Zasady dotyczące zadań i kalendarza AI znajdzie w `CORE.md`, więc nie trzeba ich powtarzać w instrukcji.

### 6. (Rozszerzenie) Podłącz kalendarz
Core ma plik `zadania.md`, a razem z kalendarzem daje pełny obraz Twojego planu: co masz do zrobienia i kiedy masz czas.

1. W ustawieniach konektorów AI (*Settings → Connectors*) podłącz **Google Calendar**. Inne kalendarze (np. Outlook) działają, jeśli Twoje narzędzie ma dla nich konektor.
2. Poproś: *„Co mam dziś do zrobienia? Sprawdź zadania i kalendarz."* AI powinno odczytać oba źródła i zaproponować plan dnia.

Kalendarz jest opcjonalny. Bez niego Core działa, a AI korzysta wyłącznie z listy zadań i mówi o tym wprost.

### 7. Sprawdź, czy działa
Napisz: *„Co o mnie wiesz?"* — AI powinno odwołać się do `profil.md`. Potem powiedz coś nowego, np. *„Zaczynam nową pracę od 1 listopada"*, i poproś, żeby zapisało to w Core. Zajrzyj do repozytorium: pojawi się nowy wpis w pliku `praca.md`. Na koniec dodaj zadanie: *„Dodaj zadanie: umówić przegląd samochodu do 15 listopada"* i sprawdź `zadania.md`.

## Jak to jest zbudowane

| Plik | Do czego służy |
| --- | --- |
| `CORE.md` | Zasady dla AI: co czytać, jak zapisywać. Najważniejszy plik. |
| `profil.md` | Kim jesteś, rutyna, preferencje |
| `praca.md` | Praca, projekty, kariera |
| `zdrowie.md` | Zdrowie, cele, nawyki |
| `finanse.md` | Finanse, plany |
| `zadania.md` | Zadania i terminy; razem z kalendarzem daje obraz planu dnia |
| `inne.md` | Wszystko, co nie pasuje gdzie indziej |
| `procedury.md` | Reguły kontroli jakości zapisów |

Zasada: **jeden temat = jeden plik**, a każdy plik ma ten sam szkielet: *Bieżący kontekst* i *Historia*. Nowy temat? Dodaj plik i wpis do tabeli w `CORE.md`.

## Bezpieczeństwo

- Trzymaj repozytorium **prywatne**. Nigdy nie wpisuj haseł, numerów kart ani PESEL-u.
- Zrób kopię zapasową (np. regularny `git clone` na dysk).
- Sprawdź w ustawieniach swojego AI, czy Twoje rozmowy nie służą do trenowania modeli.

## Licencja

MIT — korzystaj i modyfikuj dowolnie.
