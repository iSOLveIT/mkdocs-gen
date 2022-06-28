# Breadboard Mates Documentation Generator

This repository serves as a document generator for Breadboard Mates. It uses MkDocs which supports building into web and PDF documents. Both web and pdf documentation are automatically updated when changes are made to the repository assuming no error is found.

## Setting up in Windows

The following discusses how to setup a Windows machine to write and test documentation before deploying to the main branch.

Install latest Python from the [Microsoft Store](https://www.microsoft.com/en-us/search?q=python)

Install [GTK for Windows](https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer/releases)

Clone the repository

    git clone https://github.com/BreadBoardMates/Breadboard-Mates-Resources.git

Create virtual environment

    python -m venv venv

Activate virtual environment

    venv\Scripts\activate

Install all requirements in virtual environment

    pip install -r requirements.txt

Try running/serving the mkdocs

    mkdocs serve

Open your browser and go to [localhost:8000 or 127.0.0.1:8000](http://localhost:8000)

## Updating Documentation

TODO