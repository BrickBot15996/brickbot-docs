# **Componente mecanice**

## **Rulmenți**

Rulmenții sunt componente mecanice care ajută piesele care se rotesc să se
miște mai ușor și mai eficient, reducând frecarea dintre ele. Rulmenții pot
lua foarte multe forme, însă principalele 4 tipuri pe care le vom întâlni sunt:

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/flanged-bearing.png" alt="Rulment cu flanșă" width="100%">
   <p style="text-align:center"><strong>Rulment cu flanșă</strong></p>
 </div>

 <div>
   <img src="../media/non-flanged-bearing.png" alt="Rulment fără flanșă" width="100%">
   <p style="text-align:center"><strong>Rulment fără flanșă</strong></p>
 </div>

 <div>
   <img src="../media/v-groove-bearing.png" alt="Scripete" width="100%">
   <p style="text-align:center"><strong>Scripete</strong></p>
 </div>

 <div>
   <img src="../media/linear-bearing.png" alt="Rulment liniar" width="100%">
   <p style="text-align:center"><strong>Rulment liniar</strong></p>
 </div>

</div>

Scopul flanșei este să faciliteze fixarea rulmenților.

<hr>

## **Axuri**

Axurile sunt tije ce permit mișcarea de rotație a unor componente. Acestea diferă
fie prin formă, fie prin materialul din care sunt făcute, fie prin dimensiuni, însă
cea mai importantă distincție estie modul în care realizează mișcarea de rotație.

#### **Ax viu**

Axul viu este cea mai simplă metodă de transmisie de putere. În acest scenariu,
componentele se rotesc odată cu axul, axul fiind montat de obicei pe doi rulmenți,
unul în fiecare capăt. Este recomandată folosirea axului viu când dorim să angrenăm
mai multe componente deodată.

<!--prettier-ignore-start-->
!!! warning "Constrângerea axului viu"
    Nu este recomandată montarea / constrângerea unui ax viu folosind mai mult sau
    mai puțin de 2 rulmenti. În cazul constrângerii cu un singur rulment, se pierde
    foarte multă rigiditate. În cazul montării folosind mai mult de 2 rulmenți,
    orice eroare mică de aliniere în manufactura pieselor sau asamblarea robotului
    poate duce la o pierdere foarte mare de eficiență.
<!--prettier-ignore-end-->

#### **Ax mort**

Axul mort constă într-un ax fixat, iar componentele se rotesc în jurul acestuia.
Principalul avantaj al acestui tip de transmisie este bonusul de rigiditate adus
de axul mort. Pentru a realiza acest tip de transmisie, trebuie ca rulmenții să
susțină componentele amplasate pe ax, nu axul în sine.

<!--prettier-ignore-start-->
!!! tip "Sfat"
  În general, este preferată folosirea axurilor moarte pe oriunde este posibil.
<!--prettier-ignore-end-->

#### **Ax zombie**

Axul "zombie" reprezintă o combinație dintre cele două. Ce înseamnă? Practic, unele
componente folosesc axul ca pe un ax viu, altele ca pe un ax mort. Axul zombie permite
angrenarea mai multor mecanisme pe același punct de rotație.

<hr>

## **Elemente de transmisie**

Până acum am mai folosit termenul transmisie de câteva ori. Transmisia reprezintă
transmiterea mișcării de rotație între două puncte. Aceasta se poate realiza în mai
multe moduri:

#### **Roți dințate**

Roțile dințate sunt cel mai comun și simplu mod de a realiza o transmisie. Ceva de
care ar trebui totuși să ținem cont este faptul că un număr par de roți dințate
inversează direcția de rotație la capăt.

<!--add image-->

Pentru a putea alege roțile dințate potrivite ar trebui să cunoaștem următoarele
concepte:

- Pitch Diameter - ne arată distanța la care putem pune două roți dințate cu
  aceleași specificații. Dacă diferă numărul de dinți între cele două roți
  putem face media aritmetică a acestor diametre pentru a determina noua
  distanță potrivită între ele.
