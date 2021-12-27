# python-template
A simple template for building python projects with venv and pyinstaller.
There's not much in the way of error catching, as the purpose of the scripts is to perform repetitive commands in a faster manner.

## Key Scripts

### full_project_rebuild.bat
Runs initialize_venv.bat, then build_binary.bat.

### initialize_venv.bat
Erases existing venv deployment and rebuilds to directory 'venv'.
Subsequently runs install_requirements.bat

### install_requirements.bat
Installs any dependencies listed in requirements.txt to the 'venv' instance. Has a fallback in case of ssh issues.

### build_binary.bat
Erases previous build and rebuilds based on .spec file.
Assumes:
 - Pyinstaller is already installed in the virtual-environment
 - The .spec file is updated and points to all the correct files

## Useful tools

## keybindings.json in VSCode
Using the CTRL + SHIFT + P search bar, and searching for ">Preferences: Open Keyboard Shortcuts (JSON)" will give access to the keybindings.json file. It can be used to store quick keybindings for calling scripts. See below for examples
```
// Place your key bindings in this file to override the defaults
[
    {
        "key": "ctrl+alt+r",
        "command": "workbench.action.terminal.sendSequence",
        "args": {
          "text": ".\\install_requirements.bat\u000D"
        }
    },
        {
        "key": "ctrl+alt+v",
        "command": "workbench.action.terminal.sendSequence",
        "args": {
          "text": ".\\initialize_venv.bat\u000D"
        }
    }
]
```