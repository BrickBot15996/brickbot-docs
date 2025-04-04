# **Java**

## **Ce este Java?**

Java este un limbaj care face parte din grupul limbajelor **OOP** (Object-Oriented Programming).
Asta înseamnă că dispune de o serie de feature-uri specifice pe care le vom explora în continuare.

Pentru a putea testa noțiunile explicate mai jos, putem folosi <a href="https://www.w3schools.com/java/tryjava.asp?filename=demo_compiler" target="_blank">acest</a> mediu de dezvoltare
online.

<hr>

## **Tipuri de date primitive**

Ca în orice limbaj de programare, este nevoie de un mijloc de a salva și manipula
informații. Tipurile de date primitive sunt cele fundamentale, regăsite într-o formă
sau alta în aproape orice limbaj.

```java
byte a = 36; // byte ține numere întregi pe 1 byte
short b = 15996; // short ține numere întregi pe 2 bytes
int c = 15996; // int ține numere întregi pe 4 bytes
long d = 15996; // long ține numere întregi pe 8 bytes

float e = 5.0; // float ține nume raționale pe 4 bytes
double f = 5.0; // double ține tot numere raționale, dar pe 8 bytes
                // permițând precizie mai mare;
                // în general recomand utilizarea double

boolean g = true; // boolean ține valori true sau false

char h = 'B'; // char ține caractere
var i = "BrickBot"; // var permite atribuirea oricărui tip de date,
                    // fără a-l specifica în mod explicit
```

Aceste litere pe care le vedeți aici (a, b, c etc.) se numesc **variabile**, exact pentru
motivul că valoarea lor poate varia. Ele pot prelua orice tip, însă odată declarate tipul
lor (aproape că) nu poate fi schimbat. Vom discuta despre asta puțin mai încolo însă.

<hr>

## **Operatori și Instrucțiuni**

Pentru a putea manipula datele, trebuie să cunoaștem operatorii și instrucțiunile încorporate
în limbajul Java.

#### **Operatori**

##### **Operatori Aritmetici**

- `+`, `-`, `*`, `/` - operațiile fundamentale de adunare, scădere, înmulțire, împărțire
- `%` - calculează restul împărțirii
- `++`, `--` - operatorii de incrementare și decrementare realizează creșterea sau scăderea
  unei valori cu o unitate

```java
x + 5; // suma între x și 5
x - 5; // diferența între x și 5
x * 5; // produsul între x și 5
x / 5; // împărțirea lui x la 5
x % 5; // restul împărțirii lui x la 5
x++; ++x; // crește valoarea lui x cu 1;
x--; --x; // scade valoarea lui x cu 1;
          // poziția operatorului incremental/decremental determină
          // ordinea operațiilor
          // după - întâi este folosită valoarea lui x,
          //        apoi este incrementată/decrementată
          // înainte - întâi este incrementată/decrementată,
          //           apoi este folosită noua valoare
```

##### **Operatori de Atribuire**

- `=` - atribuie unei variabile o valoare
- `+=`, `-=`, `*=`, `/=`, `%=` - aplică operațiile ilustrate mai sus

```java
int x = 0; // lui x îi este atribuită inițial valoarea 0;
x += 5; // este echivalent cu x = x + 5; valoarea lui x este crescută cu 5
x -= 5; // este echivalent cu x = x - 5; valoarea lui x este scăzută cu 5
x *= 5; // este echivalent cu x = x * 5; valoarea lui x este înmulțită cu 5
x /= 5; // este echivalent cu x = x / 5; valoarea lui x este împărțită la 5
x %= 5; // este echivalent cu x = x % 5; valoarea lui x este egală cu restul
        // împărțirii sale la 5
```

##### **Operatori logici**

- `&&` - operatorul și
- `||` - operatorul sau
- `!` - operatorul de negație

##### **Operatori de comparare**

- `==` - egalitate
- `!=` - nu(!) egalitate
- `>`, `<` - strict mai mic/mai mare
- `>=`, `<=` - mai mare sau egal/mai mic sau egal

#### **Instrucțiuni**

##### **Instrucțiuni condiționale**

Pentru a putea evalua _condiții_ în Java, putem folosi instrucțiunea `if`.

```java
if (condiție1) {
    // una sau mai multe acțiuni
} else if (condiție2) {
    // una sau mai multe acțiuni
} else {
    // una sau mai multe acțiuni
}
```

Această structură este cea mai complexă implementare a unei instrucțiuni `if`:

- `if (condiție1)` - evaluează condiția și decide dacă este sau nu îndeplinită.
- `else if (condiție2)` - propune o altă condiție spre evaluare, în cazul în care
  prima nu este îndeplinită.
- `else` - în cazul în care niciuna dintre condițiile precedente nu este îndeplinită,
  acțiunile acestui câmp for fi executate.