- MOD - reprezintă "distanța" dintre dinți. Un mod mai mic înseamnă că dinții
  sunt mai apropiați, oferind un joc mai mic. Un mod mai mare înseamnă că roata
  dințată poate fi supusă unor forțe mai mari.
- DP (Diametral Pitch) - este practic o alta formă a MOD-ului. În general, vom
  lucra cu roți dințate de MOD 0.8, iar acestea sunt **aproape** la fel cu roțile
  de 32 DP. Diferența dintre ele este suficient de mică încât pot fi cuplate
  împreună.

Ce ar trebui să sțim despre acest tip de transmisie? Principalul avantaj față de
celelalte pe care le vom discuta este eficiența. O transmisie pe roți dințate este
cea mai eficientă pe care o vom putea folosi. Marele dezavantaj este că nu permite
ca distanța de transmisie să fie prea mare.

<!--yap about bevels and worm gears-->

#### **Lanț**

Al doilea tip de transmisie pe care îl putem folosi este cea pe lanț. Marele
avantaj al transmisiilor pe lanț este customizabilitatea. În orice moment putem
adăuga sau scoate câteva bucăți de lanț pentru a atinge distanța dorită, indiferent
cât de mare ar fi ea. Totuși, în ciuda acestui avantaj, nu este folosit prea des.
Marea problemă a lanțului este tensionarea. Dacă este prea slab tensionat,
mecanismul va avea foarte mult joc. Daca este prea tare tensionat, eficiența va fi
teribilă. Singurul scenariu în care lanțul excelează sunt mecanismele care necesită
un cuplu destul de mare, și nu suferă prea tare din cauza lipsei de eficiență. Un
lanț tensionat foarte tare, deși pierde mult din eficiență, câștigă foarte mult în
precizie.

<!--do some yap about sprockets but i dont know anything about them in romanian-->
<!--also add pictures-->

#### **Curele**

Tipul de transmisie pe care probabil o să îl folosim cel mai des este cea pe curele.
Reprezintă oareceum o cale de mijloc între roțile dințate și lanț. Din punct de vedere
al eficienței, dacă sunt tensionate corect stau mai bine decât transmisiile pe lanț,
iar tensionarea unei curele este mai ușoară. Din punct de vedere al distanței de
transmisie, nu este nici pe-aproape de customizabilitatea transmisiei pe lanț.

Există mai multe tipuri de curele, însă principalele două pe care le vom întâlni sunt:

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/timing-belt.png" alt="Curea dințată" width="100%">
   <p style="text-align:center"><strong>Curea dințată</strong></p>
 </div>

 <div>
   <img src="../media/round-belt.png" alt="Curea rotundă" width="100%">
   <p style="text-align:center"><strong>Curea rotundă</strong></p>
 </div>

</div>

<!--prettier-ignore-start-->
!!! tip "Inversarea direcției de rotație"
  Dacă aveți nevoie de inversarea direcției de rotație, iar utilizarea roților dințate
  este incomodă, puteți folosi o curea rotundă întoarsă (practic în formă de 8). Țineți
  cont totuși că se bazează doar pe frecare, iar la forțe mai mari nu va face față.
<!--prettier-ignore-end-->

Curelele dințate sunt foarte întâlnite la tot felul de mecanisme. În general, nu e foarte
bine să fie folosite la mecanisme cu cuplu foarte mare, deoarece apare riscul de a scăpa
dinți.

Pentru a ne ajuta cu tensionarea curelelor dințate, putem folosi calculatorul de pe platforma
<a href="" target="_blank">ReCalc</a>. Pentru curelele rotunde, recomand fie folosirea unor
curele care nu sunt deja bucle și să le închidem noi la dimensiunea potrivită, fie realizarea
unor sketch-uri în OnShape pentru a estima circumferința adecvată de curea.

<hr>

