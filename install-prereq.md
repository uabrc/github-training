# Installation and Prerequisites

1. Install https://code.visualstudio.com/

2. Install git

    1. Windows
  
        1. https://git-scm.com/download/win
        2. Use all default options.
    
    2. MacOS
  
        1. https://git-scm.com/download/mac
        2. Use your preferred option.
        3. If you have never done any of these, try homebrew first.
    
    3. Linux
  
        1. https://git-scm.com/download/linux
        2. Pick your flavor and install at the terminal by using the supplied command at the link above.
        3. You may need to provide sudo privileges.
    
3. Verify VSCode and git

    1. Open VSCode.
    2. Open a new terminal by clicking "Terminal" at the top menu bar and clicking "New Terminal".
    3. The terminal panel should open at the bottom of the VSCode window.
    4. Click on the terminal panel to bring it into focus, then type `git --version`.
    5. You should see something similar to, but probably different from, `git version 2.33.0.windows.2`.

4. Configure git to be able to make best use of git and GitHub. All changes need to be associated with a person, because GitHub is collaborative.

    1. Open a new terminal.
    2. Enter your natural name with the command `git config --global user.name "$NAME"`
    3. Enter your email address with the command `git config --global user.email "$EMAIL"`.
  
