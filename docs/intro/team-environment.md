# **Organizarea echipei**
## **Cadru organizațional**

### Structura organizațională pe roluri

``` mermaid
graph LR;
    R{{Recrut}} -.-> Membru
    R{{Recrut}} -.-> Voluntar
    C([Team Leader])-->A([Coordonator Non-Tehnic])
    C([Team Leader])-->B([Coordonator Tehnic])
    A([Coordonator Non-Tehnic])-->n1(Membrii și recruți din departamentele non-tehnice)
    B([Coordonator Tehnic])-->id1(Membrii și recruți departamentele tehnice)
```

### Structura organizațională pe departamente, secțiuni și roluri importante
``` mermaid
graph LR;
    C([Team Leader]) --> A([Coordonator Non-Tehnic])
    C --> B([Coordonator Tehnic])
    
    A --> NT(Non-Tehnic)
    NT --> PR(Public Relations)
    NT --> GF(Grafică și Fotografie)
    
    B --> T(Tehnic)
    T --> M3D(Mecanică & 3D)
    T --> P(Programare)
    T --> DT(Driving Team)
```

## **Mediul de lucru**

``` mermaid
graph TB;
    Mediu-->Fizic
    Mediu-->Online
    Fizic-->Laborator
    Fizic-->Sală
    Online-->WhatsApp
    Online-->a(Google Meet)
    Online-->Discord
    Online-->GitHub
    Online-->b(Google Drive)
```


### **Online**

| Platformă     | Descriere                        |
| -------------- | ---------------------------------|
| :simple-whatsapp: **WhatsApp**         | Canalul principal de comunicare. Aici se postează anunțuri și stabilim cele mai importante detalii  |
| :simple-googlemeet: **Google Meet**        | Cele mai multe ședințe online aici se desfășoară |
| :material-google-drive: **Google Drive**     | În Drive-ul echipei se află materiale pentru PR, documente și poze organizate pe ani. Nu toți au acces la Drive |
| :material-github: **GitHub**     | Realizăm diverse proiecte, cum ar fi acest ghid sau codul robotului! |
| :simple-discord: **Discord**      | Platforma unde (foarte des) au loc sesiuni de lucru împreună. Aici nu se organizează ședințe |