## **Atașamente pe ax**

Atașamentele pe ax sunt piese care pot fi folosite pentru a fixa componente pe axuri. Ele
pot fi separate în două mari grupuri:

#### **Set-Screw**

Atașamentele set-screw se fixează prin strângerea unui șurub care se fixează împingându-se
în ax. În general, sunt întâlnite când vrem să atașăm lucruri mici, ce nu pot fi prinse
în alt mod. Este de preferat să evităm utilizarea lor pe cât posibil, din cauza urmelor
lăsate pe axuri.

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/set-screw-gear.png" alt="Roată dințată" width="100%">
   <p style="text-align:center"><strong>Roată dințată</strong></p>
 </div>

 <div>
   <img src="../media/set-screw-collar.png" alt="Stopper set-screw" width="100%">
   <p style="text-align:center"><strong>Stopper set-screw</strong></p>
 </div>

</div>

#### **Clamps**

Atașamentele tip clamp se fixează strângându-se de jur împrejurul axului. Acestea nu lasă
niciun fel de urmă pe ax, iar în general folosesc cel puțin 2 șuruburi, nefiind predispuse
desfacerii neintenționate.

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/sonic-hub.png" alt="Sonic Hub" width="100%">
   <p style="text-align:center"><strong>Sonic Hub</strong></p>
 </div>

 <div>
   <img src="../media/shaft-collar.png" alt="Stopper" width="100%">
   <p style="text-align:center"><strong>Stopper</strong></p>
 </div>

</div>

<hr>

## **Roți**

Roțile pot avea mai multe scopuri decât simpla deplasare a robotului pe teren. Ele pot fi
folosite și la colectarea și lansarea elementelor de joc. De asemenea, nu sunt limitate
la o clasică formă rotundă.

#### **Roți pentru deplasare**

De-a lungul timpului, șasiurile în FTC au trecut prin foarte multe etape, însă în momentul
de față este destul de clar care sunt cele mai bune variante pentru un robot competitiv.

##### **Roțile mecanum**

Roțile mecanum prezintă niște "rollere" amplasate la 45 de grade, care le fac să genereze
mișcare pe diagonală. Folosind 4 astfel de roți într-o anumită orientare permit robotului
să se deplaseze în toate direcțiile (față-spate, stânga-dreapta și rotație). Sunt cele mai
folosite roți datorită agilității pe care o oferă și simplității utilizării lor.

<!--images-->

##### **Roți omni**

Roțile omni au niște cilindri de-a lungul circumferinței lor pentru a putea fi mișcate pe
laterală fără a induce o frecare mare. Totuși, golurile dintre cilindri pot fi destul de
mari, iar de aceea sunt în general folosite 2 câte 2, dar cu un offset pentru ca cilindrii
uneia să acopere golurile celeilalte.

Cel mai des roțile omni sunt folosite fie în ansambluri de odometrie, fie la șasiuri de
tracțiune facilitând rotația.

##### **Roți de tracțiune**

Roțile de tracțiune, așa cum le sugerează numele, sunt foarte aderente. Sunt cel mai des
întâlnite în cadrul sezoanelor care implică foarte multă interacțiune între roboții
alianțelor opuse. După cum am menționat mai sus, sunt cuplate cu roți omni pentru a face
rotația mai ușoară.

Un produs de care ar trebui totuși să ținem cont este <a href="" target="_blank">gray grippy tread</a>.
Este o bandă foarte aderentă, mai aderentă decât orice roți de tracțiune găsite la furnizorii
principali care sunt legale în competiție. Pentru a o putea folosi, este necesară printarea
3D a roților. Această tehnică poate oferi câteva oportunități de design în contexte specifice.

#### **Roți pentru colectarea obiectelor**

