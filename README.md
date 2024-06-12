# QUADRIGA OER Template

_english below_

Dieses Repositorium dient als Vorlage für [QUADRIGA](https://quadriga-dk.github.io) OERs, die mit [Jupyter Book](https://jupyterbook.org) geschrieben werden.

## Nutzung der Vorlage

Erstelle ein neues Repositorium mit dem Namen des neuen Buchs in der quadriga-dk-Organisation. Kopiere die Inhalte dieses Repositoriums (bspw. Download als .zip-Datei) in das neue Repositorium und passe die Dateien `_config.yml`, `_toc.yml` sowie ggf. die Datei `.github/workflows/deploy-book.yml` auf Dein neues Buch an. Achte darauf, dass Dein neues Buch in einer möglichen lokalen Version keine Git-Verbindung mehr zur Vorlage hat.

Alternativ kannst Du auch das Repositorium der Vorlage forken und dann die obigen Änderungen vornehmen. Dann musst Du allerdings aufpassen, welche Änderungen von Upstream Du übernehmen willst.

Übernimm Änderungen im Styling/Layout in der Vorlage auch in Deinem Buch. Bei wichtigen Änderungen wird ggf. auch ein Pull-Request an deine Bücher gestellt werden.

### Erstellung der Inhalte

Jupyter Book kann standardmäßig Inhalte verarbeiten, die in Markdown, MyST und Jupyter Notebook geschrieben wurden. Inhalte werden in der Website nur angezeigt, wenn sie in `_toc.yml` explizit in die Struktur aufgenommen wurden.

## Lokale Entwicklung

Ist die Github Action für Github Pages korrekt konfiguriert, so ist die Arbeit in der Github-Oberfläche möglich, wenn auch mit großen Wartezeiten verbunden. Allerdings empfehlen wir immer eine lokale "Entwicklungsumgebung".

Wir empfehlen Dir dieses Vorgehen:
- Installiere [Anaconda](https://www.anaconda.com/download) um eine Python-Umgebung auf deinem Rechner zu installieren. Falls Du schon eine Python-Umgebung hast kannst Du diesen Schritt überspringen.
- Klone das Repositorium, an dem Du arbeiten willst. Bspw.: `git clone https://github.com/quadriga-dk/Book_Template`
- In einem Terminal, wechsle in den Order des Repositoriums und erstelle ein lokales "virtual environment". (Wir nutzen `conda`, aber andere Tools sind möglich, falls Du schon mit diesen vertraut bist.) Führe dazu aus: `conda create -p conda python=3`. Dies erstellt ein neue neue Virtuelle Umgebung im Ordner `./conda/` in dem alle für dein Buch notwendigen Bibliotheken installiert werden. (Der Ordner `conda` wird nicht in Git versioniert, sodass die jeweils korrekte Version aller Software für Dein Betriebssystem installiert werden kann.)
- Aktiviere nun die Virtuelle Umgebung mit `conda activate ./conda` (und überprüfe, ob alles funktioniert hat mit `which pip`.)
- Installiere dann die für dein Buch benötigte Software mit `pip install -r requirements.txt`.
  - Es kann nötig sein, dass Du nach der Installation einmal die Umgebung deaktivierst und wieder aktivierst, damit Du auf alle Software zugreifen kannst. Das geht mit `conda deactivate` gefolgt von `conda activate ./conda`.
- Nun hast Du alle Anforderungen installiert und Du kannst das Jupyter Book lokal generieren mit `jb build .`.
  - Machmal kann es nötig sein "aufzuräumen", bevor Du eine neue Version generierst. Das geht mit `jb clean .`. Du kannst auch beide Befehle nacheinander ausführen mit `jb clean . && jb build .`.
- Die generierte HTML-Version des Buchs kannst Du nun unter `_build/html/` finden. Um die Entwicklung zu beschleunigen kann es hilfreich sein, wenn Du das Buch über einen lokalen HTTP-Server in deinem Browser verfügbar machst. Öffne dazu ein neues Terminal(-Fenster) und führe diesen Befehl aus: `python3 -m http.server -d _build/html/`. Dies startet einen HTTP-Server, der die Inhalte des HTML-Ordners (standardmäßig) unter `http://localhost:8000/` anbietet.

# Enlish version
_german above_

This is the template repository for [QUADRIGA](https://quadriga-dk.github.io) OERs created using [Jupyter Book](https://jupyterbook.org).

## How to use the Template

Duplicate the repository into a new folder with the name of your book. You could use the command `cp -R Book_Template MY_PROJECT`. Or you can fork the repository. You need do be certain to either delete the `.git`-folder and re-initialize git or to change remotes to point to a new repository, if you copied.

Then change the file `_config.yml` to fit the new book.

Any text you write has to be in Markdown, MyST oder Jupyter Notebook format. To present it in the book you need to link to each file in the `_toc.yml`. 

## Local development

We recommend the following procedure:
- Install [Anaconda](https://www.anaconda.com/download) following the instructions for your operating system.
- Clone the repository: `git clone https://github.com/quadriga-dk/Book_Template`
- In the root folder of the repository create a (local) conda environment: `conda create -p conda python=3`.
- Activate the environment with `conda activate ./conda` (and check which installation of pip is used: `which pip`).
- Then install the requirements: `pip install -r requirements.txt`.
- This installed the requirements for the example books as well as Jupyter Books itself. Now you can build a Jupyter Book locally with `jb build .`.
  - If it does't work, check if you use the correct version of Jupyter Book with `which jb`. If it is not the correct one deactivate the environment with `conda deactivate` and then reactivate it again with `conda activate ./conda`
  - It can be helpful to clean up before you build with e.g.: `jb clean . && jb build .`.
- You can run a local server to see, what the book looks like. Use for example Pythons builtin HTTP server. In a new terminal run the following command.
  ```bash
  python3 -m http.server -d _build/html/
  ```
  This serves the files in the subdirectory `_build/html/`. To view them use a browser and go to `http://localhost:8000`.

