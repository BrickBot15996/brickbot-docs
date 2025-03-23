# **Java în FTC**

## **Learn Java For FTC**

<a href="/programming/media/LearnJavaForFTC.pdf" target="_blank">_Learn Java for FTC_</a> este o carte destinată în special începătorilor, realizată de
Alan Smith, mentorul echipei <a href="https://ftcscout.org/teams/16072" target="_blank">16072 Quantum Quacks</a>,
ce adună la un loc toate conceptele fundamentale ale programării în FTC. Aceasta parcurge
totul, de la noțiuni introductive despre limbajul Java până la modurile de utilizare
a tuturor tehnologiilor disponibile în FTC.

<hr>

## **Ce este un OpMode?**

La baza oricărui cod care va rula pe robot stă un OpMode. Acesta este un program
ce definește logica de funcționare a robotului. Corespunzător etapelor unui meci
FTC, acestea sunt de 2 feluri:

- `@Autonomous` - acest tip de OpMode rulează fără a primi comenzi de la driver
- `@TeleOp` - acest tip de OpMode primește și îndeplinește comenzi de la driver

<!--prettier-ignore-start-->
??? note "Notă"
    După cum puteți observa, cei doi termeni sunt precedați de `@`, ceea ce
    înseamnă ca sunt <a href="/programming/java/#annotari" target="_blank">annotări</a>.
<!--prettier-ignore-end-->

Pentru a declara un OpMode, trebuie să ne folosim de conceptul de moștenire. În
SDK-ul (Software Development Kit) al FTC, adică proiectul ftcrobotcontroller pe
care l-am menționat în secțiunea precedentă, există mai multe structuri de OpMode
pe care le putem folosi. În general este preferată moștenirea clasei `LinearOpMode`,
deoarece are o viteză mai bună de rulare. Astfel, un exemplu de declarare a unui
OpMode este:

```java
// Declararea unei autonomii
@Autonomous (name="ExampleAutonomous", group="Examples")
public class ExampleAutonomous extends LinearOpMode {
    // conținutul OpMode-ului
}

// Declararea unei teleoperări
@TeleOp (name="ExampleTeleOp", group="Examples")
public class ExampleTeleOp extends LinearOpMode {
    // conținutul OpMode-ului
}
```

Utilizarea uneia dintre cele două annotări decide ce fel de tip de OpMode va
fi. De asemenea, putem observa prezența a două câmpuri: `name` și `group`.
Pe aplicația de pe telefon, vom putea selecta ce OpMode să rulăm. Nu pot fi
rulate mai multe OpMode-uri simultan. Câmpul `name` determină ce nume va apărea.
Dacă nu este completat acest câmp, programul va prelua direct numele clasei.
În cadrul aplicației, programele sunt sortate în ordine alfabetică. În cazul
în care vrem să facem diferența între câteva dintre ele, putem să le setâm
același grup. Grupurile vor fi sortate alfabetic, iar programele din cadrul
fiecărui grup vor fi sortate la rândul lor tot alfabetic.

Un OpMode are două etape:

- init - etapa în care robotul este pregătit să pornească, însă nu are voie
  să se deplaseze pe teren
- run - etapa în care robotul primește și execută comenzi

#### Starea unui OpMode

Există o serie de metode pentru a determina sau modifica starea unui OpMode:

- `opModeInInit()` - returnează o valoare booleană care spune daca este sau
  nu în init acest OpMode.
- `opModeIsActive()` - returnează o valoare booleană care spune dacă este
  sau nu activ acest OpMode. Pentru ca un opMode să fie activ, acesta trebuie
  să fie în etapa run.
- `waitForStart()` - așteaptă ca robotul să intre în etapa de run.
- `isStopRequested()` - returnează o valoare booleană care spune dacă a fost
  sau nu cerută oprirea programului.
- `sleep()` - face ca robotul să nu poată accepta comenzi sub nicio formă
  pentru un număr dat de milisecunde.

#### Telemetrie

Telemetria este o unealtă cu ajutorul căreia poți trimite informații de la
robot către Driver Station. Telemetria are două metode principale în cod:

- `telemetry.addData()` - prin care adaugi informații în telemetrie.
- `telemetry.update()` - prin care trimiți toate informațiile acumulate
  către Driver Station.

Trebuie să țineți cont de faptul că, telemetria acumulează toată informația
și o trimite pe toată odată. De aceea, trebuie să apelați metoda de `update()`
o singură dată per loop. Dacă o veți apela de mai multe ori, întâi va fi
trimisă toată informația, va fi ștearsă, iar la al doilea apel nu va fi
trimis nimic.

#### HardwareMap

HardwareMap-ul conține lista tuturor componentelor electronice aflate
pe robot. Aici trebuie adăugate toate motoarele, toate servo-urile,
toți senzorii etc. și fiecare cu propriul nume pentru a putea fi
identificate. Cum poate face robotul conexiunea între nume și portul
în care se află fiecare componentă? Ei bine, în cadrul Driver
Station-ului există o secțiune de configurare, în cadrul căreia
trebuie introduse aceleași nume în dreptul porturilor în care este
mufat fiecare element.

<hr>
