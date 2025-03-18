# **Componentele electronice**

<!-- TODO: fa totul la intai plural nu a doua plural-->

Componentele electronice sunt baza oricărui robot. Acestea pot fi folosite în număr
limitat, iar de aceea este foarte important să întelegem cum funcționează, ce pot
face și cum pot fi folosite la potențialul lor maxim.

<hr>

## **Motoare**

Motoarele sunt cele mai puternice actuatoare pe care le avem la dispoziție în FTC. Mai
mulți dintre furnizorii principali au propriile lor motoare la vânzare, însă la bază toate sunt
la fel. Cele mai des folosite sunt motoarele <a href="https://www.gobilda.com/modern-robotics-12vdc-motor/" target="_blank">Modern Robotics 12VDC</a>.

![Motor Modern Robotics 12VDC](media/motor.png "Motor Modern Robotics 12VDC")
![Motor GoBilda 13.7:1](media/gobilda-435.png "Motor GoBilda 13.7:1")

Pentru a putea înțelege mai bine motoarele este nevoie de câteva concepte de bază:

- Cuplul - forța pe care o poate exercita un motor la capătul unui braț de 1cm. Se măsoară
  în kg⋅cm sau N⋅m
- RPM - numărul de rotații pe minut pe care îl realizează un motor la curent maxim. Acesta
  este invers proporțional cuplului.
- Rație - numărul de rotații care intră, raportat la câte ies. De exemplu 13.7:1 înseamnă că
  pentru fiecare 13.7 rotații ale motorului, vom avea o rotație la ieșire. Rațiile permit
  oarecum modificarea specificațiilor motorului. Această rație de 13.7:1 face ca motorul să fie
  de 13.7 ori mai lent, însă îi oferă un cuplu de 13.7 ori mai mare. În general vom întâlni
  două tipuri de rații - interne și externe. Cele interne sunt cele realizate de cutia de viteze
  a motorului. Cele externe sunt cele realizate prin transmisii pe curele, roți dințate sau
  orice altceva. Astfel putem obține orice viteză/cuplu dorim pentru un anumit mecanism.

### Curbele de performanță ale motoarelor

Foarte multe lucruri în lumea reală nu sunt liniare. În general este suficient să aproximăm
marea majoritate folosind liniaritatea, însă cred că este mai important să întelegem cum
funcționează de fapt motoarele.

![Curbă de performanță a unui motor](media/motor-curve.png "Curbă de performanță a unui motor")

Acest grafic ilustrează evoluția puterii unui motor, cu cât este aplicată mai multă forță pe  
el, până la maximul pe care îl poate duce. Cifrele pentru RPM și cuplu nu sunt de la sine
relevante, deoarece acestea se schimbă odată cu rația aplicată pe motor. Ce este cel mai  
important de ținut cont, este faptul că motorul produce cea mai mare putere la jumătate din  
cuplul său maxim. Concluzia care trebuie trasă de aici este că, pentru un mecanism care  
vrem să ruleze la potențial maxim, rația optimă este cea care oferă cuplu dublu față de  
forța aplicată pe motor. Această opțiune însă, nu este mereu cea corectă și vom vedea la  
secțiunea despre <a href="#bateriile-și-curentul">baterie și curent</a> de ce.

Există și câteva calculatoare publice care pot fi folosite pentru a determina cu aproximare  
rația adecvată unor mecanisme des folosite în FTC:

- <a href="https://www.chiefdelphi.com/t/ilite-drivetrain-simulator-v2020/369188" target="_blank">ILITE Drivetrain Calculator</a> - folosit pentru a determina rația pe care ar trebui să o
  folosim pentru un șasiu
- <a href="https://calculator.frc4322.com/linear-mechanism" target="_blank">Linear Mechanism Calculator</a> - folosit pentru a determina rația cea mai bună pentru  
  mecanisme liniare, cum ar fi lifturile

