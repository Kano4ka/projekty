# Projekt Elektro-Bud – analiza wymagań

## 1. Opis systemu

Celem projektu jest przygotowanie analizy wymagań dla systemu zarządzania magazynem firmy Elektro-Bud.

Firma jest hurtownią materiałów elektrycznych i budowlanych. Obecnie pracownicy korzystają z dokumentów papierowych, arkuszy kalkulacyjnych oraz ręcznych zapisów. Nowy system ma usprawnić wyszukiwanie produktów, kontrolowanie stanów magazynowych, przyjmowanie i wydawanie towarów oraz prowadzenie historii operacji.

System będzie posiadał różne poziomy dostępu zależne od roli użytkownika.

---

# 2. Wymagania funkcjonalne

| ID    | Nazwa                               | Opis                                                                                                                        |
| ----- | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| FR-01 | Logowanie użytkownika               | System umożliwia użytkownikowi zalogowanie się za pomocą indywidualnego loginu i hasła.                                     |
| FR-02 | Wyszukiwanie produktu               | Użytkownik może wyszukać produkt na podstawie jego nazwy lub kodu EAN.                                                      |
| FR-03 | Wyświetlanie informacji o produkcie | System wyświetla nazwę produktu, kod EAN, kategorię, lokalizację oraz aktualny stan magazynowy.                             |
| FR-04 | Sprawdzanie lokalizacji produktu    | Użytkownik może sprawdzić sektor, regał oraz półkę, na której znajduje się produkt.                                         |
| FR-05 | Sprawdzanie stanu magazynowego      | System umożliwia sprawdzenie aktualnej liczby sztuk danego produktu.                                                        |
| FR-06 | Rejestrowanie przyjęcia towaru      | Magazynier może zarejestrować przyjęcie produktu wraz z ilością, użytkownikiem oraz datą i godziną operacji.                |
| FR-07 | Aktualizacja stanu po przyjęciu     | Po zarejestrowaniu przyjęcia system zwiększa stan magazynowy produktu.                                                      |
| FR-08 | Rejestrowanie wydania towaru        | Magazynier może zarejestrować wydanie produktu wraz z ilością, użytkownikiem oraz datą i godziną operacji.                  |
| FR-09 | Kontrola dostępnej ilości           | Przed wydaniem system sprawdza, czy na magazynie znajduje się wystarczająca liczba produktów.                               |
| FR-10 | Aktualizacja stanu po wydaniu       | Po prawidłowym wydaniu system zmniejsza stan magazynowy produktu.                                                           |
| FR-11 | Blokowanie nieprawidłowego wydania  | System nie pozwala wydać większej liczby produktów niż aktualnie znajduje się na magazynie.                                 |
| FR-12 | Historia operacji                   | System zapisuje historię przyjęć i wydań towarów.                                                                           |
| FR-13 | Przeglądanie historii               | Kierownik magazynu może przeglądać historię wykonanych operacji.                                                            |
| FR-14 | Zarządzanie produktami              | Kierownik może dodawać oraz edytować informacje o produktach.                                                               |
| FR-15 | Przeglądanie stanów magazynowych    | Kierownik może przeglądać aktualne stany wszystkich produktów.                                                              |
| FR-16 | Raporty magazynowe                  | Kierownik może generować raporty dotyczące stanów i operacji magazynowych.                                                  |
| FR-17 | Zarządzanie użytkownikami           | Administrator może tworzyć, edytować oraz blokować konta użytkowników.                                                      |
| FR-18 | Zarządzanie uprawnieniami           | Administrator może przypisywać użytkownikom odpowiednie role i uprawnienia.                                                 |
| FR-19 | Obsługa zapomnianego hasła          | System umożliwia obsługę procesu odzyskania dostępu do konta po zapomnieniu hasła.                                          |
| FR-20 | Obsługa równoczesnych operacji      | System prawidłowo obsługuje sytuację, gdy kilku użytkowników jednocześnie wykonuje operacje dotyczące tego samego produktu. |

---

# 3. Wymagania niefunkcjonalne

