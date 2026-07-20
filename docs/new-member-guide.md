# New Member Guide

This is the onboarding SOP for new students joining the Waitt Group.
Work through it in order during your first week or two — it ends with
an introductory assignment that ties everything together.

Most of our work runs on **Python and Linux command-line tools**, so a
good chunk of onboarding is getting comfortable with both before you
touch any research code.

## 1. Get accounts set up

1. Create a [GitHub account](https://github.com/join) if you don't
   already have one.
2. Create an [ACCESS account](https://access-ci.org/) — this is what
   the group's compute allocations run through.
3. Email the PI to get added to the group's GitHub org and shared
   Drive. Send it to **waittc@trine.edu** with the subject line
   `[Your Name] account set up`.

   Copy and paste this into your email, filling in your details:

   ```
   Hi Dr. Waitt,

   I'm setting up my accounts for the group.

   ACCESS username: <your ACCESS username>
   GitHub username: <your GitHub username>

   Thanks,
   <Your Name>
   ```

## 2. Set up a Linux command-line environment

- **Mac**: Linux-compatible command-line tools are built in. Open
  `Terminal` (Applications → Utilities → Terminal) and you're ready.
- **Windows**: Install the Windows Subsystem for Linux (WSL), which
  gives you a real Linux environment alongside Windows:
  ```
  wsl --install
  ```
  Restart when prompted, then finish setting up your Ubuntu
  username/password. Use this Ubuntu terminal for all command-line
  work going forward.
- **Chromebook**: Turn on Linux (Crostini) under
  `Settings → Advanced → Developers → Linux development environment`,
  then use the Terminal app it installs.

Once you have a terminal, work through the [Software Carpentry Unix
Shell lesson](https://swcarpentry.github.io/shell-novice/) to learn
basic commands (navigating directories, moving/copying files, etc.).

## 3. Install Python and Jupyter

1. Download and install **Python 3.12.2** from the official source:
   [python.org/downloads/release/python-3122](https://www.python.org/downloads/release/python-3122/)
   - On Windows, check **"Add Python to PATH"** during installation.
2. Confirm the install:
   ```bash
   python3 --version
   ```
3. Install Jupyter Notebook:
   ```bash
   pip install notebook
   ```
4. Launch it to confirm it works:
   ```bash
   jupyter notebook
   ```
5. Work through the [Software Carpentry Python
   lesson](https://swcarpentry.github.io/python-novice-inflammation/)
   to learn basic Python.

## 4. Install the group's Python packages

```bash
pip install ase==3.29.0 rdkit==2026.3.4
```

## 5. Learn Git and GitHub

1. Work through the [Software Carpentry Git
   lesson](https://swcarpentry.github.io/git-novice/) to learn the
   basics (commit, push, pull, branches).
2. **Fork the group wiki repo**: go to
   [waittgroup/waittgroup.github.io](https://github.com/waittgroup/waittgroup.github.io)
   on GitHub and click **Fork** to create your own copy.
3. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/waittgroup.github.io.git
   ```
4. Make a small change (e.g. add your name to [People](people.md)),
   commit it, and push it to your fork:
   ```bash
   git checkout -b my-first-change
   git add docs/people.md
   git commit -m "Add myself to the People page"
   git push origin my-first-change
   ```
5. Open a pull request from your fork's branch back to
   `waittgroup/waittgroup.github.io` and ask your mentor to review it.

## 6. Complete the introductory assignment

Once your environment is set up, work through the
[Introductory Assignment](intro-assignment.md) — it's your first
hands-on exercise with ASE, RDKit, and the tools above.

## 7. Group norms

- SOPs live in this wiki — if you figure out a workflow that isn't
  documented, add it (see `CLAUDE.md` in the repo for formatting
  conventions).
- Ask questions early — computational workflows have a learning curve.

## 8. First tasks

- _TBD — mentor assigns a starter task during week 1._