### Bune practici

Ceva de care ar trebui să ținem cont, este protejarea motoarelor. Practici bune în acest  
scop sunt:

- Evitarea direct drive - direct drive înseamnă atașarea mecanismului pe care îl  
  angrenează direct pe axul motorului. Această practică expune motorului la daune  
  interne, dar și la îndoirea axului în cazul în care sunt aplicate în mod direct șocuri pe  
  acesta. Alternativa constă în folosirea de transmisii externe despre care vom discuta  
  în secțiunea următoare.
- Gestionarea consumului de curent - consumul de curent crește odată cu forța aplicată  
  pe un motor. Conform curbei de performanță, puterea maximă produsă de motor se  
  află la jumătate din cuplul maxim. În general, nu este bine să depășim acest prag,  
  deoarece începem să pierdem și din performanța mecanismului și să consumăm  
  excesiv de mult curent, punând astfel sub risc motorul.
- Atenția la blocaje - dacă un motor nu se mai poate mișca, însă continuă să fie  
  alimentat, acesta va continua să tragă din ce în ce mai mult curent până când va  
  reuși să se miște sau se va arde. De aceea, ar trebui să avem foarte mare grijă,  
  în special din punct de vedere al programării, în momentul în care lucrăm cu motoare.

<hr>

## **Servouri**

Servo-urile la bază sunt tot niște motoare, însă cu un comportament destul de diferit.  
Există două moduri diferite pentru servo-uri:

- CRServo(Continuous Rotation Servo) - acest mod se comportă exact ca un motor.
- Servo - acest mod oferă un control foarte precis al poziției. Din punct de vedere  
  software, le pot fi atribuite valori între 0.0 și 1.0, acestea reprezentând o poziție  
  undeva în intervalul maxim pe care îl suportă. Există servo-uri cu intervale de 180,  
  270, 360 de grade, dar și unele care oferă mai multe rotații complete, până chiar la 7  
  rotații.

![Servo Axon Max](media/axon-max.webp "Servo Axon Max")
![Servo Plex Torque](media/plex-torque.png "Servo Plex Torque")

Conceptele de cuplu, RPM și rație rămân oarecum la fel. Mai apare în plus conceptul de  
viteză unghiulară. În general o să îl întâlnim sub forma de secunde/60°, reprezentând timpul  
necesar pentru a parcurge 60° de rotație.

Un lucru inedit la servo-uri este posibilitatea de a folosi un <a href="https://www.revrobotics.com/rev-31-1108/" target="_blank">servo programmer</a> pentru a  
seta și testa range-ul de folosire al acestuia. În cazul anumitor servo-uri, de exemplu cele  
Axon, ele folosesc un <a href="https://docs.axon-robotics.com/axon-servos/servo-programmer" target="_blank">program</a> pe calculator prin care poți controla mai multe setări.

### Bune practici

Comparativ cu motoarele, servo-urile sunt și mai fragile, necesitând și mai multă atenție  
în folosirea lor. Din punct de vedere al bunelor practici, evitarea direct drive rămâne  
în continuare o prioritate. De asemenea, mai există varianta de a fi protejate montând  
un rulment undeva de-a lungul atașamentului servo-ului, pentru a-i oferi încă un punct  
de susținere.

Un aspect foarte important de prevenit sunt șocurile. În general, brațele în FTC sunt  
angrenate folosind servo-uri, iar tendința generală este să folosim brațe destul de lungi,  
deoarece pot simplifica anumite sarcini ale jocului. În acele situații totuși, șocul în  
momentul în care brațul încearcă să se oprească devine foarte mare, riscând stricarea  
servo-urilor. Aici putem implementa conceptul de counter-springing, folosind un arc sau  
un elastic pentru a reduce din inerție, reducând șocul final. Puteți vedea implementarea  
în <a href="https://www.youtube.com/shorts/cLI090Csmi8" target="_blank">acest</a> filmuleț folosind câteva arcuri pe un braț. De asemenea, <a href="https://www.youtube.com/watch?v=QsBT6OzlN24&t=84s&ab_channel=Technicbots8565" target="_blank">acest</a> workshop ținut de  
echipa 14361 Robolobos ilustrează mai multe implementări de counter-springing și pentru  
alte tipuri de mecanisme.