În cazul în care avem o serie de foarte multe instrucțiuni `else if` există alternativa
de a folosi un `switch case`.

```java
switch(expresie) {
    case valoare1:
        // una sau mai multe acțiuni
        break;
    case valoare2:
    case valoare3:
        // una sau mai multe acțiuni
        break;
    default:
        // una sau mai multe acțiuni
        break;
}
```

Utilizarea generală a unui `switch case` este pentru a evalua mai multe posibile valori
cunoscute ale unei expresii. În funcție de valoarea acesteia, va fi ales un anumit `case`.
De asemenea, există și cazul `default`, pentru situațiile în care una dintre valori nu a fost
menționată explicit în cazurile precedente.

`break` este un cuvânt cheie despre care vom discuta mai încolo, însă, pe scurt, rolul său
este pentru a determina finalul acțiunilor aferente unui caz. După cum putem observa, între
cazurile pentru `valoare2` și `valoare3` nu există cuvântul cheie `break`. De ce? Pentru
că aici a fost folosit mecanismul de fall-through. Practic, dacă avem 2 cazuri diferite
pentru care am vrea să avem aceleași consecințe, putem să nu folosim `break`, iar cazurile
vor _curge_ unul în altul.

##### **Bucle repetitive**

În Java avem la dispoziție 3 tipuri principale de bucle repetitive:

- `while(condiție)` - se va executa cât timp condiția este îndeplinită
- `do while(condiție)` - se va executa cel puțin o dată și se va opri când
  condiția nu mai este îndeplinită
- `for`- se va executa pentru un număr cunoscut de iterații

Din punct de vedere sintactic, buclele `while` și `do while` sunt foarte simple.

```java
while (condiție) {
    // una sau mai multe acțiuni
}

do {
    // una sau mai multe acțiuni
} while (condiție);
```

După cum puteți vedea, în cazul buclei `do while` condiția este pusă la final, executându-se
o dată înainte de a ajunge prima dată la verificare condiției.

Bucla `for` este mai inedită. Pentru a putea îndeplini funcționalitatea de a rula pentru
un număr prestabilit de iterații, sintaxa este ceva mai complexă.

```java
for (int i = 0; i < 10; i++) {
    // una sau mai multe acțiuni
}
```

Pentru a putea înțelege de ce arată așa, trebuie să descompunem puțin logica sa. Structura
este de fapt de forma `for(valoare inițială; condiții; pas)`. O buclă `for` practic face
o numărătoare, de la o valoare inițială (în cazul nostru 0) până la o valoare maximă (în
cazul nostru 10), folosind un pas (amintindu-ne de operatorul incremental `++`, pasul este
1). Astfel, putem determina numărul total de iterații (10 în exemplul dat). Ce trebuie să
observăm este că, în structura buclei `for` am menționat _condiții_, nu valoare limită. Asta
înseamnă că putem pune și alte condiții, care nu au legătură neapărat cu numărătoarea
propriu-zisă.

```java
for (int i = 0; (i < 10) && (i % 5 != 4); i += 2) {
    // una sau mai multe acțiuni
}
```

Acest exemplu parcurge o serie de numere pornind de la 0, din 2 în 2, până când întâlnește un
număr care nu este mai mic decât 10 sau până când întâlnește un număr al cărui rest al împărțirii
la 5 este 4. Primul număr de acest fel este chiar 4, care deși este mai mic decât 10, provoacă
întreruperea iterațiilor.

O altă formă a buclei `for` este `for-each`.

```java
for (Robot robot : robots) {
    // una sau mai multe acțiuni
}
```

Pentru a putea înțelege în totalitate acest tip de buclă avem nevoie de câteva cunoștințe mai
avansate, însă o vom aborda într-un mod mai practic. `robots` este tratat ca un _grup_ de roboți.
Această buclă preia toate elementele de tipul `Robot` și le oferă temporar numele `robot` pentru
a le putea prelucra individual. Această structură de tip `for-each` face foarte ușoară parcurgerea
grupurilor de obiecte, fără a fi nevoie să ținem cont de numărul, deoarece va face exact atâtea
iterații câte obiecte sunt în grupul `robots`.

<hr>

## **Metode**

Metodele sunt secvențe de cod reutilizabile, ce pot fi folosite printr-un simplu apel.

```java
int add(int a, int b) {
    return a + b;
}
```

