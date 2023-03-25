# Dotfiles

User-specific application configuration is traditionally stored in dotfiles (files whose filename starts with a dot). Keeping track of these files with a version control system, such as Git, allows keeping track of changes and synchronizing dotfiles across various hosts.

This repo is intended to be initialized directly in the $HOME directory as a bare repository with aliases.

## Setup

*As a prerequisite you must have `git` installed*

#### 1. `echo ".cfg" >> .gitignore`

Add `.cfg` to your global `.gitignore` to avoid recursive tracking of this repo.

#### 2. `git clone --bare https://github.com/jamwest/dotfiles.git $HOME/.cfg`

Clone as a bare repository in your `$HOME` directory.

#### 3. `which git`

Find the location of `git` on your system.

#### 4. `alias config='<git-location> --git-dir=$HOME/.cfg/ --work-tree=$HOME'`

Set up an alias to send Git commands to `.cfg`, and also set `$HOME` as the work tree, while storing the Git state at `.cfg`.

#### 5. `config config --local status.showUntrackedFiles no`

Set a local configuration in `.cfg` to ignore untracked files.

#### 6. `config checkout`

Checkout the actual content from your `.cfg` repository to `$HOME`.

## Committing changes

#### 1. `config status`

List staged and unstaged changes.

#### 2. `config add <files-to-be-staged>`

Add the files to staging. This applies to both new files and editted files.

#### 3. `config commit -m "<commit-message>"`

Commit your staged changes and include a descriptive message.

#### 4. `config push -u origin main`

Push your changes to the `main` branch.
