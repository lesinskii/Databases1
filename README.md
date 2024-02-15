# Systemy Baz Danych 2023/2024 – projekt

## Wstęp

Otrzymaliście zlecenie zaprojektowania systemu bazodanowego dla firmy oferującej różnego rodzaju kursy i szkolenia. Początkowo oferowane usługi były świadczone wyłącznie stacjonarnie, ale ze względu na pandemię COVID-19 usługi zostały w różnym stopniu zdigitalizowane. Obecnie model świadczenia usług jest hybrydowy, ale bardzo niejednolity dla różnych usług. Oferowane usługi dzielą się na:

1. **Webinary**: odbywają się na żywo na jednej z popularnych platform chmurowych, następnie są nagrywane i udostępniane uczestnikom na okres 30 dni.
    - W ramach systemu bazodanowego nie przechowujemy danych binarnych – nagrania przechowywane są zewnętrznie.
    - Każdy webinar może być darmowy lub płatny. W przypadku webinarów płatnych, istnieje możliwość zakupienia dostępu do nich (również na okres 30 dni). Webinary bezpłatne są ogólnodostępne. Wszystkie webinary przechowywane są bezterminowo (ale administrator może je skasować).
    - Warunkiem koniecznym dostępu do webinaru jest posiadanie konta oraz potwierdzenie płatności (w przypadku webinarów płatnych).

2. **Kursy**: krótkie formy kształcenia, trwające zazwyczaj kilka dni, istnieją wyłącznie kursy płatne. Zaliczenie kursu wymaga zaliczenia min. 80% modułów. Moduły mogą być:
    - Stacjonarne – odbywają się synchronicznie, mają przypisaną salę zajęciową, zaliczane na podstawie obecności.
    - On-line synchroniczne – odbywają się „na żywo” na platformie do webinarów, wymagane jest uczestnictwo. Podobnie jak w przypadku webinarów, są nagrywane i przechowywane w systemie zewnętrznym. Zaliczane na podstawie obecności.
    - On-line asynchronicznie – zaliczenie na podstawie obejrzenia udostępnionego nagrania (weryfikacja automatyczna).
    - Hybrydowe – łączą podejście on-line i stacjonarne (np. 2 nagrania i 2 dni stacjonarne).

3. **Studia**: długotrwałe (kilkuletnie) formy kształcenia, składające się ze spotkań on-line oraz stacjonarnych (te same uwagi jak w przypadku kursów). Dodatkowo wymagają zaliczenia praktyk, które odbywają się dwa razy do roku. Kończą się egzaminem końcowym.
    - Program studiów (sylabus) musi być znany przed ich rozpoczęciem, a ich tematyka nie może być modyfikowana.
    - Harmonogram spotkań musi być znany przed rozpoczęciem każdego semestru, ale należy uwzględnić możliwość zmian z przyczyn losowych.
    - Wymagane jest uczestnictwo w min. 80% zajęć. Nieobecności można odrabiać pod warunkiem uczestnictwa w zajęciach lub kursie komercyjnym o zbliżonej tematyce.
    - Praktyki trwają 14 dni – wymagana jest tu 100% frekwencja.
    - Podobnie jak w przypadku kursów, spotkania mogą być stacjonarne, on-line lub hybrydowe.
    - Istnieje jednak możliwość zapisania się na spotkania pojedyncze spotkania studyjne bez konieczności udziału w całym studium. Cena dla osoby spoza studium jest inna niż dla stałych słuchaczy.

## Integracja z systemem płatności:

1. System płatności jest dostarczany przez zewnętrzną firmę – należy pominąć jego implementację.
2. Uczestnicy mogą dodawać produkty do koszyka (jeden lub więcej), następnie dla każdego zamówienia generowany jest link do płatności dla użytkownika. W momencie zakończenia płatności integracja przesyła informację zwrotną o statusie (udana/nieudana).
3. Dostęp do webinaru możliwy jest po uprzednim uiszczeniu opłaty (nawet tuż przed rozpoczęciem).
4. Uczestnictwo w kursie wymaga wpłacenia zaliczki przy zapisie, oraz dopłaty całości kwoty najpóźniej 3 dni przed rozpoczęciem kursu. Możliwe jest także opłacenie całości z góry od razu przy zapisie.
5. Uczestnictwo w studium wymaga uiszczenia wpisowego (różne dla poszczególnych studiów) oraz uiszczenia opłaty za dany zjazd najpóźniej trzy dni przed jego rozpoczęciem.
6. Od zasad 3-5 przysługują wyjątki – decyduje każdorazowo Dyrektor Szkoły (np. zgoda na płatność odroczoną dla stałych klientów).

