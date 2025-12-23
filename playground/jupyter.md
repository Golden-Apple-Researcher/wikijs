---
title: Jupyter
description: Das Jupyter Universum
published: 1
date: 2025-12-23T23:22:22.613Z
tags: 
editor: markdown
dateCreated: 2025-12-23T10:13:06.162Z
---

[Jupyter](https://docs.jupyter.org/en/latest/) umfasst nicht nur [Notebooks](https://jupyter-notebook.readthedocs.io/en/latest/), sondern ist ein ganzes Universum fuer sich. Prinzipiell baut es auf dem IPykernel auf und bietet entweder [Jupyter Notebooks](https://docs.jupyter.org/en/latest/use/use-cases/narrative-notebook.html) oder das [JupyterLab](https://jupyterlab.readthedocs.io/en/latest/) als Userinterface an. Die lassen sich dann z.b. ueber einen Single User Server, den [JupyterHub](https://docs.jupyter.org/en/latest/use/use-cases/narrative-hub.html) fuer multiuser oder im Browser als [JupyterLite](https://jupyterlite.readthedocs.io/en/stable/) betreiten. Und neben der urspruenglichen [IPython](https://docs.jupyter.org/en/latest/reference/ipython.html) Runtime gibts mittlerweile auch fuer diverse andere Sprachen [passende Kernel](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels). 

Praktisch ist das halt dort, wo ein schnelles Feedback wichtig ist. Im gegensatz zu einer REPL hat man den ganzen Script-Verlauf vor sich und kann bei Bedarf einzelne Werte anpassen und ab da noch einmal laufen lassen. Ich nutze das gerne, wenn ich irgendwelche Scraper bastel, die dann zuerst mal eine HTML Suppe zurueckgeben und via xpath mal rausgetest wird, was fuer elemente mitgefiltert werden. 

Ein anderer haeufiger Einsatzzweck sind LLMs, da es dort meist eher darum geht Parameter fuers Feintuning zu bestimmen, aber man nicht so beschraenkt wie bei einem Config File ist. Siehe z.b. [Unsloth](https://docs.unsloth.ai) mit ihren [Notebooks](https://docs.unsloth.ai/get-started/unsloth-notebooks). 

Aber auch um etwas zu erklaeren sind Notebooks natuerlich praktisch. Hier ein Beispiel eines JupyterLite Notebooks, dass im Browser laeuft und als [Github Page](https://github.com/golden-Apple-Research/jupyterlite/) gehostet wird. Das Notebook nutzt einen JS Kernel fuer das [P5js](https://p5js.org/) Framework. 

<iframe src="https://golden-apple-research.github.io/jupyterlite/notebooks/index.html?path=p5.ipynb&theme=JupyterLab Dark" 
        width="100%" 
        height="1000px"
        ></iframe>