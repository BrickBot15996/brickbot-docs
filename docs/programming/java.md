# **Java**

<!--make things bold-->

Java este un limbaj care face parte din grupul OOP (Object-Oriented Programming). Asta  
înseamnă că dispune de o serie de feature-uri specifice pe care le vom explora pe scurt.

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
```

Aceste litere pe care le vedeți aici (a, b, c etc.) se numesc variabile, exact pentru  
motivul că valoarea lor poate varia. Ele pot prelua orice tip, însă odată declarate tipul  
lor (aproape că) nu poate fi schimbat. Vom discuta despre asta puțin mai încolo însă.

<!--move methods, add operators and intructions-->

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
prin sunetele pe care le scot. Utilizarea clasei `Animal` ca și trăsătură comună ne  
permite să nu mai avem câmpurile `name` și `age` în fiecare tip de animal.

### Clase și Interfețe

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

Un ultim tip de "clasă" sunt interfețele. O interfață poate conține metode, insă fără să aibă  
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
detaliu în secțiunea de Principii OOP.

### Cuvinte cheie

- static, final
- access markers
- @Override

### Principii OOP

- inheritance
- abstraction
- skibussy i forgot the rest

<hr>

## **Alte resurse**

Pentru informații mai detaliate despre Java, ce prezintă multe din cele și mai multe  
feature-uri ale acestui limbaj, recomand să accesați site-ul <a href="https://www.w3schools.com/java">W3Schools</a>.

<hr>