Metoda `add()` cuprinde tot ce ne interesează. La început, cuvântul cheie `int` arată tipul
de date ce va fi returnat de metodă. Aici poate apărea orice tip primitiv și neprimitiv de
date, în funcție de ce doriți să facă metoda. Mai există un "tip" pe care nu l-am acoperit
până acum, acela fiind `void`. Acesta este folosit atunci când nu dorești ca metoda ta să
returneze o valoare. `add()` este numele metodei. Între paranteze, apar cei doi parametri
`int a, int b`, reprezentând cele două numere întregi a căror sumă dorim să o calculăm.
Între acolade, se află conținutul metodă ce va fi executat de fiecare dată când aceasta este
apelată. `return` reprezintă valoarea pe care o vei primi din partea metodei. Pentru a apela
o funcție, trebuie să o numiți și să îi dați parametrii dacă este cazul.

```java
int c = add(3, 6); // În acest caz, c va primi valoarea 3 + 6 = 9
```

<hr>

## **Programare orientată pe obiecte (OOP)**

După cum am menționat mai sus, Java este un limbaj OOP. Ce înseamnă asta? Ei bine, la
baza oricărui tip neprimitiv de date stă tipul `Object`. Scopul limbajelor OOP este facilitarea
reutilizării codului, prin descoperirea de proprietăți comune între obiecte.

```java
public abstract class Animal {
    String name;
    int age;
    abstract void makeSound();
}

class Cat extends Animal {
    Cat(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void makeSound() {
        System.out.println("Meow!");
    }
}

class Dog extends Animal {
    Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void makeSound() {
        System.out.println("Woof!");
    }
}
```

Acest exemplu prezintă și câteva concepte mai complicate pe care urmează să le
parcurgem. În esență, ce face acest cod este diferențierea dintre un câine și o pisică
prin sunetul pe care îl scoate fiecare. Utilizarea clasei `Animal` ca și trăsătură
comună ne permite să nu mai avem câmpurile `name` și `age` în fiecare tip de animal.

#### **Clase și Interfețe**

După cum puteți vedea, în exemplul principal este folosit cuvântul cheie `class`. Clasa
deține definiția trăsăturilor unui obiect. Cum o putem folosi? Ei bine, în exemplul de mai
sus există metodele `Cat()` și `Dog()` care poartă numele claselor în care se află. Aceste
metode se numesc constructori. Constructorii creează o **instanță** a clasei. Practic, două
apeluri diferite de constructor creează 2 animale diferite, indiferent dacă au același nume,
vârstă sau sunt de aceeași specie.

```java
Dog dog = new Dog("Azorel", 7);
```

Această linie de cod creează o **instanță** a clasei `Dog`, având numele Azorel și vârsta de
7 ani. Mai departe, puteți accesa câmpurile și metodele acestei clasei folosind punct.

```java
dog.makeSound(); // Acest apel ar trebui să afișeze în consolă "Woof!"
```

În Java există mai multe tipuri neprimitive de date care pot fi folosite fără a necesita
implementarea manuală a lor. Cel mai des întâlnit dintre ele este String.

```java
String team = "BrickBot"; // Tipul String ține un șir de caractere
```

La bază, toate tipurile neprimitive sunt de tipul `Object` și implicit clase la bază. Ce nu am
menționat încă, este că mai există 2 tipuri de "clase".

În exemplul cu animalele, am folosit cuvântul cheie `abstract`. Abstract semnalează practic
o clasă incompletă. Pentru a putea avea o clasă abstractă, este necesară prezența unei
metode abstracte, precum `makeSound()`, care trebuie completată cu sunetul specific al
animalului pe care vrem să-l creem. Clasele abstracte sau incomplete nu pot fi instanțiate,
având trăsături nedefinite.

Un alt tip de "clasă" sunt interfețele. O interfață poate conține metode, insă fără să aibă
o implementare. Un exemplu bun de utilizare a interfețelor este pentru o serie de comenzi
de tipuri diferite.

```java
interface Command {
    void execute();
}

class InstantCommand implements Command {
    void execute() {
        // Implementare
    }
}

class SequentialCommand implements Command {
    void execute() {
        // Implementare
    }
}
```

Această interfață `Command`, ne permite generalizarea tuturor tipurilor de comenzi, fiecare
putând fi apelată cu metode ce poartă același nume. Acest concept va fi prezentat mai în
detaliu în secțiunea de <a href="#principiile-oop">Principii OOP</a>.

Ultimul tip este reprezentat de enumerații. Acestea sunt declarate folosind cuvântul cheie
`enum`.

```java
public enum Teams {
    BRICKBOT(15996),
    INFINITYEDGE(19060),
    NEW_ROBOTICS_TEAM(99999);

    int teamNumber;

    Teams(int teamNumber) {
        this.teamNumber = teamNumber;
    }

    public int getTeamNumber() {
        return teamNumber;
    }
}
```

Enumerațiile sunt exact ce le sugerează și numele, o listă de lucruri dintr-o anumită
categorie. În general, sunt utilizate pentru înregistrarea unui număr finit de stări.
Ele pot conține variabile, metode și constructori pentru a putea asocia trăsături
fiecărui element al enumerației.