"Roțile" pentru colectarea obiectelor nu sunt în general roți propriu-zise. Trăsătura lor
generală este flexibilitatea. Sunt în general făcute din materiale moi ce permit mularea pe
elementele de joc. Câteva exemple sunt:

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/gecko-wheel.png" alt="Roți Gecko" width="100%">
   <p style="text-align:center"><strong>Roți Gecko</strong></p>
 </div>

 <div>
   <img src="../media/compliant-wheel.png" alt="Roți compliant" width="100%">
   <p style="text-align:center"><strong>Roți compliant</strong></p>
 </div>
 
 <div>
   <img src="../media/intake-star.png" alt="Steluțe" width="100%">
   <p style="text-align:center"><strong>Steluțe</strong></p>
 </div>

 <div>
   <img src="../media/tubing-spinner.png" alt="Roți cu tub chirurgical" width="100%">
   <p style="text-align:center"><strong>Roți cu tub chirurgical</strong></p>
 </div>

</div>

Un alt lucru pe care îl mai putem face este printarea lor din TPU. TPU este un plastic
flexibil ce poate fi folosit la imprimanta 3D. Acest procedeu ne deschide foarte multe
oportunități când vine vorba de forma pe care le-o dăm pentru a putea gestiona orice
fel de element de joc, indiferent de forma pe care o are.

#### **Roți pentru lansarea elementelor**

O dată la câțiva ani, jocul FTC implica lansarea unor elemente de joc, deseori bile sau
discuri. Aceste forme ne permit utilizarea lansatoarelor de tip <a href="" target="_blank">flywheel</a>.
Un flywheel implică o roată care se rotește la o viteză foarte mare, pentru a imprima
viteză altor obiecte. Câteva trăsături relevante pentru un flywheel sunt aderența și
greutatea. De ce este importantă greutatea? Pentru că o roată grea, are mai multă inerție
și va pierde mai puțină viteză odata cu lansarea elementelor. Singurul dezavantaj este
timpul de accelerație pentru a aduce roata la viteză maximă, însă putem neglija asta
dacă ținem roata la o viteză mare pe toată durata meciului. Astfel, cele mai bune roți
de lansare pe care le avem la dispoziție sunt roțile de tracțiune de la Gobilda. Acestea
au un spațiu înăuntru în care putem atașa greutăți adiționale pentru a configura cum
dorim flywheel-ul nostru.

<hr>

## **Componente pentru mișcare liniară**

Mișcarea liniară este probabil cel mai des-întâlnit aspect în jocurile FTC, fie că
este vorba de înalțimi de 30cm sau de 1m. De aceea, este unul din elementele care fac
diferența între un robot bun și unul foarte bun. În principal, avem trei variante
foarte bune pentru a realiza mișcarea liniară:

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">

 <div>
   <img src="../media/linear-slides.png" alt="Glisiere" width="100%">
   <p style="text-align:center"><strong>Glisiere</strong></p>
 </div>

 <div>
   <img src="../media/linear-rail.png" alt="Șină liniară" width="100%">
   <p style="text-align:center"><strong>Șină liniară</strong></p>
 </div>
 
 <div>
   <img src="../media/box-tube.png" alt="Tub telescopic" width="100%">
   <p style="text-align:center"><strong>Tub telescopic</strong></p>
 </div>

</div>

#### **Glisiere**

Glisierele sunt cele mai populare și cele mai simple de utilizat. În general, constau
în 2 sau 3 nivele culisante ce se pot extinde în una sau ambele direcții. Cele mai
folosite glisiere sunt <a href="" target="_blank">Misumi Sar2XX</a>, deoarece permit
realizarea unui ansamblu ușor, compact și au găuri filetate făcând asamblarea mecanismelor
foarte ușoară.

#### **Șina liniară**

Șina liniară permite deplasarea de-a lungul unei tije, în general de oțel. Pot fi folosite
în combinație cu glisierele, deoarece dacă mecanismul este montat la baza glisierelor, șina
permite ridicarea până în partea de sus.

<!--insert-some-images to showcase this cause jesus christ it's hard to explain-->

#### **Tub telescopic**

<hr>
