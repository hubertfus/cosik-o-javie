# Java Powtórka

## Opis Języka

Java jest wysokopoziomowym, kompilowanym, obiektowym językiem programowania z silną kontrolą typów. Składnia Javy wzorowana była na językach C/C++, jednak z założeniem zwiększenia bezpieczeństwa poprzez eliminację wskaźników.

## Kluczowe Cechy Javy

1. **Bezpieczeństwo**:
   - Brak wskaźników.

2. **Przenośność**:
   - Niezależność od platformy sprzętowej i programowej.
   - Java generuje kod pośredni (bajtkod), który jest wykonywany przez wirtualną maszynę Javy (JVM).

3. **Niezależność od Platformy**:
   - Programy napisane w Javie mogą być uruchamiane na różnych systemach operacyjnych i komputerach posiadających zainstalowaną JVM.
   - Efekt działania programów jest identyczny na różnych platformach, przy zgodności z JVM.

## Identyfikatory

- Identyfikatory mogą zawierać litery, cyfry oraz znak „_”.
- Java odróżnia małe i wielkie litery, zatem identyfikatory `A` i `a` są różne.
- Identyfikatory mogą zawierać znaki narodowe (np. polskie znaki) dzięki użyciu Unicode.
- Długość identyfikatorów jest nieograniczona.
- Identyfikatory nie mogą być słowami kluczowymi Javy ani literałami `true`, `false` i `null`.

## Komentarze

- **Komentarz wierszowy (jednoliniowy)**: Rozpoczyna się od dwóch ukośników `//`
  ```java
  // Komentarz jednowierszowy
- **Komentarz wielowierszowy (blokowy)**: Zaczyna się od `/*` i kończy `*/`
    ```java
    /* Komentarz
    wielowierszowy
    blokowy */

## Dostęp do Danych

