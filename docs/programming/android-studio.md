# **Android Studio**

## **Ce este Android Studio?**

Android Studio este un IDE (Integrated Development Environment - Mediu de
dezvoltare) conceput de Google pentru a oferi o serie de feature-uri foarte utile
pentru developeri. Deoarece sistemul de control folosește o variantă de Android
ca sistem de operare, aplicația pe care o realizăm pentru a controla robotul
trebuie să ruleze și ea pe Android.

<!--prettier-ignore-start-->
!!! info
    Java este un limbaj destul de pretențios din punct de vedere al structurii
    proiectelor, iar de aceea acest IDE ne va ușura considerabil munca.
<!--prettier-ignore-end-->

<hr>

## **De ce avem nevoie?**

În primul rând, trebuie să descărcăm <a href="https://developer.android.com/studio" target="_blank">Android Studio</a>.

Apoi, avem nevoie de un JDK (Java Development Kit) pentru a putea construi proiecte Java.
În FTC, este folosită versiunea <a href="https://www.oracle.com/ro/java/technologies/javase/javase8-archive-downloads.html" target="_blank">Java 8</a>.

Pentru a facilita acomodarea cu mediul de lucru al FTC, recomand să descărcați proiectul <a href="https://github.com/FIRST-Tech-Challenge/FtcRobotController" target="_blank">ftcrobotcontroller</a>.
Acesta reprezintă aplicația de bază și mijlocul de comunicare cu aparatura aflată pe
robot. De asemenea, conține câteva exemple de programe pentru a vă arăta bazele programării
în FTC. Tot ceea ce vom face mai departe pentru a ne programa robotul, va veni în completarea
acestui proiect.

<!--prettier-ignore-start-->
!!! tip "GitHub"
    Pentru a putea facilita colaborarea între membrii departamentului de programare, este
    recomandat să vă faceți cont de <a href="https://github.com/" target="_blank">GitHub</a> și să vă descărcați <a href="https://desktop.github.com/download/" target="_blank">GitHub Desktop</a>.
    Pentru a înțelege mai bine cum funcționează tehnologia Git, recomand <a href="https://www.youtube.com/watch?v=8Dd7KRpKeaE&ab_channel=CoderCoder" target="_blank">acest</a> tutorial.
<!--prettier-ignore-end-->

<hr>

## **Componentele unui proiect Java**

Am menționat mai sus termenul de **JDK**. Acesta reprezintă un set de instrumente necesare
pentru dezvoltarea și rularea aplicațiilor Java. Fiecare versiune vine cu feature-uri
noi, fie pentru îmbunătățirea experienței dezvoltatorului, fie pentru a îmbunătăți
produsele finale care pot fi realizate. Cea mai recentă versiune este Java 24. Poate
vă întrebați de ce folosim Java 8? În industrie, Java 8 și Java 11 sunt considerate cele
mai **stabile** versiuni, iar fiind mai vechi, oferă **compatibilitate** cu aparatură mai
veche, cum ar fi sistemul de control al roboților FTC.

**Gradle** este un sistem de gestionare al dependențelor (pachete externe de cod). Java este un
limbaj în care se scrie foarte mult **boilerplate** (cod repetitiv, dar necesar), care a fost
deseori scris și publicat deja de alte persoane, astfel Java devenind foarte dependent de
pachete externe. De aceea, este necesar un sistem precum Gradle.

<!--prettier-ignore-start-->
!!! danger "Actualizare Gradle"
    Nu ar trebui să actualizați versiunea de gradle în cadrul proiectului vostru pentru
    FTC. Deseori veți primi un pop-up pentru a face asta, însă nu îl ascultați. Actualizarea
    va distruge compatibilitatea proiectului cu dependențele, iar retrogradarea versiunii 
    poate fi dificilă de făcut.
<!--prettier-ignore-end-->

O noțiune pe care s-ar putea să o întâlniți când navigați prin Android Studio este **JVM**.
JVM sau Java Virtual Machine este componenta care oferă acestui limbaj **portabilitatea**
pe care o are. Codul este compilat în **bytecode** (format universal de instrucțiuni) care
poate rula pe o varietate de sisteme de operare cu ajutorul mașinii virtuale Java. Această
portabilitate este unul dintre **atuurile principale** ale Java.

<hr>
