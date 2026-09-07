 FRC SCOUTING APP - SETUP & USAGE GUIDE
====================================================

This guide covers everything you need to install and use the app.
No programming knowledge required - just follow the steps in order.


----------------------------------------------------
STEP 1: INSTALL PYTHON (one-time setup)
----------------------------------------------------

The app runs on Python. If you don't already have it installed:

  1. Go to https://www.python.org/downloads/
  2. Download and install the latest version (3.11 or newer).

  WINDOWS USERS: On the first install screen, check the box that says
  "Add python.exe to PATH" before clicking Install.

  MAC USERS: You must use the installer from python.org (the link
  above). Do NOT install Python through Homebrew - it will be missing
  a piece the app needs to display its windows.

To check if Python is already installed, open a terminal
(Command Prompt on Windows, Terminal on Mac) and type:

    python3 --version

If you see a version number of 3.11 or higher, you're already set.


----------------------------------------------------
STEP 2: GET THE APP FOLDER READY
----------------------------------------------------

  1. Unzip the folder you were given (frc_scouting_app) somewhere
     easy to find, like your Desktop.
  2. Open a terminal (Command Prompt on Windows, Terminal on Mac).
  3. Navigate into the folder. For example, if it's on your Desktop:

       WINDOWS:   cd Desktop\frc_scouting_app
       MAC:       cd Desktop/frc_scouting_app

  4. Install the one thing the app needs (matplotlib, for the charts)
     by typing:

       WINDOWS:   pip install -r requirements.txt
       MAC:       pip3 install -r requirements.txt

     This only needs to be done once. It requires an internet
     connection, but only for this one-time install - the app itself
     never uses the internet.


----------------------------------------------------
STEP 3: OPEN THE APP
----------------------------------------------------

From that same terminal window, inside the frc_scouting_app folder,
type:

    WINDOWS:   python main.py
    MAC:       python3 main.py

The app window should open. Every time you want to use the app again,
just repeat this step (open a terminal, navigate to the folder, run
the command above).

TIP (optional): You can make this easier by creating a shortcut:
  - WINDOWS: Make a new text file, put "python main.py" inside it,
    save it as "Open App.bat" in the frc_scouting_app folder, and
    double-click that file from now on instead of using the terminal.
  - MAC: Make a new text file, put these two lines inside it:
        cd "$(dirname "$0")"
        python3 main.py
    Save it as "Open App.command" in the frc_scouting_app folder.
    Then, in Terminal, run this once to make it clickable:
        chmod +x "Open App.command"
    After that, double-click "Open App.command" to launch the app.


----------------------------------------------------
STEP 4: USING THE APP
----------------------------------------------------

The app has five tabs across the top:

  - MATCH LOOKUP    Type a match number and press Go to see both
                     alliances' stats, predicted scores, win odds,
                     and a score distribution chart.
  - TEAM LOOKUP     Type a team number to see that team's stats and
                     score history chart.
  - PICK LIST       Ranked list of teams for alliance selection.
  - RANKINGS        Full event rankings (use the Sort By dropdown to
                     change ordering).
  - MATCH SIMULATOR Type in any six team numbers (3 red, 3 blue) to
                     see a hypothetical matchup's predicted odds and
                     scores, even if that match isn't on the schedule.

IMPORTING YOUR DATA:
  Use the "Data" menu at the top of the window:
    - "Import Match Schedule" - loads the match schedule CSV
    - "Import Raw Data"       - loads your scouting data CSV
  When importing, you'll be asked whether this is:
    - "Update current"    - adds to/updates the existing competition
    - "New competition"   - wipes old data first, for a fresh event
  Pick "New competition" whenever you're starting a new event to
  avoid mixing data between events.

SETTING YOUR TEAM NUMBER:
  Data menu -> "Set My Team Number" (used to highlight your team).

RECALCULATING:
  The app recalculates automatically, but if something looks off you
  can force a refresh with Data menu -> "Recalculate Now".


----------------------------------------------------
STEP 5: PRINTING MATCH RESULTS (optional)
----------------------------------------------------

If you have an 80mm thermal receipt printer:

  1. Install the printer's driver and plug it in, as normal for any
     printer on your computer (this app doesn't need anything special
     beyond the normal driver install).
  2. In the app, go to Data menu -> "Select Receipt Printer..." and
     choose it from the list. You only need to do this once - the app
     remembers your choice.
  3. On the Match Lookup tab, after looking up a match, click the
     "Print Results" button next to Go. This prints one receipt for
     Red alliance and one for Blue alliance.

If no printer is selected yet, the app will prompt you to pick one
automatically the first time you click Print Results.


----------------------------------------------------
TROUBLESHOOTING
----------------------------------------------------

"python is not recognized" / "command not found"
  -> Python isn't installed, or wasn't added to PATH. Reinstall from
     python.org and (Windows) make sure "Add python.exe to PATH" is
     checked.

App window doesn't appear / errors mentioning "tkinter" (Mac only)
  -> You likely installed Python through Homebrew. Uninstall it and
     reinstall using the official installer from python.org instead.

"No module named matplotlib"
  -> Run the pip install command from Step 2 again.

Printer not showing up in "Select Receipt Printer..."
  -> Make sure the printer's driver is installed and it shows up as a
     normal printer in your computer's own Printers/Devices settings
     first. The app only sees printers your operating system already
     knows about.

For anything else, or for the full version history of the app, see
README.md in this same folder.