<a href="https://www.youtube.com/watch?v=pmneNLmWc10&ab_channel=Wolfpack%26Lupine-WaringRobotics" target="_blank">Acest</a> filmuleț realizat de echipa 18438 Wolfpack Machina explică utilizarea corectă a  
servo-urilor în FTC. Reia toate informațiile prezentate până acum și oferă exemple vizuale  
pentru a face totul mai ușor de înțeles.

<hr>

## **Senzori**

Senzorii sunt o parte foarte importantă în FTC pentru a obține un robot fiabil, fie că este  
vorba de perioada de autonomie sau cea de teleoperare.

### Encodere

Pentru perioada de autonomie, aspectul cel mai important este localizarea. În acest sens,  
există niște senzori ce poartă numele de encoder. Scopul lor este măsurarea poziției de  
rotație. La ce ne poate folosi acest lucru? De exemplu, în cazul localizării, folosim o roată  
care merge de-a lungul terenului odată cu robotul. Dacă știm câte unități s-a rotit această  
roată, putem face conversia în cm pentru a afla cât de mult s-a deplasat robotul nostru.  
Encoderele nu sunt folosite doar în cazul localizării robotului. Ele pot fi folosite și pentru  
a determina cât de mult s-a extins un lift, folosind rotația motorului de exemplu. Encoderele  
îți permit să cunoști starea în care se află un mecanism. Există 2 tipuri principale de  
encoder:

- Relativ - acesta are la început o valoare 0, iar deplasarea este determinată față de acel  
  0 arbitrar.
- Absolut - acesta are un interval de 360 de grade și oferă poziția pe acel interval,  
  similar cu poziția servo-urilor. În momentul în care depășește cele 360 de grade,  
  începe iarăși de la 0.

### Camere

Un element nelipsit din jocurile FTC este utilizarea de computer vision folosind o cameră.
Aceasta poate fi folosită pentru detectarea unor elemente specifice perioadei de autonomie,  
sau pentru detectarea elementelor de joc pentru a fi colectate eficient și punctate. De  
asemenea, pe marginile terenului se mai află niște imagini, similare cu niște coduri QR,  
numite <a href="https://ftc-docs.firstinspires.org/en/latest/apriltag/vision_portal/apriltag_intro/apriltag-intro.html" target="_blank">april tag-uri</a>. Folosind biblioteca incorporată de computer vision, sunt foarte  
ușoare de folosit pentru a prelua poziția relativă față de ele. Astfel, cunoscând poziția  
lor absolută pe teren, putem obține poziția robotului pe teren destul de ușor.

### Alți senzori

Alți senzori sunt deseori folosiți pentru a determina dacă un element de joc a ajuns într-o  
anumită parte a robotului. În acest scop pot fi folosiți <a href="https://www.pololu.com/category/283/pololu-digital-distance-sensors" target="_blank">senzori de distanță</a>, <a href="https://www.revrobotics.com/rev-31-1557/" target="_blank">de culoare</a>,
<a href="https://www.optimusdigital.ro/en/others/3802-ir-break-beam-sensor-5mm-leds.html?srsltid=AfmBOorV_Iwi6ldmZ035XtM8g-1rpblMwcX8gbHlA9Hg8fkli82h4HUW" target="_blank">break beams</a> sau <a href="https://sigmanortec.ro/precomanda/other-accessories/dip-2-pin-momentary-push-button-tactile-tact-switches-6-x-6-x-5mm-contact-momentary" target="_blank">butoane</a>. În mod evident, există și alte utilizări pentru acești senzori, cum ar fi  
detectarea de obstacole sau determinarea stării unor mecanisme ale robotului.

