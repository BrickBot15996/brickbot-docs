# Brickbot-Docs Contributor Guide (Windows Only)

This guide provides step-by-step instructions for setting up your development environment to contribute to this MkDocs Material project. By following these steps, you'll be able to install dependencies, run the project locally, and make contributions.

## Prerequisites

Before setting up the project, ensure you have the following installed:

- [Visual Studio Code (VS Code)](https://code.visualstudio.com/download)
- [Python](https://www.python.org/downloads/)
- [pip](https://pip.pypa.io/en/stable/installation/)
- [Git](https://git-scm.com/downloads)
- [GitHub Desktop](https://desktop.github.com/) (optional)

### 1. Install Visual Studio Code (VS Code)

1. Download VS Code from [here](https://code.visualstudio.com/download).
2. Run the installer and follow the setup instructions.
3. During installation, ensure **"Add to PATH"** is checked.

### 2. Install Python and Add to PATH

1. Download the latest version of Python from [here](https://www.python.org/downloads/).
2. Run the installer.
3. Ensure you check the box **"Add Python to PATH"** before clicking "Install Now".
4. Verify installation by opening a command prompt (`Win + R`, type `cmd`, press Enter) and running:
   ```sh
   python --version
   pip --version
   ```

### 3. Upgrade pip (If Necessary)

After installing Python, upgrade `pip` to the latest version:

```sh
python -m pip install --upgrade pip
```

### 4. Install Git

1. Download Git from [here](https://git-scm.com/downloads).
2. Run the installer and follow the default setup.
3. Ensure **"Git Bash Here"** and **"Add to PATH"** options are checked.
4. Verify installation:
   ```sh
   git --version
   ```

## Cloning the Repository

You can clone the repository using either GitHub Desktop or Git.

### Option 1: Using GitHub Desktop

1. Install [GitHub Desktop](https://desktop.github.com/).
2. Open GitHub Desktop and sign in to your GitHub account.
3. Click **File > Clone repository**.
4. Select **"URL"**, paste the repository URL, and choose a local path.
5. Click **Clone**.

### Option 2: Using Git

1. Open a command prompt and navigate to your desired directory.
2. Clone the repository:
   ```sh
   git clone https://github.com/BrickBot15996/brickbot-docs.git
   cd brickbot-docs
   ```

## Installing Dependencies

Run the following command inside the project directory to install MkDocs and the Material theme:

```sh
pip install -r requirements.txt
```

If `requirements.txt` is missing, install manually:

```sh
pip install mkdocs mkdocs-material
```

## Running the Project Locally

Start the development server:

```sh
mkdocs serve
```

Open your browser and go to `http://127.0.0.1:8000/` to view the documentation.

## Making Contributions

### 1. Create a New Branch

Before making changes, create a new branch:

```sh
git checkout -b my-feature-branch
```

### 2. Make Changes and Test Locally

Edit the markdown files in the `docs/` folder and test them by running `mkdocs serve`.

### 3. Commit Changes

After making changes, commit them:

```sh
git add .
git commit -m "Describe your changes"
```

### 4. Push Your Branch

Push your branch to GitHub:

```sh
git push origin my-feature-branch
```

### 5. Open a Pull Request

1. Go to the repository on GitHub.
2. Click **"Compare & pull request"**.
3. Provide a clear title and description of your changes.
4. Submit the pull request.

## Additional Resources

- Markdown Syntax Guide: [https://www.markdownguide.org/](https://www.markdownguide.org/)
- MkDocs Official Documentation: [https://www.mkdocs.org/](https://www.mkdocs.org/)
- MkDocs Material Documentation: [https://squidfunk.github.io/mkdocs-material/](https://squidfunk.github.io/mkdocs-material/)

## Troubleshooting

### 1. `mkdocs` command not found

Ensure Python and pip are added to your system’s PATH. If not, manually add them:

1. Open Windows Search and type **"Environment Variables"**.
2. Click **"Edit the system environment variables"**.
3. Click **"Environment Variables"**.
4. Under **System Variables**, find `Path`, select it, and click **Edit**.
5. Click **New** and add the following paths (replace `X.Y` with your Python version):
   ```
   C:\Users\YourUsername\AppData\Local\Programs\Python\PythonX.Y\
   C:\Users\YourUsername\AppData\Local\Programs\Python\PythonX.Y\Scripts\
   ```
6. Click **OK** and restart your computer.

### 2. `pip install -r requirements.txt` fails

Run the following command to ensure you have the latest `pip`:

```sh
python -m pip install --upgrade pip
```

Then retry installing dependencies:

```sh
pip install -r requirements.txt
```

### 3. GitHub Pages Deployment Issues

Ensure you have Git installed and set up:

```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Then deploy using:

```sh
mkdocs gh-deploy
```

---