W każdym języku programowania istnieje określony sposób dostępu do danych. W niektórych językach programista musi ciągle kontrolować wykonywane operacje (np. użycie wskaźników w C, C++, C#), co wymaga stosowania specjalnej składni.

### Uproszczony Dostęp do Danych w Javie

W Javie proces dostępu do danych został uproszczony. Wszystko jest obiektem, więc istnieje jeden zwarty zapis używany powszechnie. Programista odwołuje się do obiektów poprzez referencje, a nie bezpośrednio. Można to porównać do telewizora (obiekt) i pilota (referencja). Referencja może istnieć bez obiektu, co oznacza, że może mieć wartość null.

### Przykład Kodowy

```java
    String s; // Utworzenie referencji o nazwie „s” dla typu obiektowego String
    s = new String("tekst"); // Utworzenie nowego obiektu String i przypisanie referencji
    // Lub prościej
    String s = "tekst"; // Bezpośrednie zainicjowanie obiektu String
```

### Inicjalizacja Obiektów
Inne typy obiektowe inicjalizowane są za pomocą słowa kluczowego `new`.

```java
    MyClass obj = new MyClass();
```
## Typy Pamięci

### Rejestry

- **Rejestry**: Najszybciej dostępna pamięć, wewnątrz procesora.
  - Liczba rejestrów jest bardzo ograniczona.
  - Java nie ma kontroli nad rejestrami.

### Stos

- **Stos**: Wydzielony fragment pamięci RAM, obsługiwany przez procesor.
  - Szybki mechanizm przydzielania pamięci.
  - Kompilator musi znać rozmiar i okres życia zmiennych.
  - Referencje do obiektów przechowywane są na stosie.

### Sterta

- **Sterta**: Fragment pamięci ogólnego zastosowania w RAM.
  - Przechowuje obiekty.
  - Kompilator nie musi znać rozmiaru ani okresu życia obiektów.
  - Umożliwia elastyczne zarządzanie pamięcią, choć jest wolniejsza od stosu.

### Obszar Stałych

- **Obszar stałych**: Przechowuje wartości stałe umieszczane bezpośrednio w kodzie.
  - Stałe są zabezpieczone przed zmianami.
  - Mogą być umieszczane w pamięci tylko do odczytu (ROM).

### Obszar Spoza RAM

- **Obszar spoza RAM**: Dane, które istnieją również poza uruchomionym programem, np. w plikach lub bazach danych.

# Typy w Języku Java

## Typy Proste (Pierwotne)

Typy zdefiniowane w języku Java, leżące u podstaw każdego programu:
- **Typy liczbowe**
- **Typy logiczne**
- **Typy znakowe**
- **Typ pusty**

## Typy Referencyjne

Wskazują na miejsce przechowywania obiektów w pamięci (na stercie) lub mają wartość null. Dzielą się na następujące kategorie:
- **Typy klas**
- **Typy interfejsów**
- **Typy tablic**

### Wartości Typów Referencyjnych

Wartościami typów referencyjnych są referencje (w pewnym uproszczeniu można o nich myśleć jako o wskaźnikach) do obiektów. Domyślnie mają one wartość null. Istnieje także typ o pustej nazwie, będący typem wyrażenia null. Ponieważ nie ma on nazwy, nie można zadeklarować zmiennej tego typu. Wartość null można rzutować na dowolny typ referencyjny, co oznacza, że wartość null może reprezentować każdy typ referencyjny.

## Zmienne

Zmienne można kojarzyć z nazwanymi pojemnikami, w których gromadzi się pojedyncze wartości określonego typu (typu zmiennej). Dzielą się one na:

### Zmienne Proste (Podstawowe)

Przechowują wartości swoich typów, np. 10, 20.5, true, 'A'.

### Zmienne Typu Referencyjnego

Przechowują referencje do obiektów (wskazują na adres w pamięci, pod jakim znajduje się obiekt). Jeśli nie wskazują obiektu, to mają wartość null.

### Rodzaje Zmiennych

W języku Java wyróżnia się siedem rodzajów zmiennych:
 
1. **Zmienne klasowe**: Zmienne zdefiniowane wewnątrz klasy z użyciem słowa kluczowego `static`. Są współdzielone przez wszystkie instancje klasy.

2. **Zmienne egzemplarzowe**: Zmienne zdefiniowane wewnątrz klasy, ale poza metodami. Każda instancja klasy ma własną kopię tych zmiennych.

3. **Zmienne lokalne**: Zmienne zdefiniowane wewnątrz metod, konstruktorów lub bloków kodu. Są dostępne tylko w obrębie tych metod, konstruktorów lub bloków.
4. **Elementy tablic**: Anonimowe zmienne przechowywane w strukturze tablicowej. Każdy element tablicy jest zmienną.
5. **Parametry metod**: Zmienne zadeklarowane w nagłówku metody, służące do przekazywania wartości do metod.
6. **Parametry konstruktorów**: Zmienne zadeklarowane w nagłówku konstruktora, służące do przekazywania wartości do konstruktorów.
7. **Parametry obsługi wyjątków**: Zmienne używane w blokach `catch` do przechwytywania wyjątków zgłaszanych w blokach `try`.

# Deklaracja i Inicjalizacja Zmiennych w Javie

Każda utworzona w programie zmienna musi być zadeklarowana. Podczas deklaracji podawany jest typ danych, który wiąże się z deklarowaną zmienną. Określenie typu zmiennej pozwala kompilatorowi na weryfikowanie poprawności operacji dokonywanych na zmiennych.

## Silne Typowanie

Java jest językiem silnie typowanym. Jeżeli kompilator wykryje, że w programie użyto zmiennej niezgodnej z jej typem, to wyrzuci on błąd i nie pozwoli skompilować takiego kodu. Sprawdzanie zgodności typów zmiennych jest ważną i użyteczną cechą Javy, pozwalającą na wykrywanie błędów już na etapie kompilacji. Dotyczy to jednak błędów składniowych, ponieważ błędów semantycznych, które mogą pojawić się w trakcie wykonywania programu, kompilator wychwycić nie może.

## Inicjalizacja Zmiennych

Każda zmienna w języku Java musi zostać przed pierwszym użyciem zainicjowana – jest to wymuszane przez kompilator. 

- **Parametry metod** są inicjowane wartościami podanymi przy wywołaniu metody.
- **Zmienne klasowe**, **zmienne egzemplarzowe** i **elementy tablic** są inicjowane automatycznie wartościami domyślnymi.
- **Zmienne lokalne** muszą być jawnie zainicjowane przez programistę.

## Zasięg i Czas Życia Zmiennych

W większości języków programowania obowiązuje pojęcie zasięgu zmiennych (ang. scope), które obejmuje zarówno widoczność zmiennych, jak i ich czas (okres) życia.

### Zasięg w Javie

W językach C, C++ oraz Java zasięg zmiennych definiuje się poprzez użycie nawiasów klamrowych `{}`. Zmienna zdefiniowana w pewnym bloku operacji jest widoczna i istnieje tylko w tym bloku.

- **Parametry metod** są widoczne w całej metodzie i żyją przez cały okres wykonywania się metody.
- **Zmienne lokalne** inicjowane w blokach wewnątrz metody istnieją i są widoczne w obrębie tych bloków.

## Czas Życia Obiektów

Czas życia obiektów w Javie różni się od czasu życia zmiennych typów prostych (podstawowych). Obiekt utworzony przy użyciu operatora `new` istnieje również poza swoim zasięgiem. Poza zasięgiem przepada tylko referencja do obiektu, natomiast sam obiekt wciąż zajmuje pamięć.

### Problem Zarządzania Pamięcią w C++

W języku C++ programista był zobligowany do niszczenia obiektów w odpowiednim momencie przy użyciu destruktorów. To podejście, choć elastyczne, było bardzo niebezpieczne, gdyż mogło prowadzić do wycieków pamięci. Przykładowo, obiekty utworzone w metodach mogły pozostać w pamięci, jeśli nie były poprawnie zniszczone, co mogło prowadzić do wyczerpania pamięci.

### Garbage Collector w Javie

W Javie problem wycieków pamięci został rozwiązany za pomocą mechanizmu zwanego **Garbage Collector**. 

- **Garbage Collector** sprawdza wszystkie obiekty na stercie utworzone przez operator `new` i wykrywa te, do których nie ma aktualnej referencji.
- Następnie zwalnia pamięć przydzieloną dla tych obiektów, co umożliwia przydzielenie tej pamięci innym obiektom.

Dzięki Garbage Collector, programista nie musi martwić się o zwalnianie pamięci – maszyna wirtualna zrobi to za niego, chroniąc przed wyciekami pamięci.

# Bezpieczeństwo Tablic w Javie

Tablice występują praktycznie we wszystkich językach programowania, jednak nie wszędzie ich używanie jest bezpieczne. Przykładowo, w językach C czy C++ tablice są jedynie obszarami pamięci, co może prowadzić do błędów takich jak wykraczanie poza ich zakres lub odwoływanie się do niezainicjowanej tablicy, co skutkuje nieprzewidzianymi wynikami.

W Javie, będącej językiem bezpiecznym, większość z tych problemów nie występuje. Java wymusza inicjalizację tablicy przed jej użyciem i nie pozwala na wykroczenie poza jej granice, zatrzymując program i zgłaszając odpowiedni wyjątek w razie potrzeby.

Podczas tworzenia tablicy obiektów tworzona jest tablica referencji do nich, gdzie każda komórka tablicy jest automatycznie ustawiana na wartość `null`. Przed odwołaniem się do elementu tablicy, należy przypisać do niego jakiś obiekt. Odwołanie się do pustych referencji podczas działania programu powoduje wyrzucenie odpowiedniego wyjątku. Dla typów prostych kompilator zapewnia inicjalizację poprzez wyzerowanie obszaru przydzielonego dla tablicy.

# Instrukcje Przerywania i Kontynuacji Pętli

## Instrukcja `break`

Instrukcja `break` służy do natychmiastowego przerwania wykonania pętli lub ciągu instrukcji w instrukcji wyboru `switch`. Wykonanie instrukcji `break` powoduje skok do pierwszej napotkanej instrukcji znajdującej się za przerwaną pętlą lub instrukcją wyboru.

## Instrukcja `continue`

Instrukcja `continue` może być użyta wewnątrz pętli i służy do przerwania wykonania danej iteracji pętli. Przerywane jest w tym przypadku tylko wykonanie bieżącej iteracji, a nie całej pętli, jak to ma miejsce w przypadku `break`.

W przypadku umieszczenia instrukcji `break` lub `continue` w pętli zagnieżdżonej w innej pętli, mają one skutek tylko dla pętli, w której bezpośrednio się znajdują. Możliwe jest wskazanie poprzez etykietę pętli bardziej zewnętrznej.

# Definiowanie Klasy

Zdefiniowanie nowej klasy wprowadza do programu nowy typ danych, który pozostaje do dyspozycji programisty przy budowie programu. W Javie można definiować klasy na najwyższym poziomie zagnieżdżeń struktury programu oraz jako klasy zagnieżdżone, czyli takie, których definicja jest zawarta w innej klasie lub interfejsie.

Podczas tego wykładu omawiane będą jedynie klasy niezagnieżdżone, jednak większość z tych informacji odnosi się do wszystkich rodzajów klas. Typy wyliczeniowe, które w języku Java również ujmowane są w klasy, nie będą omawiane.

## Składowe Klasy

W języku Java wyróżnia się trzy składowe klasy: pola (atrybuty), metody i konstruktory. Wszystkie składowe klasy mogą być opatrzone odpowiednimi modyfikatorami widoczności.

### Pola Klasy

Pola klasy stanowią strukturę danych przechowywaną przez klasę. Są to zmienne globalne w obrębie danej klasy, mogące być zarówno zmiennymi podstawowymi, jak i obiektowymi. Deklaracja pola klasy składa się z określenia jego typu, nazwy i nieobligatoryjnej części inicjującej, zakończonej średnikiem.

### Metody

Metody to funkcje zdefiniowane wewnątrz klasy, przypominające zwykłe funkcje w języku C czy C++. Poprzez metody definiuje się interfejs klasy, który określa, co klasa lub obiekt zbudowany na jej bazie może wykonać. Metody mogą służyć do określania dostępu do pól klasy, ich odczytywania lub modyfikacji wartości oraz do prowadzenia obliczeń. 

Deklaracja metody rozpoczyna się od określenia typu zwracanego wyniku (lub słowa kluczowego `void`, jeśli nie zwraca ona wartości), następnie podawana jest nazwa metody, a kolejnym elementem jest lista parametrów formalnych otoczona nawiasami okrągłymi. Ostatnim elementem jest ciało metody, stanowiące blok kodu ujęty w klamry. Wynik działania metody musi być zgodny z założonym typem i może zależeć od parametrów metody.

# Konstruktor w Javie

Konstruktor jest specjalnym typem metody, którego zadaniem jest tworzenie nowych obiektów swojej klasy. Konstruktor wyróżnia się dwoma cechami:
1. Nazwa konstruktora musi być taka sama jak nazwa klasy, w której go zadeklarowano.
2. Konstruktor nie zwraca wartości, nawet typu `void`.

## Właściwości Konstruktora

- **Inicjalizacja Obiektów:** Specyfikacja Javy wymaga wywołania konstruktora zawsze, gdy tworzony jest obiekt, co gwarantuje, że każdy obiekt zostanie zainicjowany w sposób określony przez programistę.
- **Ustawianie Pól Obiektu:** Najczęściej w konstruktorze ustawiane są wartości pól obiektu oraz wywoływane metody danej klasy i klasy bazowej.
- **Wywoływanie Konstruktora Klasy Bazowej:** Dla konstruktorów z parametrami możliwe jest wywołanie konstruktorów klas bazowych.

## Domyślny Konstruktor

- **Automatyczne Tworzenie:** Jeśli programista nie zdefiniuje konstruktora, kompilator automatycznie tworzy konstruktor domyślny (bezargumentowy), który nie inicjalizuje żadnych pól obiektu.

## Słowo Kluczowe `this`

- **Referencja do Obiektu:** `this` odnosi się do obiektu, na rzecz którego wywołana jest metoda lub konstruktor.
- **Rozróżnianie Pól i Parametrów:** Użycie `this` jest wymagane, gdy nazwa parametru metody lub konstruktora pokrywa się z nazwą pola klasy.
- **Odwoływanie się do Metod i Konstruktorów:** `this` może być używane do odwoływania się do metod i konstruktorów klasy. Jest to przydatne przy tworzeniu przeciążonych form konstruktorów.
- **Ograniczenie Użycia:** `this` może być stosowane tylko wewnątrz niestatycznej metody.

## Przeciążanie Konstruktorów

- **Definiowanie Wielu Konstruktorów:** Przeciążanie pozwala na definiowanie dwóch lub więcej konstruktorów z tą samą nazwą, ale różnymi argumentami.
- **Wymagania:** Każda przeciążona metoda (konstruktor) musi mieć unikatową listę typów argumentów, różniącą się liczbą, typem lub kolejnością argumentów.

# Pakiety w Javie

Pakiet jest jednostką biblioteczną, grupą klas zebranych we wspólnej przestrzeni nazw. Przykładem jest biblioteka narzędziowa java.util, zawierająca klasę `Scanner`.

## Modyfikatory Dostępu

Podczas deklaracji klas oraz ich składowych można używać modyfikatorów dostępu, które określają, gdzie dana składowa klasy może być użyta. Dostępne modyfikatory to:

- **public:** Umożliwia dostęp bez ograniczeń, dla wszystkich klas występujących w pakiecie i poza nim.
- **protected:** Pozwala na dostęp z pakietu, w którym zdefiniowano klasę zawierającą składową, oraz z podklas tej klasy, nawet gdy są one zdefiniowane w innym pakiecie.
- **private:** Oznacza, że do składowej takiej nie ma dostępu nikt poza jego własną klasą z wnętrza jej metod.
- **brak modyfikatora (domyślny):** Pozwala na dostęp do składowych klasy w obrębie pakietu, w którym osadzona jest klasa.

## Niuanse Modyfikatorów Dostępu

- **Dostęp Chroniony:** Modyfikator protected zezwala na dostęp w podklasach oraz w obrębie całego pakietu.
- **Dostęp Prywatny:** Modyfikator private pozwala na dostęp w całej klasie zadeklarowanej na najwyższym poziomie.
- **Dotyczy Klas, nie Obiektów:** Modyfikatory dostępu dotyczą klas, a nie obiektów.

## Przemyślenia dotyczące Widoczności

- **Chronienie Struktury Danych:** Zazwyczaj chroniona jest struktura danych obiektu, czyli jego pola (atrybuty) – są one poprzedzane modyfikatorami private lub protected.
- **Publiczne Metody i Konstruktory:** Metody i konstruktory najczęściej deklarowane są jako publiczne.
- **Metody Używane Wewnątrz Klasy:** Metody używane wewnątrz danej klasy lub hierarchii są definiowane jako prywatne bądź chronione.

# Hermetyzacja (Enkapsulacja) w Javie

Hermetyzacja jest techniką programistyczną używaną w Javie do ukrywania struktury wewnętrznej klasy poprzez ograniczenie dostępu do pól klasy oraz kontrolowanie ich stanu za pomocą publicznych metod.

## Problemy z Bezpośrednim Dostępem do Pól

Bezpośredni dostęp do pól klasy może prowadzić do niekontrolowanego ustawiania niepoprawnych wartości, co może prowadzić do błędów w programie. Na przykład, programista może ustawić wartość pól na null lub na wartość nieprawidłową, co nie jest zamierzone w kontekście projektu.

## Rozwiązanie: Hermetyzacja

Aby uniknąć powyższych problemów, stosuje się hermetyzację, czyli enkapsulację danych. Polega ona na:
- Oznaczeniu pól klasy jako private lub protected, aby uniemożliwić bezpośredni dostęp do nich z zewnątrz klasy.
- Udostępnieniu publicznych metod (getterów i setterów) do odczytu (get) i zapisu (set) wartości pól klasy.

## Korzyści Hermetyzacji

- **Bezpieczeństwo Danych:** Dzięki hermetyzacji wartości pól klasy są kontrolowane przez metody, co zapobiega nieprawidłowym operacjom na danych.
- **Ukrycie Implementacji:** Hermetyzacja ukrywa implementację klasy, co ułatwia utrzymanie i modyfikację kodu bez wpływu na zewnętrzne części programu.
- **Łatwiejsze Użycie i Rozwój:** Poprzez publiczne metody dostępu do pól klasy można kontrolować jakie operacje mogą być wykonane na danych.

## Przykład Użycia Getterów i Setterów

```java
public class Person {
    private String firstName;
    private String lastName;
    private int age;

    // Getter dla firstName
    public String getFirstName() {
        return firstName;
    }

    // Setter dla firstName
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    // Getter dla lastName
    public String getLastName() {
        return lastName;
    }

    // Setter dla lastName
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    // Getter dla age
    public int getAge() {
        return age;
    }

    // Setter dla age
    public void setAge(int age) {
        if (age >= 0) {
            this.age = age;
        } else {
            throw new IllegalArgumentException("Wiek nie może być ujemny");
        }
    }
}
```

## Hermetyzacja (Enkapsulacja) w Javie

Hermetyzacja jest techniką programistyczną używaną w Javie do kontrolowania dostępu do pól klasy oraz zapewnienia bezpieczeństwa i niezawodności aplikacji poprzez zastosowanie zasad poprawnego korzystania z danych.

W powyższym przykładzie pola `firstName`, `lastName` i `age` są prywatne, a dostęp do nich odbywa się za pomocą publicznych metod `get` i `set`. Metoda `setAge` zawiera dodatkową walidację, aby zapobiec ustawieniu ujemnej wartości dla wieku.

Hermetyzacja pozwala uniknąć bezpośredniego manipulowania polami obiektów, co może prowadzić do nieprzewidywalnych stanów danych. Zamiast tego, dane są kontrolowane i manipulowane tylko za pomocą odpowiednich metod, co zwiększa spójność i bezpieczeństwo kodu.

# Dziedziczenie i Klasy Abstrakcyjne w Javie

Dwa podstawowe mechanizmy, które umożliwiają tworzenie nowych klas na bazie istniejących, to dziedziczenie i kompozycja.

## Dziedziczenie

Dziedziczenie jest mechanizmem w Javie, który umożliwia tworzenie nowych klas (klas potomnych) na podstawie już istniejących klas (klas bazowych). Klasy potomne dziedziczą atrybuty (pola) oraz metody z klasy bazowej. W Javie używa się słowa kluczowego `extends`, aby określić, że nowa klasa rozszerza (dziedziczy po) innej klasie.

### Charakterystyka dziedziczenia:
- Mechanizm generalizacji ↔ specjalizacji.
- Oznaczenie w języku UML: niezapełniony trójkąt.
- Klasy w Javie domyślnie dziedziczą po klasie `Object`, chyba że explicite określimy inną klasę bazową.

## Klasy Abstrakcyjne

Klasa abstrakcyjna w Javie jest klasą, która nie może być bezpośrednio instancjonowana, ale może zawierać metody abstrakcyjne (bez ciała), które muszą być zaimplementowane w klasach dziedziczących. Służą one do tworzenia wspólnego interfejsu dla klas potomnych.

### Charakterystyka klas abstrakcyjnych:
- Oznaczenie w języku UML: zapełniony rąbek.
- Metody abstrakcyjne nie posiadają implementacji i są poprzedzone słowem kluczowym `abstract`.
- Klasy abstrakcyjne mogą zawierać zarówno metody abstrakcyjne, jak i zwykłe metody z implementacją.
- Aby klasa była abstrakcyjna, musi zawierać co najmniej jedną metodę abstrakcyjną.
- Klasa abstrakcyjna nie może być bezpośrednio instancjonowana, a próba tego skutkuje błędem kompilacji.

### Dziedziczenie w kontekście klas abstrakcyjnych:
- Klasy abstrakcyjne mogą dziedziczyć po innych klasach abstrakcyjnych lub konkretnych.
- Klasa dziedzicząca po klasie abstrakcyjnej musi zaimplementować wszystkie odziedziczone metody abstrakcyjne, aby przestać być sama klasą abstrakcyjną.

Dziedziczenie i klasy abstrakcyjne stanowią podstawowe narzędzia w programowaniu obiektowym w Javie, umożliwiające tworzenie hierarchii klas i zachowanie spójności oraz przejrzystości kodu.
# Interfejsy w Javie

Interfejsy w Javie stanowią zaawansowany mechanizm umożliwiający definiowanie abstrakcyjnych klas bazowych, które są pozbawione implementacji. Interfejsy są używane do określania zestawu metod, które powinny być zaimplementowane przez klasy implementujące dany interfejs.

## Charakterystyka interfejsów:

- Interfejs definiuje jedynie nazwy metod, listy argumentów oraz typy zwracane.
- Metody zawarte w interfejsie są zawsze abstrakcyjne (bez ciała) i nie używa się w nich słowa kluczowego `abstract`.
- Może zawierać pola, które są automatycznie traktowane jako `static final`.
- Interfejs nie może zawierać metod z implementacją.
- Aby utworzyć interfejs w Javie, używa się słowa kluczowego `interface` zamiast `class`.

## Implementacja interfejsów:

- Klasa implementująca interfejs używa słowa kluczowego `implements`.
- Jedna klasa może implementować wiele interfejsów jednocześnie.
- Implementując interfejs, klasa zobowiązana jest dostarczyć ciała dla wszystkich metod zadeklarowanych w interfejsie.
- Dziedziczenie po interfejsach umożliwia klasie implementowanie wielu różnych zachowań, co jest namiastką dziedziczenia wielobazowego.

## Porównanie interfejsów z klasami abstrakcyjnymi:

- Klasa abstrakcyjna może zawierać metody abstrakcyjne oraz metody z implementacją, podczas gdy interfejsy zawierają wyłącznie metody abstrakcyjne.
- Klasa abstrakcyjna może zawierać pola, które nie są statyczne, w przeciwieństwie do pól w interfejsach.
- Interfejsy nie mogą być instancjonowane, co oznacza, że nie można utworzyć obiektu na bazie samego interfejsu.

## Dziedziczenie i interfejsy:

- Klasa może dziedziczyć po jednej klasie bazowej za pomocą `extends`, natomiast implementować wiele interfejsów za pomocą `implements`.
- Klasa dziedzicząca po klasie abstrakcyjnej musi implementować wszystkie jej abstrakcyjne metody, aby stać się klasą konkretną.

Interfejsy w Javie stanowią potężne narzędzie do tworzenia modularnych i elastycznych aplikacji, umożliwiając definiowanie wspólnych zachowań dla różnych klas. Ich używanie pomaga w unikaniu nadmiernego związania (coupling) pomiędzy klasami oraz wspiera zasadę programowania przez interfejsy (interface-driven programming).

# Składowe statyczne w Javie

Składowe statyczne w języku Java różnią się od składowych dynamicznych tym, że są powiązane z samą klasą, a nie z konkretnymi obiektami tej klasy. Oznacza to, że ich wartość jest wspólna dla wszystkich obiektów tej klasy.

## Rodzaje składowych statycznych:

1. **Statyczne pola:**
   - Deklarowane za pomocą słowa kluczowego `static`.
   - Wszystkie obiekty klasy mają dostęp do tego samego egzemplarza pola statycznego.
   - Pola statyczne mogą być również oznaczone jako `final`, co oznacza, że są to stałe klasy.

2. **Statyczne metody:**
   - Metody zadeklarowane jako `static`.
   - Metody statyczne mogą być wywoływane bez tworzenia instancji klasy.
   - Z metod statycznych można odwoływać się jedynie do innych metod statycznych oraz do statycznych pól klasy.

3. **Statyczne inicjalizatory:**
   - Bloki kodu używane do inicjalizacji statycznych pól klasy.
   - Wykonywane są tylko raz, przy pierwszym użyciu klasy (np. przy tworzeniu pierwszego obiektu lub odwołaniu się do składowej statycznej).

## Szczegóły dotyczące składowych statycznych:

- Zmienne statyczne i metody mogą być deklarowane na poziomie klasy.
- Nie można deklarować zmiennych statycznych lokalnych, nawet w metodach statycznych.
- Wewnątrz metod statycznych nie można używać pól instancji ani wywoływać metod instancji.

Składowe statyczne pozwalają na definiowanie właściwości i zachowań, które są wspólne dla wszystkich instancji danej klasy oraz dostępne bez potrzeby tworzenia obiektu tej klasy.

# Wyjątki w języku Java

Wyjątki w programowaniu to sytuacje nienormalne, które mogą wystąpić podczas działania aplikacji. Mogą pojawić się nawet w poprawnie napisanych programach, dlatego programiści muszą brać pod uwagę możliwość ich wystąpienia i odpowiednio na nie reagować.

## Definicja i istota wyjątków

- **Wyjątek** to obiekt, który jest tworzony w momencie wystąpienia nieprawidłowości w aplikacji.
- Nieprawidłowości mogą wynikać z różnych sytuacji, takich jak brak miejsca na dysku podczas zapisu pliku czy zerwanie połączenia podczas transmisji danych.
- W języku Java wyjątki są zgłaszane poprzez instrukcję `throw` lub `raise`.

## Mechanizmy obsługi wyjątków

- Gdy wyjątek zostaje zgłoszony, program przechodzi do szukania obsługi dla tego wyjątku.
- Wyjątki mogą być obsługiwane przez bloki `try-catch` lub przekazywane wyżej w stosie wywołań (`throws`).
- Jeśli nie ma obsługi dla wyjątku, program zostanie przerwany.

## Ewolucja obsługi błędów

- W starszych językach programowania, zamiast mechanizmów obsługi wyjątków, stosowano konwencje zwracania specjalnych wyników oznaczających błędy.
- Brak skutecznej obsługi błędów ograniczał możliwości tworzenia złożonych i solidnych aplikacji.

## Korzyści z mechanizmów obsługi wyjątków

- Nowoczesne języki programowania, takie jak Java, umożliwiają skuteczną obsługę sytuacji wyjątkowych.
- Dzięki mechanizmom wyjątków możliwe jest szybkie reagowanie na problemy i unikanie poważniejszych błędów w działaniu aplikacji.

Wyjątki w języku Java są kluczowym narzędziem do tworzenia bezpiecznych i niezawodnych aplikacji, które potrafią odpowiednio reagować na nieprzewidziane sytuacje.

# Rzucanie wyjątków i ich obsługa

## Rzucanie wyjątku

Rzucanie wyjątków jest sposobem na reakcję na sytuacje wyjątkowe podczas działania aplikacji. Możemy użyć tego mechanizmu, aby przerwać działanie aktualnego kontekstu i przekazać informacje o błędzie do wyższego poziomu w aplikacji.

```java
if (obj == null)
    throw new NullPointerException();
```

## Rzucanie wyjątków

Jeśli warunek powyżej jest spełniony, rzucany jest wyjątek NullPointerException. Rzucenie wyjątku oznacza, że programista jest zwolniony z jego natychmiastowej obsługi, a obsługa błędu musi być realizowana gdzie indziej, w szerszym kontekście aplikacji.

## Wyjątki a transakcje

Działanie wyjątków można porównać do transakcji w bazach danych. W obu przypadkach, gdy coś pójdzie nie tak (np. wyjątek lub błąd w transakcji), można cofnąć lub unieważnić dotychczasowe operacje. Wyjątki pozwalają na kontrolowane wycofywanie się z operacji, które nie mogą być dokończone.
## Deklaracja i kontrola wyjątków

Przed wywołaniem metody, która może rzucić wyjątek, deklaruje się możliwe do wystąpienia wyjątki za pomocą klauzuli `throws`. Jest to wymuszone przez kompilator, aby programista świadomie zarządzał potencjalnymi wyjątkami.

```java
public void metoda() throws IOException, SQLException {
    // kod, który może rzucić IOException lub SQLException
}
```
Klauzula `throws` informuje o możliwych wyjątkach, które mogą być rzucane przez daną metodę. Programista musi je obsłużyć lub przekazać do wyższego poziomu aplikacji.

## Przechwytywanie wyjątków - blok `try`

Aby kontrolować, jak program reaguje na wyjątki, stosuje się blok `try`, który obejmuje kod, w którym może wystąpić wyjątek. Blok `try` jest następnie poprzedzony jednym lub więcej blokami `catch`, które obsługują konkretny typ wyjątku.

```java
try {
    // kod, który może rzucić wyjątek
} catch (Exception e) {
    // obsługa wyjątku
}
```

Zastosowanie bloków `try` i `catch` umożliwia grupowanie i jednoczesne zarządzanie obsługą wyjątków w jednym miejscu, co zwiększa czytelność i skalowalność kodu.

Wyjątki w języku Java są kluczowym elementem zapewniającym bezpieczeństwo i niezawodność aplikacji poprzez kontrolowane reagowanie na nieprzewidziane sytuacje.

# Obsługa wyjątków – blok `catch`

Każdy wyrzucony wyjątek musi mieć swoje miejsce obsługi! Zatem dla każdego wyjątku, który programista chce obsłużyć, musi istnieć osobna procedura obsługi. Te procedury obsługi występują w kodzie bezpośrednio po bloku `try` i oznaczone są słowami kluczowymi `catch`.

## Hierarchia wyjątków w języku Java

W obiekcie, który jest wyjątkiem, zawrzeć można różne dodatkowe informacje, które mogą być pomocne przy podejmowaniu odpowiednich działań naprawczych. Najczęściej stosuje się jednak wyjątki, które są egzemplarzami różnych klas i dla każdego egzemplarza stosuje się oddzielny blok `catch`.

W języku Java zdefiniowano bardzo wiele wyjątków, najważniejsze z nich zawarto w pakiecie `java.lang`. Wyjątki te używane są przez klasy pakietów standardowych. Różnią się one zasadniczo jedynie nazwą, która pozwala na ich rozróżnianie. Programiści mogą używać standardowych klas wyjątków lub tworzyć nowe, własne, które pasują do konkretnego zastosowania.

Wszystkie klasy wyjątków muszą dziedziczyć po klasie `Throwable`. Jednak podczas tworzenia nowych wyjątków nie rozszerza się bezpośrednio tej klasy, ale klasy pochodzące od niej.

Wyjątki, które dziedziczą po klasie `Error`, stanowią bardzo poważne błędy, których ani aplikacja ani podjęte w niej środki naprawcze nie będą w stanie naprawić. Dobrym przykładem może tutaj być klasa wyjątków `VirtualMachineError`. Pojawienie się takiego wyjątku stanowi informację, iż maszyna wirtualna Javy nie jest w stanie dalej kontynuować pracy. Przyczyną takiego stanu rzeczy może być np. wyczerpanie wymaganych przez aplikację zasobów systemowych. Inną wartą uwagi podklasą klasy `Error` jest `AssertionError`. Wyjątek taki zostaje wyrzucony jeśli niezmiennik (określany w Javie jako asercja), umieszczony w kodzie przez twórcę aplikacji, okazuje się nieprawdziwy po jego wyliczeniu.

Należy pamiętać, że wyjątki dziedziczące po klasie `Error` nie mogą być obsłużone, nie ma sensu ich zatem nawet przechwytywać. Mogą się one pojawić praktycznie w każdej linii kodu. Nie ma zatem potrzeby wyliczać ich przy użyciu klauzuli `throws`.

Wyjątki, które dziedziczą po klasie `Exception`, dotyczą sytuacji wyjątkowych, na które poprawnie wykonany program powinien być przygotowany. To właśnie klasę `Exception` rozszerza programista podczas tworzenia własnych wyjątków. Poniżej przedstawiono kilka przykładów rozszerzenia klasy `Exception`:
- `IOException` – dotyczy sytuacji wyjątkowych związanych z wejściem i wyjściem. Często używa się tego typu wyjątków przy pracy z plikami.
- `ClassNotFoundException` – wskazuje, że maszyna wirtualna nie odnalazła danej klasy.
- `SQLException` – dotyczy obsługi wyjątków pojawiających się podczas interakcji z bazami danych.
- `SAXParseException` – informuje, że wystąpił błąd podczas procesu parsowania pliku XML.

Wartą uwagi podklasą klasy `Exception` jest klasa `RuntimeException`. Nie posiada ona zbyt wiele klas pochodnych. Wyjątki klas dziedziczących po `RuntimeException` pojawiają się podczas wykonywania typowych operacji, takich jak odwoływanie się do niewłaściwego elementu tablicy, wykroczenie poza zakres tablicy, odwołanie się do składowych obiektu, który nie istnieje, niewłaściwe rzutowanie zmiennej, itp. Pojawienie się tego typu wyjątków najczęściej wskazuje na błędy popełnione przez programistę podczas tworzenia kodu lub niewłaściwe wykorzystanie kodu utworzonego przez inne osoby.

Tego typu błędów nie da się przeważnie wykryć w procesie kompilacji i zostają one zidentyfikowane przez maszynę wirtualną dopiero w trakcie działania aplikacji.

Poniżej przedstawiono przykłady takich wyjątków:
- `ClassCastException` – informuje o próbie rzutowania zmiennej na niewłaściwy typ.
- `IndexOutOfBoundsException` – informuje, że odwołano się do indeksu spoza zakresu danej kolekcji.
- `NullPointerException` – informuje, że zamiast referencji wskazującej na obiekt pojawiła się wartość `null`.

Kolejność obsługi wyjątków, czyli kolejność występowania bloków `catch`, jest ważna. Zasada jest taka, że wyjątki podklasy muszą występować przed wyjątkami nadklasy. Jest to zresztą logiczne – im klasa bardziej ogólna, tym może wyłapać więcej wyjątków. W utrzymaniu odpowiedniej kolejności występowania pomaga kompilator, który nie pozwoli skompilować programu, jeśli bloki `catch` są niewłaściwie ustawione.

Blok `catch`, który obsługuje wyjątki `Exception`, powinien być wstawiony na samym końcu programu. Jeśli programista nie przewidzi wystąpienia jakiegoś wyjątku i nie obsłuży go w odpowiednim bloku `catch`, taki wyjątek zostanie wyłapany przez ostatni blok `catch`, który obsługuje dowolne, obsługiwane wyjątki.

# Tworzenie i obsługa wyjątków w Javie

Programista Javy nie jest zmuszony do używania tylko i wyłącznie wyjątków istniejących w Javie. Hierarchia wyjątków w Javie nie jest w stanie przewidzieć wszystkich sytuacji nienormalnych, które programista chce obsłużyć. Dlatego istnieje możliwość tworzenia własnych, odpowiednio wyspecyfikowanych wyjątków.

## Tworzenie własnych wyjątków

Utworzenie własnej klasy wyjątków polega na dziedziczeniu po istniejącym typie wyjątków, który jest najbardziej zbliżony do tworzonego wyjątku (choć nie zawsze jest to możliwe). Najprostszą drogą jest stworzenie domyślnego konstruktora, co wymaga niewiele kodu.

## Blok finally

Często zdarzają się sytuacje, w których chcielibyśmy wykonać pewne działania niezależnie od tego, czy w bloku `try` wystąpił jakiś wyjątek, czy też nie. Do takich operacji zalicza się np. zakończenie połączenia z bazą danych, zakończenie transmisji sieciowej, zwolnienie portów (gniazd), zamknięcie otwartego pliku, czy zakończenie połączenia z urządzeniem peryferyjnym.

Aby zagwarantować niezawodność takich operacji, umieszcza się je w bloku `finally`, który jest umieszczony na końcu za blokami `catch`. Blok `finally` różni się od bloku `catch` tym, że zawarte w nim operacje na pewno się wykonają, niezależnie od tego, ile wyjątków zdarzyło się po drodze w bloku `try`.

W języku Java, który nie posiada destruktorów (w których wykonywałyby się takie operacje), rola bloku `finally` nabiera szczególnego znaczenia.

## Metody pomocnicze

Metoda `printStackTrace()`, zawarta w każdym obiekcie wyjątku, pozwala na wyświetlenie rozwinięcia stosu wywołań. Informacje te można uzyskać również poprzez użycie metody `getStackTrace()`, która zwraca tablicę elementów stosu wywołań, gdzie każdy element reprezentuje pojedynczą ramkę stosu. Zerowy element tablicy to szczyt stosu, czyli ostatnie wywołanie metody, w którym doszło do utworzenia obiektu `Throwable` i wyrzucenia wyjątku. Ostatni element stosu wywołań jest pierwszym wywołaniem metody w sekwencji wywołań.


# przentacja kozioła o kolekcjach
```
https://urstudrzeszow.sharepoint.com/sites/Programowanieobiektowewykady-materiay/Materiay%20z%20zaj/PO1%20wyk%C5%82ad/wyk%C5%82ad%206%20-%20Kolekcje.pdf?wdsle=0&CT=1719480687548&OR=ItemsView&wdOrigin=TEAMSFILE.FILEBROWSER.DOCUMENTLIBRARY
```

# Typy generyczne w językach programowania obiektowego

Paradygmat obiektowy umożliwia łatwe opisywanie obiektów świata rzeczywistego oraz tworzenie abstrakcji. Pojęcie klasy pozwala na tworzenie abstrakcji, a dziedziczenie umożliwia tworzenie nowych abstrakcji na bazie już istniejących klas. Jednakże, istnieją sytuacje, w których potrzebne są bardziej elastyczne mechanizmy do obsługi typów danych przechowywanych lub przetwarzanych przez klasy.

## Potrzeba typów generycznych

Często programiści potrzebują określić typy danych przechowywanych lub przetwarzanych przez klasy. Mechanizm dziedziczenia i reguła podstawiania (polimorfizm) w teorii pozwalają na abstrahowanie od typu przetwarzanych obiektów, deklarując je jako typ `Object`. Takie podejście jest jednak mało wygodne i może prowadzić do konieczności nieefektywnego rzutowania typów.

## Typy generyczne jako rozwiązanie

W wielu językach programowania, takich jak Java, C# czy C++, wprowadzono typy generyczne (parametryzowane). Pozwalają one sparametryzować fragment kodu typem przetwarzanych danych, dodając nowy rodzaj parametrów, które opisują typy.

### Implementacje w różnych językach

- **C++**: Implementacja oparta jest na rozwijaniu makr, co umożliwia bardzo dużą siłę wyrazu, w tym metaprogramowanie.
  
- **Java**: Wprowadzono mechanizm typów generycznych, jednak implementacja opiera się na wymazywaniu typów (type erasure), co było wymuszone zachowaniem zgodności z wcześniejszymi wersjami maszyny wirtualnej. Ma to pewne ograniczenia, ale jest wystarczające w większości przypadków.

- **C#**: Podobnie jak Java, wprowadzono typy generyczne, jednak rozwiązanie jest bardziej spójne i nie ma ograniczeń wynikających z zachowania kompatybilności wstecz.

### Przykład: Klasa generyczna `Pair`

Jako przykład klasy generycznej rozważmy klasę `Pair`, która przechowuje dwie wartości dowolnego typu. Klasa powinna zawierać metody umożliwiające odczytywanie i podmienianie elementów pary oraz odpowiedni konstruktor.

```java
public class Pair<T> {
    private T first;
    private T second;

    public Pair(T first, T second) {
        this.first = first;
        this.second = second;
    }

    public T getFirst() {
        return first;
    }

    public void setFirst(T first) {
        this.first = first;
    }

    public T getSecond() {
        return second;
    }

    public void setSecond(T second) {
        this.second = second;
    }
}
```
Klasa `Pair` jest parametryzowana typem `T`, co pozwala na elastyczne używanie jej do przechowywania pary elementów dowolnego typu.

Typy generyczne są potężnym narzędziem, które znacznie zwiększają wyrazistość i użyteczność języków programowania obiektowego poprzez możliwość bardziej elastycznego zarządzania typami danych.

## Deklaracja klasy parametryzowanej

Deklaracja klasy parametryzowanej różni się od zwykłej klasy przez wskazanie typów będących parametrami tej klasy. Parametry te są umieszczane bezpośrednio po nazwie klasy, oddzielone przecinkami, a cała lista parametrów jest umieszczona w nawiasach kątowych, podobnie jak w języku C++.

## Konwencje nazewnictwa

Podczas korzystania z typów generycznych stosuje się pewne konwencje nazewnicze:

- **T** – typ ogólny (generalny),
- **K** – klucz,
- **V** – wartość,
- **E** – element (np. kolekcji),
- **N** – liczba.


```java
public interface Pair<K, V> {
    public K getKey();
    public V getValue();
}
```

Interfejs ten definiuje parę, której klucz jest typu `K`, a wartość jest typu `V`, umożliwiając operowanie na parze elementów dowolnych typów.

Typy generyczne są niezwykle przydatnym narzędziem, które znacznie zwiększają ekspresywność i użyteczność języków programowania obiektowego poprzez możliwość dynamicznego parametryzowania klas i metod.


# Zalety i problemy związane z typami generycznymi

## Zalety typów generycznych:

- **Kontrola typów na poziomie kompilacji**: Typy generyczne pozwalają na sprawdzenie poprawności typów już podczas kompilacji kodu, co eliminuje wiele błędów w czasie wykonania.
  
- **Brak potrzeby rzutowania**: Dzięki typom generycznym unikamy konieczności stosowania rzutowania (casting), co upraszcza i ułatwia kodowanie.

- **Ogólna implementacja algorytmów**: Typy generyczne umożliwiają implementację algorytmów w sposób ogólny, który można stosować do różnych typów danych.

## Ważniejsze problemy związane z typami generycznymi:

- **Typy proste nie mogą być parametrami typów generycznych**: Typy generyczne muszą być typami referencyjnymi, a nie prostymi (np. int, float), co jest ograniczeniem wynikającym z implementacji w języku Java.

- **Brak wsparcia dla operatora instanceof**: Operator instanceof nie może być stosowany do typów generycznych z określonymi argumentami, ponieważ jest on wyliczany podczas działania programu, gdy informacje o typach są już częściowo utracone.

- **Nie można tworzyć obiektów typu będącego parametrem typu generycznego**: Ograniczenie to wynika z faktu, że mechanizm typów generycznych i dziedziczenia nie nakładają żadnych ograniczeń na konstruktory.

- **Nie można tworzyć tablic typów generycznych**: W języku Java nie jest możliwe utworzenie tablicy zawierającej obiekty typu generycznego.

- **Rzutowania do typów generycznych generują ostrzeżenia kompilatora**: Rzutowanie do typów generycznych może generować ostrzeżenia kompilatora, co może sugerować potencjalne problemy z typami.

## Wykorzystanie typów generycznych

Typy generyczne mogą być używane na kilka sposobów:

- Tworzenie własnych typów generycznych.
- Wykorzystywanie bibliotek wbudowanych lub innych, które używają typów generycznych.
- Tworzenie własnych typów generycznych na bazie istniejących, zarówno własnych, jak i cudzych.

## Implementacja uogólnionych metod w Javie

Metody generyczne mogą być implementowane również w zwykłych klasach. Deklaracja takich metod poprzedzana jest określeniem parametrów w nawiasach kątowych, podobnie jak dla klas uogólnionych. Jednakże, przy użyciu metody generycznej, nie jest konieczne podawanie listy typów, ponieważ kompilator sam dedukuje te typy na podstawie argumentów przekazywanych do metody.

Przykład:

```java
public class GenericsMethods {
    public <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.print(element + " ");
        }
        System.out.println();
    }
}
```


Metoda `printArray` jest metodą generyczną, która może drukować dowolny typ tablicy.

Ramy (ang. bounds) w typach generycznych
Ramy pozwalają na nałożenie ograniczeń na typy konkretyzujące typ generyczny. Dzięki ramom można narzucić reguły dotyczące typów, które mogą być używane z danym uogólnieniem. Nałożenie ramy pozwala również na wywołanie metod odpowiednich dla typów, które pasują do ramy.

Przykład ograniczenia do typów implementujących interfejs `Comparable`:

```java
public class MyClass<T extends Comparable<T>> {
    // Metody i pola klasy
}
```

W tym przypadku `T` musi być typem, który implementuje interfejs `Comparable`.

Typy generyczne są potężnym narzędziem w języku Java, które umożliwiają tworzenie bardziej elastycznych i bezpiecznych struktur oraz algorytmów, mimo pewnych ograniczeń wynikających z implementacji.

# Ograniczenia i wariancje w typach generycznych

## Ograniczenia parametrów typów generycznych

Czasami konieczne jest narzucenie ograniczeń na parametry klasy generycznej. Przykładowo, chcemy, aby parametry były jedynie typami liczbowymi, a nie typami jakichkolwiek obiektów. W Javie można osiągnąć to poprzez określenie ograniczenia już na etapie implementacji klasy:

```java
class Stos<T extends Number> {
    // Implementacja klasy Stos, gdzie T musi być podtypem klasy Number
}
```

Można używać takiej klasy generycznej polimorficznie, podstawiając różne typy liczbowe pod parametr T podczas tworzenia obiektu.

## Ograniczenia wielokrotne

Typ generyczny można ograniczyć do jednoczesnego rozszerzenia klasy i implementacji interfejsów. Na przykład:

```java
class C2<T extends C1 & I1 & I2> {
    // Implementacja klasy C2, gdzie T musi rozszerzać klasę C1 oraz implementować interfejsy I1 i I2
}
```
W powyższym przykładzie, typ T musi być podtypem klasy C1 oraz implementować interfejsy I1 i I2. Klasa musi wystąpić jako pierwsza w kolejności ograniczeń.

## Wariancje w typach generycznych

W Javie wprowadzono możliwość korzystania z wariancji typów generycznych poprzez użycie symboli wieloznacznych:

- **Kowariancja** (`<? extends T>`): Ograniczenie z góry, oznacza wszystkie podtypy T.
- **Kontrawariancja** (`<? super T>`): Ograniczenie z dołu, oznacza wszystkie nadtypy T.
- **Biwariancja** (`<?>`): Oznacza wszystkie typy.

Te mechanizmy pozwalają na bezpieczne przekazywanie obiektów do metod (zapis) oraz odczytywanie wartości zwracanych (odczyt) dla typów uogólnionych.

### Przykład wykorzystania wariancji:


```java
Box<Float> boxFloat = new Box<Float>(1F);
Box<Number> boxNumber = new Box<Number>(2.0);
Box box = new Box(100);

box = boxFloat; // ok
box = boxNumber; // ok
boxFloat = box; // ostrzeżenie: Unchecked Conversion
boxNumber = box; // ostrzeżenie: Unchecked Conversion
boxNumber = boxFloat; // błąd kompilacji
boxFloat = boxNumber; // błąd kompilacji
```

## Typy generyczne i dziedziczenie

W interfejsach generycznych można określić parametry typów oraz dodatkowe parametry, które rozszerzają funkcjonalność.

Przykład:

```java
interface PayloadList<E, P> extends List<E> {
    void addPayload(P val);
    // Dodatkowe metody i pola interfejsu
}
```
Interfejs `PayloadList` rozszerza interfejs `List` o dodatkową funkcjonalność związaną z dodawaniem payloadów.

Typy generyczne w Javie są potężnym narzędziem, które umożliwiają tworzenie bardziej elastycznych i bezpiecznych struktur danych oraz algorytmów, mimo pewnych ograniczeń wynikających z implementacji.


## prezentacja kozioła o stringach

```
https://urstudrzeszow.sharepoint.com/sites/Programowanieobiektowewykady-materiay/Materiay%20z%20zaj/PO1%20wyk%C5%82ad/wyk%C5%82ad%208%20-%20ci%C4%85gi%20znak%C3%B3w.pdf?wdsle=0&CT=1719482525363&OR=ItemsView&wdOrigin=TEAMSFILE.FILEBROWSER.DOCUMENTLIBRARY
```
## -||- o strumieniach
```
https://urstudrzeszow.sharepoint.com/:p:/r/sites/Programowanieobiektowewykady-materiay/_layouts/15/Doc2.aspx?action=edit&sourcedoc=%7B37dec53c-6512-4a8d-b3ba-204d5905c0bd%7D&wdOrigin=TEAMS-WEB.teamsSdk_ns.rwc&wdExp=TEAMS-TREATMENT&wdhostclicktime=1719482606275&web=1
```


# nie chce mi się już fajrant 
# reszta u kozioła