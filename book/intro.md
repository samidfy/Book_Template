# Welcome to your QUADRIGA OER

This template is intended for the creation of QUADRIGA OERs. It showcases the capabilities of the Jupyter Book platform and how we recommend using them for the creation of your OER.

If you want to know more details about Jupyter Book features, go to [the Jupyter Book documentation](https://jupyterbook.org).

## What is Jupyter Book and what is it's relation to Jupyter Notebooks?
Jupyter Book is a programm, that generates HTML files (or PDFs, …) based the content and structure you provide.

Jupyter Notebooks are executable documents that mix static elements like text (written in Markdown) and executable elements in so called cells, i.e. code. This code can be in severe programming languages. The code is executed in a so called kernel. When you execute a cell, the code is sent to the kernel which runs it and returns the results. Jupyter Notebooks then present the results inline with the rest of the content.

Jupyter Book can use Jupyter Notebooks as one of its content fileformats. When generating the book it will run the included Jupyter Notebooks before transforming them into the output format (HTML, PDF, …).

Jupyter Book is based on the documentation generator [Sphinx](https://www.sphinx-doc.org/en/master/).

## How to use this Template
A Jupyter Book consists of a configuration file (`_config.yml`), a table of contents (`_toc.yml`) and at least one content file in the formats Markdown, MyST or Jupyter Notebook.  Markdown files are always treated as MyST even, if you don't use any of its special features.

To create a new QUADRIGA OER you can fork this repository and make your changes. Or you can simply create a new repository and then copy the files of this repository.

## How to work on your QUADRIGA OER
You can clone the repository locally and then build the book and run it using a local web server. Or you can work directly in Github.

## Example Pages

```{tableofcontents}
```

