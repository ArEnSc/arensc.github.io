---
layout: post 
title: Python VirtualEnv
tags: [VirtualEnv, Python, Notes]
categories: [Data Science]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Notes about VirtualEnv and Visual Studio Code

<!--more-->

Create a Virtual Environment

```bash
python3 -m venv --copies /path/to/new/virtual/environment 
source venv/bin/activate #activate
deactivate # leave
```

Visual Studio Code: When you create a virtual env and open a folder where your code is sitting, then create the virtual environment there. Once you do, you can activate the environment in Visual Studio Code - look to the bottom corner and you can change the environment with the dropdown menu, or use the command palette and select the environment.
We have to use copies to ensure that we don't symlink to the system installed python3.

```
Command + P select interpreter
``` 

```
# settings.json
{
    "workbench.colorTheme": "Noctis Viola",
    "python.pythonPath": "/usr/local/bin/python3",
    "editor.fontFamily": "FiraCode-Retina",
    "editor.fontLigatures": true,
    "editor.fontSize": 15,
}
```

```
To start the Jupyter notebook, set up your virtual env.
Then Command + P and select interpreter to start Jupyter notebook. Restart Visual Studio Code if it doesn't work.
```