#### **Extindere și Implementare**

Două elemente care au apărut în exemplele de până acum, asupra cărora nu am atras atenția
au fost cuvintele cheie `extends` și `implements`. Acestea sunt mijloacele prin care o clasă/o interfață
poate prelua trăsăturile alteia.

- `extends` - se folosește când se dorește preluarea trăsăturilor unei clase. O clasă poate
  extinde o singură altă clasă.
- `implements` - se folosește când se dorește preluarea trăsăturilor unei interfețe. În cazul
  acesta, pot fi implementate una sau mai multe interfețe.

#### **Cuvinte cheie**

Cuvintele cheie din Java sunt termeni rezervați de limbaj, ce ajută la definirea structurii
și comportamentului programelor, având semnificații prestabilite. Pentru a explora toate
cuvintele cheie pe care le avem la dispoziție, puteți accesa această <a href="https://www.w3schools.com/java/java_ref_keywords.asp" target="_blank">listă</a>. În
continuare, vom aborda câteva dintre cele mai importante care nu au fost menționate până acum.

##### **Specificatori de acces**

În Java, specificatorii de acces determină unde pot fi preluate și utilizate anumite câmpuri,
fie ele variabile, metode sau clase.

- default - acesta este implicit și nu trebuie menționat; câmpurile pot fi accesate în același
  pachet
- private - cel mai strict; câmpurile pot fi accesate doar în cadrul clasei în care au fost
  declarate
- protected - câmpurile pot fi accesate doar în cadrul subclaselor
- public - cel mai puțin restrictiv, câmpurile pot fi accesate oriunde în cadrul proiectului

##### **Modificatori**

Doi modificatori foarte importanți pe care nu i-am menționat până acum sunt:

- `static` - permite accesarea câmpului respectiv fără a creea o instanță a clasei
- `final` - odată cu inițializarea unei variabile, valoarea acesteia nu poate fi modificată.
  Acesta poate fi folosit și în cazul claselor, pentru a nu permite extinderea lor, sau în
  cazul metodelor pentru a nu permite suprascrierea lor.

##### **Annotări**

Annotările nu sunt cu adevărat cuvinte cheie, însă acestea sunt cuvinte precedate de `@`, în
general plasate deasupra declarării unei clase, metode sau variabile. Cea mai des întâlnită
annotare este `@Override`. Aceasta permite suprascrierea unei metode care nu a fost marcată
ca `final` și are deja o definiție.

#### **Principiile OOP**

În programarea orientată pe obiect (OOP) din Java, patru principii fundamentale sunt esențiale
pentru a înțelege structura aplicațiilor: încapsularea, moștenirea, polimorfismul și abstracția.

1. **Încapsularea** presupune ascunderea detaliilor interne ale unei clase și oferirea unui set de
   metode publice pentru interacțiunea cu obiectele acelei clase. Astfel, datele sensibile sunt
   protejate, iar utilizatorul clasei nu are acces direct la variabilele interne, ci doar la
   metodele care manipulează aceste date.

2. **Moștenirea** permite crearea de clase noi care preiau comportamente și proprietăți de la alte
   clase deja existente. Acest principiu favorizează reutilizarea codului și reducerea duplicării
   acestuia.

3. **Polimorfismul** se referă la capacitatea unui obiect de a lua forme diferite, de obicei prin
   suprascrierea metodelor. Astfel, aceleași metode pot avea comportamente diferite în funcție
   de tipul obiectului care le invocă.

4. **Abstracția** ascunde complexitatea sistemului, prezentând doar informațiile esențiale. În Java,
   acest principiu este implementat prin utilizarea de clase și interfețe abstracte care definesc
   comportamentele fără a dezvălui implementările detaliate.

#### **Design Patterns**

Deși conceptul de design pattern este unul destul de avansat, este important să fim conștienți de
existența lor și să înțelegem cum pot îmbunătăți calitatea unui proiect. Aceste modele reprezintă
soluții dovedite și eficiente pentru rezolvarea unor probleme recurente în proiectele OOP, facilitând
organizarea logică și structurarea clară a codului. Implementarea design patterns contribuie la
modularitatea, scalabilitatea și întreținerea mai ușoară a proiectelor. Pentru a aprofunda acest
concept, recomand citirea documentației despre design patterns de pe <a href="https://refactoring.guru/design-patterns" target="_blank">acest</a> site.

<hr>

## **Alte resurse**

Pentru informații mai detaliate despre Java, ce prezintă multe din cele și mai multe
feature-uri ale acestui limbaj, recomand să accesați site-ul <a href="https://www.w3schools.com/java">W3Schools</a>.

<hr>
