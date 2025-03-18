# Ghid pentru Contribuitori MkDocs Material (Doar Windows)

Acest ghid oferă instrucțiuni pas cu pas pentru configurarea mediului de dezvoltare necesar pentru a contribui la acest proiect MkDocs Material. Urmând acești pași, vei putea instala toate dependințele, rula proiectul local și contribui eficient.

## Cerințe preliminare

Înainte de a configura proiectul, asigură-te că ai instalate următoarele:

- [Visual Studio Code (VS Code)](https://code.visualstudio.com/download)
- [Python](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- [Git](https://git-scm.com/downloads)
- [GitHub Desktop](https://desktop.github.com/) (opțional)

### 1. Instalarea Visual Studio Code (VS Code)

1. Descarcă VS Code de [aici](https://code.visualstudio.com/download).
2. Rulează instalatorul și urmează instrucțiunile de configurare.
3. În timpul instalării, asigură-te că **"Add to PATH"** este bifat.

### 2. Instalarea Python și Adăugarea în PATH

1. Descarcă cea mai recentă versiune de Python de [aici](https://www.python.org/downloads/).
2. Rulează instalatorul.
3. Asigură-te că bifezi opțiunea **"Add Python to PATH"** înainte de a apăsa "Install Now".
4. Verifică instalarea deschizând Command Prompt (`Win + R`, scrie `cmd`, apasă Enter) și rulează:
   ```sh
   python --version
   pip --version
   ```

### 3. Actualizarea pip (Dacă este necesar)

După instalarea Python, actualizează `pip` la cea mai recentă versiune:

```sh
python -m pip install --upgrade pip
```

### 4. Instalarea Git

1. Descarcă Git de [aici](https://git-scm.com/downloads).
2. Rulează instalatorul și urmează setările implicite.
3. Asigură-te că bifezi **"Git Bash Here"** și **"Add to PATH"**.
4. Verifică instalarea:
   ```sh
   git --version
   ```

## Clonarea Repozitoriului

Poți clona repo-ul folosind GitHub Desktop sau Git.

### Opțiunea 1: Utilizând GitHub Desktop

1. Instalează [GitHub Desktop](https://desktop.github.com/).
2. Deschide GitHub Desktop și autentifică-te în contul tău GitHub.
3. Apasă **File > Clone repository**.
4. Selectează **"URL"**, introduce URL-ul repo-ului și alege o locație pe disc.
5. Apasă **Clone**.

### Opțiunea 2: Utilizând Git

1. Deschide Command Prompt și navighează la directorul dorit.
2. Clonează repo-ul:
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

Înainte de a face modificări, creează o ramură nouă:

```sh
git checkout -b my-feature-branch
```

### 2. Modificarea și Testarea Locală

Editează fișierele markdown din folderul `docs/` și testează modificările rulând `mkdocs serve`.

### 3. Comitează Modificările

După ce ai făcut modificările, salvează-le prin commit:

```sh
git add .
git commit -m "Descrierea modificărilor"
```

### 4. Trimite Ramura pe GitHub

Publică ramura pe GitHub:

```sh
git push origin my-feature-branch
```

### 5. Creează un Pull Request

1. Mergi la repo-ul pe GitHub.
2. Apasă **"Compare & pull request"**.
3. Completează un titlu și o descriere clară a modificărilor.
4. Trimite pull request-ul.

## Resurse Suplimentare

- Ghid Sintaxă Markdown: [https://www.markdownguide.org/](https://www.markdownguide.org/)
- Documentația Oficială MkDocs: [https://www.mkdocs.org/](https://www.mkdocs.org/)
- Documentația MkDocs Material: [https://squidfunk.github.io/mkdocs-material/](https://squidfunk.github.io/mkdocs-material/)

## Depanare

### 1. Comanda `mkdocs` nu este recunoscută

Asigură-te că Python și pip sunt adăugate în variabila PATH. Dacă nu, adaugă-le manual:

1. Deschide Windows Search și scrie **"Environment Variables"**.
2. Apasă **"Edit the system environment variables"**.
3. Apasă **"Environment Variables"**.
4. Sub **System Variables**, găsește `Path`, selectează-l și apasă **Edit**.
5. Apasă **New** și adaugă următoarele căi (înlocuiește `X.Y` cu versiunea ta de Python):
   ```
   C:\Users\YourUsername\AppData\Local\Programs\Python\PythonX.Y\
   C:\Users\YourUsername\AppData\Local\Programs\Python\PythonX.Y\Scripts\
   ```
6. Apasă **OK** și repornește computerul.

### 2. `pip install -r requirements.txt` eșuează

Asigură-te că ai cea mai recentă versiune de `pip`:

```sh
python -m pip install --upgrade pip
```

Apoi încearcă din nou instalarea dependențelor:

```sh
pip install -r requirements.txt
```

### 3. Probleme cu Deploy pe GitHub Pages

Asigură-te că ai configurat Git corect:

```sh
git config --global user.name "Numele Tău"
git config --global user.email "emailul.tau@example.com"
```

Apoi publică folosind:

```sh
mkdocs gh-deploy
```

---

Acest README servește drept ghid pentru viitorii contribuitori. Dacă întâmpini probleme, consultă documentația oficială sau deschide un issue în repo!
