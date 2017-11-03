---
layout: post
title: "Python 3 Venv Wrapper"
description: "Simple venv wrapper for Python 3 venv"
category: Development
tags: [python, python3, venv, virtual, environment, wrapper]
---
{% include JB/setup %}

If you followed Python tutorials or used Python in a project you most probably came across use of virtual environments.

Most OSs include a version of Python. At the time of writing MacOS Sierra has Python 2.7.10. If you use system Python you install all dependencies to `/usr/lib/python2.7/site-packages`. This causes not only permission problems, but also compatibility issues.

virtualenv says,
>Imagine you have an application that needs version 1 of LibFoo, but another application requires version 2. How can you use both these applications? If you install everything into /usr/lib/python2.7/site-packages (or whatever your platform’s standard location is), it’s easy to end up in a situation where you unintentionally upgrade an application that shouldn’t be upgraded.

With that need in mind [virtualenv](https://virtualenv.pypa.io/en/stable/) module and [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/) was being used. In current version of Python, `venv` module can ve used instead. It creates a virtual environment isolated from system site directories.

The difference in venv, it creates virtual environment inside the project directory. I published a small [script](https://gist.github.com/dbtek/fb2ddccb18f0cf63a654ea2cc94c8f19) to simulate what virtualenvwrapper does, but with venv module. It simply manages virtual environments under `~/.venv/` directory.

Usage:  
- `$ mkvenv myvirtualenv` creates a virtual environment unde `~/.venv`.
- `$ venv myvirtualenv` activates virtual environment.
- `$ deactivate` deactivates virtual environment.
- `$ rmvenv myvirtualenv` removes virtual environment.

Find the script in [this gist](https://gist.github.com/dbtek/fb2ddccb18f0cf63a654ea2cc94c8f19), include it in .bash_profile / .bashrc / .zshrc file and start using.