## Raportowanie

System powinien wspierać generowanie często używanych raportów poprzez zdefiniowanie widoków.
1. Raporty finansowe – zestawienie przychodów dla każdego webinaru/kursu/studium.
2. Lista „dłużników” – osoby, które skorzystały z usług, ale nie uiściły opłat.
3. Ogólny raport dotyczący liczby zapisanych osób na przyszłe wydarzenia (z informacją, czy wydarzenie jest stacjonarnie, czy zdalnie).
4. Ogólny raport dotyczący frekwencji na zakończonych już wydarzeniach.
5. Lista obecności dla każdego szkolenia z datą, imieniem, nazwiskiem i informacją czy uczestnik był obecny, czy nie.
6. Raport bilokacji: lista osób, które są zapisane na co najmniej dwa przyszłe szkolenia, które ze sobą kolidują czasowo.

## Pozostałe informacje

1. Wszystkie formy kształcenia są prowadzone przez przypisanego wykładowcę w ustalonym języku (najczęściej jest to język polski).
2. Część form kształcenia jest tłumaczona na żywo na język polski – należy wówczas podać informacje o tłumaczu.
3. Webinary nie posiadają limitu miejsc, podobnie jak kursy on-line. Kursy hybrydowe i stacjonarne posiadają limit miejsc – każdorazowo inny.
4. Studia również posiadają limit miejsc (który może być mniejszy od limitu miejsc spotkań – tzn na niektóre zjazdy można zapisać więcej osób „z zewnątrz”, na inne mniej albo wcale). Limit miejsc na studium nie może być jednak większy niż najmniejszy spośród limitów miejsc poszczególnych spotkań.
5. Na zakończenie każdego kursu oraz studium uczestnik otrzymuje dyplom (o ile był obecny) – należy wysłać go Pocztą Polską na adres korespondencyjny podany w zgłoszeniu.

## Wymagane elementy w projekcie

- Propozycja funkcji realizowanych przez system – wraz z określeniem, który użytkownik jakie funkcje może realizować (krótka lista).
- Projekt bazy danych.
- Zdefiniowanie bazy danych.
- Wygenerowanie danych.
- Zdefiniowanie warunków integralności: wykorzystanie wartości domyślnych, ustawienie dopuszczalnych zakresów wartości, unikalność wartości w polach, czy dane pole może nie zostać wypełnione, złożone warunki integralnościowe.
- Propozycja oraz zdefiniowanie struktury widoków ułatwiających dostęp do danych – widoki powinny prezentować dla użytkowników to, co ich najbardziej interesuje; ponadto powinny zostać zdefiniowane widoki dla różnego typu raportów.
- Propozycja oraz zdefiniowanie operacji na danych (procedury składowane, triggery, funkcje) - powinny zostać zdefiniowane procedury składowane do wprowadzania danych (także do zmian konfiguracyjnych) - należy stworzyć także funkcje zwracające istotne ilościowe informacje; triggery należy wykorzystać do zapewnienia spójności oraz spełnienia przez system specyficznych wymagań klienta.
- Propozycja oraz zdefiniowanie indeksów.
- Propozycja oraz określenie uprawnień do danych - należy zaproponować role oraz ich uprawnienia do operacji, widoków, procedur.

## Sprawozdanie

- Opis funkcji systemu wraz z informacją, co jaki użytkownik może wykonywać w systemie.
- Schemat bazy danych (w postaci diagramu) + opis poszczególnych tabel (nazwy pól, typ danych i znaczenie każdego pola, a także opis warunków integralności, jakie zostały zdefiniowane dla danego pola + kod generujący daną tabelę).
- Spis widoków wraz z kodem, który je tworzy oraz informacją co one przedstawiają.
- Spis procedur składowanych, triggerów, funkcji wraz z ich kodem i informacją co one robią.
- Informacje odnośnie wygenerowanych danych.
- Określenie uprawnień do danych - opis ról wraz z przyporządkowaniem do jakich elementów dana rola powinna mieć uprawnienia.
- Informacja, do jakich pól stworzone są indeksy.

## Implementacja

Projekt powinien zostać zaimplementowany przy użyciu **MS SQL Server**.

## Ocena zadania

Za zadanie można otrzymać 0-10 punktów:
- 4 pkt za schemat bazy danych.
- 1 pkt za warunki integralnościowe.
- 4 pkt za procedury, triggery, widoki.
- 1 pkt - inne (indeksy, uprawnienia...).

Uzyskane punkty przeliczane są na ocenę wg skali obowiązującej w AGH.