| ID     | Nazwa                           | Opis / kryterium                                                                                                                                 |
| ------ | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| NFR-01 | Wydajność                       | Wyszukiwanie produktu oraz sprawdzanie informacji powinno zazwyczaj zajmować około 1–2 sekund.                                                   |
| NFR-02 | Uwierzytelnianie                | Dostęp do systemu wymaga zalogowania za pomocą indywidualnych danych użytkownika.                                                                |
| NFR-03 | Bezpieczne przechowywanie haseł | Hasła użytkowników powinny być przechowywane w postaci bezpiecznych skrótów, a nie jako zwykły tekst.                                            |
| NFR-04 | Kontrola dostępu                | Użytkownik może korzystać tylko z funkcji dostępnych dla jego roli.                                                                              |
| NFR-05 | Spójność danych                 | System nie może dopuścić do powstania ujemnego stanu magazynowego.                                                                               |
| NFR-06 | Obsługa współbieżności          | Jednoczesne operacje wykonywane przez różnych użytkowników nie mogą powodować błędnego stanu magazynowego.                                       |
| NFR-07 | Dostęp zdalny                   | Uprawniony kierownik powinien mieć możliwość dostępu do informacji magazynowych również poza stanowiskiem magazynowym.                           |
| NFR-08 | Wielodostępność                 | System powinien umożliwiać jednoczesną pracę co najmniej 3 magazynierów oraz kierownika lub administratora.                                      |
| NFR-09 | Indywidualne konta              | Każdy użytkownik powinien posiadać własne konto umożliwiające identyfikację osoby wykonującej operację.                                          |
| NFR-10 | Rejestrowanie operacji          | Każda operacja powinna zawierać informację o użytkowniku, produkcie, rodzaju operacji, ilości oraz dacie i godzinie.                             |
| NFR-11 | Użyteczność                     | Interfejs powinien umożliwiać szybkie wykonywanie podstawowych operacji magazynowych.                                                            |
| NFR-12 | Dostępność informacji           | Uprawniony użytkownik powinien mieć możliwość szybkiego sprawdzenia produktu, jego lokalizacji i stanu bez korzystania z dokumentów papierowych. |

---

# 4. Aktorzy systemu

## 4.1. Magazynier

Magazynier jest pracownikiem odpowiedzialnym za codzienną obsługę magazynu.

Może:

* zalogować się do systemu,
* wyszukiwać produkty,
* sprawdzać lokalizację produktu,
* sprawdzać stan magazynowy,
* przyjmować towary,
* wydawać towary.

## 4.2. Kierownik magazynu

Kierownik odpowiada za kontrolę magazynu i analizę jego działania.

Może:

* zalogować się do systemu,
* zarządzać informacjami o produktach,
* przeglądać stany magazynowe,
* przeglądać historię operacji,
* generować raporty.

## 4.3. Administrator

Administrator odpowiada za konta użytkowników i uprawnienia.

Może:

* zalogować się do systemu,
* zarządzać użytkownikami,
* tworzyć i blokować konta,
* nadawać role,
* zarządzać uprawnieniami,
* obsługiwać problemy z dostępem do kont.

---

# 5. Przypadki użycia

## Magazynier

* Logowanie
* Wyszukaj produkt
* Sprawdź lokalizację
* Sprawdź stan magazynowy
* Przyjmij towar
* Wydaj towar

## Kierownik magazynu

* Logowanie
* Zarządzaj produktami
* Przeglądaj stany
* Przeglądaj historię operacji
* Generuj raport

## Administrator

* Logowanie
* Zarządzaj użytkownikami
* Zarządzaj uprawnieniami
* Obsłuż zapomniane hasło

---

# 6. Relacje `<<include>>` i `<<extend>>`

## 6.1. `<<include>>`

Relacja `<<include>>` oznacza, że jeden przypadek użycia zawsze korzysta z innego przypadku użycia.

W projekcie:

**Przyjmij towar** `<<include>>` **Zarejestruj operację**

Przyjęcie towaru musi zostać zapisane w systemie.

**Wydaj towar** `<<include>>` **Sprawdź dostępny stan**

Przed wydaniem system musi sprawdzić, czy wystarczająca ilość produktu znajduje się na magazynie.

**Wydaj towar** `<<include>>` **Zarejestruj operację**

Prawidłowo wykonane wydanie musi zostać zapisane w historii.

## 6.2. `<<extend>>`

Relacja `<<extend>>` oznacza dodatkowe zachowanie, które występuje tylko w określonej sytuacji.

W projekcie:

**Odrzuć wydanie z powodu braku towaru** `<<extend>>` **Wydaj towar**

Odrzucenie wydania następuje tylko wtedy, gdy użytkownik chce wydać więcej produktów, niż znajduje się aktualnie na magazynie.

### Przykład

Na magazynie znajduje się 5 sztuk produktu.

Magazynier próbuje wydać 8 sztuk.

System sprawdza stan magazynowy i wykrywa brak wystarczającej ilości. Wtedy uruchamiane jest dodatkowe zachowanie **„Odrzuć wydanie z powodu braku towaru”**.

---

# 7. Diagram UML – Use Case

Diagram został przygotowany w języku PlantUML.

Diagram znajduje się w osobnym pliku:

`diagram_use_case.puml`

---

# 8. Podsumowanie

System zarządzania magazynem Elektro-Bud ma zastąpić obecne papierowe i ręczne sposoby ewidencji.

Najważniejsze funkcje systemu to:

* wyszukiwanie produktów,
* sprawdzanie ich lokalizacji,
* kontrolowanie stanów magazynowych,
* przyjmowanie towarów,
* wydawanie towarów,
* prowadzenie historii operacji,
* zarządzanie produktami,
* generowanie raportów,
* zarządzanie użytkownikami i uprawnieniami.

System powinien zapewniać bezpieczeństwo danych, kontrolę dostępu, poprawność stanów magazynowych oraz możliwość jednoczesnej pracy kilku użytkowników.

Zastosowanie relacji `<<include>>` i `<<extend>>` pozwala dokładniej przedstawić zależności pomiędzy przypadkami użycia.
