# Calculator

A desktop calculator app with calculation history and export support, built with Flask and pywebview, and compiled into native `.deb` (Linux) and `.exe` (Windows) binaries via GitHub Actions.

## Features

- Clean calculator interface running in a native desktop window (no browser required)
- Automatic history of every calculation, saved to a local SQLite database
- Export your calculation history to **CSV**, **HTML**, or **Excel**
- Fully standalone binaries — no Python installation needed to run

## Download

Prebuilt binaries are generated automatically for every release tag via GitHub Actions:

1. Go to the [Actions tab](../../actions)
2. Open the latest successful **"Build for Multi-Platform Desktop"** workflow run
3. Download the artifact for your platform:
   - `desktop-ubuntu-latest` → contains the `.deb` package
   - `desktop-windows-latest` → contains the `.exe`

### Installing on Linux
```bash
sudo dpkg -i calculator.deb
calculator
```

### Running on Windows
Just double-click the `.exe` — no installation required.

## Tech Stack

- **Backend:** Python, Flask
- **Desktop window:** pywebview
- **Database:** SQLite
- **Data export:** pandas
- **Packaging:** Nuitka (standalone compilation), `dpkg-deb`
- **CI/CD:** GitHub Actions

## Building from source

```bash
git clone https://github.com/eyobzefere01-web/Calculator.git
cd Calculator
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
python GUI.py
```

## Building the binaries yourself

Push a version tag to trigger the GitHub Actions build pipeline:

```bash
git tag v1.0.0
git push origin v1.0.0
```

This compiles both the Linux `.deb` and Windows `.exe` automatically and uploads them as workflow artifacts.

## Project Structure

```
├── app.py                 # Flask app and routes
├── GUI.py                 # pywebview entry point
├── logics/
│   └── database.py        # SQLite database logic
├── templates/              # HTML templates
├── static/                 # CSS, JS, icons
└── .github/workflows/
    └── build.yml           # CI/CD build pipeline
```

## License

This project is open source. Feel free to use, modify, and share.

## Author

**Eyob**
