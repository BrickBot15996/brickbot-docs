# Ghid pentru Contribuitori MkDocs Material (Windows Only)

Acest ghid oferă instrucțiuni pas cu pas pentru configurarea mediului de dezvoltare necesar pentru a contribui la acest proiect MkDocs Material. Urmând acești pași, vei putea instala toate dependințele, rula proiectul local și contribui eficient.

## Cerințe Prealabile

Înainte de a începe, asigură-te că ai instalat următoarele:

- [Visual Studio Code (VS Code)](https://code.visualstudio.com/download)
- [Python](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- [Git](https://git-scm.com/downloads)
- [GitHub Desktop](https://desktop.github.com/) (opțional)

### 1. Instalare Visual Studio Code (VS Code)

1. Descarcă VS Code de [aici](https://code.visualstudio.com/download).
2. Rulează instalatorul și urmează instrucțiunile.
3. În timpul instalării, asigură-te că opțiunea **"Add to PATH"** este bifată.

### 2. Instalare Python și Adăugare în PATH

1. Descarcă ultima versiune de Python de [aici](https://www.python.org/downloads/).
2. Rulează instalatorul.
3. Bifează opțiunea **"Add Python to PATH"** înainte de a apăsa „Install Now”.
4. Verifică instalarea deschizând Command Prompt (`Win + R`, tastează `cmd`, apasă Enter) și rulează:
   ```sh
   python --version
   pip --version
   ```

### 3. Actualizare pip (Dacă Este Necesare)

După instalarea Python, actualizează `pip` la cea mai recentă versiune:

```sh
python -m pip install --upgrade pip
```

### 4. Instalare Git

1. Descarcă Git de [aici](https://git-scm.com/downloads).
2. Rulează instalatorul și urmează pașii de instalare.
3. Asigură-te că opțiunile **"Git Bash Here"** și **"Add to PATH"** sunt bifate.
4. Verifică instalarea:
   ```sh
   git --version
   ```

## Clonarea Repozitoriului

Poți clona repo-ul folosind GitHub Desktop sau Git.

### Opțiunea 1: Folosind GitHub Desktop

1. Instalează [GitHub Desktop](https://desktop.github.com/).
2. Deschide GitHub Desktop și autentifică-te în contul GitHub.
3. Click pe **File > Clone repository**.
4. Selectează **"URL"**, introdu URL-ul repo-ului și alege o locație locală.
5. Apasă **Clone**.

### Opțiunea 2: Folosind Git

1. Deschide Command Prompt și navighează la directorul dorit.
2. Clonează repo-ul cu comanda:
   ```sh
   git clone https://github.com/BrickBot15996/brickbot-docs.git
   cd brickbot-docs
   ```

## Instalarea Dependențelor

Rulează următoarea comandă în directorul proiectului pentru a instala MkDocs și tema Material:

```sh
pip install -r requirements.txt
```

Dacă `requirements.txt` lipsește, instalează manual:

```sh
pip install mkdocs mkdocs-material
```

## Rularea Proiectului Local

Pornește serverul de dezvoltare:

```sh
mkdocs serve
```

Deschide browserul și accesează `http://127.0.0.1:8000/` pentru a vizualiza documentația.

## Contribuirea la Proiect

### 1. Crearea unei Ramuri Noi

**Cu Git:**

```sh
git checkout -b branch-name
```

**Cu GitHub Desktop:**

1. Deschide GitHub Desktop.
2. Asigură-te că repo-ul este selectat.
3. Click pe **Current Branch** și selectează **New Branch**.
4. Introdu un nume pentru branch și apasă **Create Branch**.

### 2. Efectuarea Modificărilor și Testarea Locală

Editează fișierele Markdown din folderul `docs/` și testează modificările rulând `mkdocs serve`.

### 3. Realizarea Commit-urilor

**Cu Git:**

```sh
git add .
git commit -m "Descrierea modificărilor"
```

**Cu GitHub Desktop:**

1. În GitHub Desktop, modificările tale vor apărea automat.
2. Completează câmpul „Summary” cu o descriere a modificărilor.
3. Apasă **Commit to branch-name**.

### 4. Trimiterea Modificărilor

**Cu Git:**

```sh
git push origin branch-name
```

**Cu GitHub Desktop:**

1. Asigură-te că ești pe branch-ul corect.
2. Click pe **Push origin** pentru a trimite modificările pe GitHub.

### 5. Crearea unui Pull Request

1. Mergi pe pagina repo-ului pe GitHub.
2. Click pe **"Compare & pull request"**.
3. Oferă un titlu clar și o descriere a modificărilor.
4. Apasă **Submit pull request**.

## Resurse Suplimentare

- Ghid sintaxă Markdown: [https://www.markdownguide.org/](https://www.markdownguide.org/)
- Documentație MkDocs: [https://www.mkdocs.org/](https://www.mkdocs.org/)
- Documentație MkDocs Material: [https://squidfunk.github.io/mkdocs-material/](https://squidfunk.github.io/mkdocs-material/)

## Depanare

### 1. Comanda `mkdocs` nu este recunoscută

Asigură-te că Python și pip sunt adăugate în variabila `PATH`. Dacă nu, adaugă-le manual:

1. Deschide Windows Search și caută **"Environment Variables"**.
2. Click pe **"Edit the system environment variables"**.
3. Click pe **"Environment Variables"**.
4. La **System Variables**, selectează `Path`, apoi **Edit**.
5. Click **New** și adaugă căile (înlocuiește `X.Y` cu versiunea ta de Python):
   ```
   C:\Users\NumeleTău\AppData\Local\Programs\Python\PythonX.Y\
   C:\Users\NumeleTău\AppData\Local\Programs\Python\PythonX.Y\Scripts\
   ```
6. Click **OK** și repornește calculatorul.

### 2. `pip install -r requirements.txt` eșuează

Rulează comanda pentru actualizarea `pip`:

```sh
python -m pip install --upgrade pip
```

Apoi reinstalează dependențele:

```sh
pip install -r requirements.txt
```

### 3. Probleme cu publicarea pe GitHub Pages

Asigură-te că Git este configurat corect:

```sh
git config --global user.name "Numele Tău"
git config --global user.email "emailul.tau@example.com"
```

Apoi publică folosind:

```sh
mkdocs gh-deploy
```

---

Acest README servește drept ghid pentru contribuitori. Dacă întâmpini probleme, consultă documentația oficială sau deschide un issue în repo!