### Protocoale de comunicare

Senzorii pot folosi mai multe protocoale de comunicare:

- Digital
- Analogic
- I²C
- Cuadratură

De ce trebuie să ținem cont de ele? Deoarece există o diferență importantă între I²C și  
celelalte. Timpul de citire al protocolului I²C este mult mai lung decât al celorlaltor  
protocoale, astfel încetinind viteza codului robotului. Din această cauză, ar trebui evitați  
pe cât posibil senzorii I²C.

### IMU

IMU(Intertial Measurement Unit) este un modul ce permite măsurarea orientării față de cele  
3 axe ale sistemului tridimensional, dar și alți parametrii precum accelerația și viteza pe  
fiecare axă. Un astfel de IMU este integrat în <a href="#control-hub-și-expansion-hub">Control Hub</a>, însă  
trebuie ținut cont că acesta folosește protocolul I²C.

Există, de asemenea, alte 2 produse foarte interesante ce conțin un IMU:

- <a href="https://www.gobilda.com/pinpoint-odometry-computer-imu-sensor-fusion-for-2-wheel-odometry/?srsltid=AfmBOooDG4LzVG8dq8ChpTcGNVmskizohiltAPpMYJrZsK2mI4I72jBq" target="_blank">Pinpoint</a> - un calculator care, folosind 2 roți ce măsoară deplasarea robotului și un IMU  
  poate determina poziția absolută a robotului în teren.
- <a href="https://www.sparkfun.com/sparkfun-optical-tracking-odometry-sensor-paa5160e1-qwiic.html" target="_blank">OTOS(Optical Tracking Odometry Sensor)</a> - un senzor optic care, folosind un IMU și o  
  serie de imagini cu suprafața terenului calculează poziția robotului în teren.

<hr>

## **Sistemul de control**

<a href="https://docs.revrobotics.com/duo-control" target="_blank">Sistemul de control</a> este _creierul_ robotului. Acesta rulează codul pe care îl scriem,
și controlează toate celelalte componente electronice.

### Control Hub și Expansion Hub

Control Hub-ul este partea principală a sistemului de control. Acesta este conectat la
Driver Station (telefonul care preia instrucțiunile de la driveri și le transmite robotului)
prin Wi-Fi. Pe el rulează o versiune minimală de Android și o aplicație (Robot Controller)
care se ocupă de gestionarea comenzilor primite și le transmite mai departe la celelalte
componente electrice.

Expansion Hub-ul este practic o extensie a Control Hub-ului, oferind aceleași porturi, însă
fără capacitatea de a fi conectat prin Wi-Fi și fără sistemul de operare.

Din punct de vedere calitativ, au câteva lipsuri, care pot prezenta probleme. În principal,
trebuie să ținem cont de următoarele lucruri:

- Nu folosiți portul USB 2.0 - acesta este conectat la placa de rețea, iar o problemă des
  întâlnită este ca odată cu o descărcare electrică suferită pe acest port, să se ardă
  placa de rețea, făcând imposibilă conectarea prin Wi-Fi la Control Hub, această
  componentă devenind complet inutilă. Puteți citi mai multe <a href="https://cookbook.dairy.foundation/electrical/why_we_should_only_use_usb_30.html" target="_blank">aici</a>.
- Porturile de encoder - din cauza electronicii interne, porturile de encoder 0-3 se
  comportă diferit față de porturile 1-2, porturile 1-2 fiind limitate la numărul de impulsuri
  pe care le pot măsura. Puteți citi mai multe în <a href="https://cookbook.dairy.foundation/electrical/how_to_wire_odometry_pods.html" target="_blank">această</a> postare și resursele de acolo  
  care prezintă mai bine cauza problemei.
