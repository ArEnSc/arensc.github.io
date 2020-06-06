---
layout: post 
title: Python VirtualEnv
tags: [VirtualEnv, Python, Notes]
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

Visual Studio Code, when you create a virtual env and use open a folder, where your code is sitting, then create the virtual environment there. Once you do you can activate the environment in visual studio code look to the bottom corner and you can change the environment with the dropdown menu, or use the command pallete and select the environment.
We have to use copies to ensure that we don't symlink to the system installed python3

```
command + p select interpreter
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
To start the juptyer notebook setup your virtual env.
Then command + p and select interpreter to start juptyer notebook. Restart visual studio code if it doesn't work.
```



