# QUADRIGA OER Template

This is the template repository for [QUADRIGA](https://quadriga-dk.github.io) OERs created using [Jupyter Book](https://jupyterbook.org).

## How to use the Template

Duplicate the whole folder `book` into a new folder with the name of your book. You could use the command `cp -R book MY_PROJECT`.

Then change the file `_config.yml` to fit the new book.

Text you write has to be in Markdown, MyST oder Jupyter Notebook format. To present it in the book you need to link to each file in the `_toc.yml`. 

## Local development

We recommend the following procedure:
- Install [Anaconda](https://www.anaconda.com/download) following the instructions for your operating system.
- Clone the repository: `git clone https://github.com/schnaitter/TemplateBook`
- In the root folder of the repository create a (local) conda environment: `conda create -p conda python=3`.
- Activate the environment with `conda activate ./conda` (and check which installation of pip is used: `which pip`).
- Then install the requirements: `pip install -r book/requirements.txt`.
- This installed the requirements for the example books as well as Jupyter Books itself. Now you can build a Jupyter Book locally with `jb build book`.
  - If it does't work, check if you use the correct version of Jupyter Book with `which jb`. If it is not the correct one deactivate the environment with `conda deactivate` and then reactivate it again with `conda activate ./conda`
  - It can be helpful to clean up before you build with e.g.: `jb clean book && jb build book`.
- You can run a local server to see, what the book looks like. Use for example Pythons builtin HTTP server. In a new terminal run the following commands.
  ```bash
  cd book/_build/html/
  python3 -m http.server
  ```
  This serves the files in the subdirectory `book/_build/html/`. To view them use a browser and go to `http://localhost:8000`.


## License
The contents of this repository are licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