- Porturile de servo - acestea sunt conectate între ele două câte două (0-1, 2-3 și 4-5) și pot
  scoate în total 4A de curent pe 2 porturi, de aceea ar trebui să aveți grijă ce și
  unde mufați în momentul în care folosiți servo-uri mai puternice (Axon, Plex etc.). Dacă
  unul dintre porturi se strică în vreun fel, nici cel asociat lui nu va mai funcționa.

### Bateriile și curentul

Bateriile în FTC vin cu o serie de specificații de bază, indiferent de modelul sau de
furnizorul de la care au fost cumpărate. Acestea funcționeaza la 12V și pot oferi un
curent de până la 20A. Pentru a avea un robot fiabil, este important să avem grijă la
consumul de curent al robotului în orice scenariu. Un consum prea mare de curent la un
moment dat, poate duce la "_brownout_"(stingerea pentru o fracțiune de secundă a
electronicii, întrerupând comunicarea cu driver station-ul și oprind mecanismele). În
general, un robot alimentează constant și simultan cel puțin 6 motoare care suferă
forțe relevante, ducând la un consum minim de curent deja destul de ridicat, luând în
calcul bugetul maxim de 20A. Astfel, trebuie implementate soluții mecanice pentru a mai
reduce din acest consum, fie prin alegerea unor rații mai "conservative" ale motoarelor
în cadrul mecanismelor, fie folosind counter-springing pentru a reduce din forța aplicată  
asupra actuatoarelor. Un alt parametru care afectează consumul de curent este rezistența  
internă a bateriei. <a href="https://www.gobilda.com/12v-battery-health-analyzer-nimh-3000mah/" target="_blank">Analizorul de sănătate a bateriei</a> de la Gobilda ne permite măsurarea  
acesteia. O rezistență internă mai mică, permite robotului să tragă mai mult curent din  
baterie. Această <a href="https://blog.eeshwark.com/robotblog/electrical-ramblings" target="_blank">postare</a> conține și o secțiune despre consumul de curent și  
bugetarea acestuia.

### Servo Power Module și Servo Hub

Servo Power Module și Servo Hub sunt două componente de electronică ce permit
alimentarea a 6 servo-uri cu 6V, în loc de cei 5V furnizați de Control Hub și de Expansion
Hub. Principalul beneficiu al lor este creșterea specificațiilor de viteză și cuplu ale
servo-urilor, oferind un bonus de performanță cu costul a unui consum de curent puțin
mai mare.

<!-- de adaugat imagini -->

Servo Power Module (SPM) a fost primul apărut și prezintă două posibile probleme:

- Predispoziția la scurt circuit - pentru a evita asta este recomandată acoperirea
  conectorilor șurub și a porturilor rămase goale cu bandă adeziva, deoarece orice
  reziduu metal poate provoca un scurt circuit.
- Curentul total furnizat redus - curentul pe care îl poate furniza un SPM este de 15A.
  Scopul principal de utilizare al său este alimentarea de servo-uri cu consum ridicat,
  iar de exemplu servo-urile Axon și Plex care definesc această categorie au consumul
  maxim de câte 4A fiecare, astfel fiind limitat la alimentarea a 4 servo-uri în loc de
  maximul de 6. Aceasta nu este neapărat o problemă, deoarece consumul acestor
  servo-uri nu va atinge în mod realist 4A vreodată, însă este recomandat să tratăm totul
  ca în cazul extrem, pentru a evita apariția de defecțiuni foarte ușoare de prevenit.

Servo Hub-ul a venit ca o îmbunătățire asupra SPM-ului, rezolvând problemele de scurt
circuitare, simplificând procesul de cablare și aducând alte câteva feature-uri de finețe.
Curentul maxim este tot de 15A, însă după cum am spus, nu este o problemă în adevăratul
sens al cuvântului, doar o limitare care ar trebui respectată.

<!-- add images for everything -->

<hr>
