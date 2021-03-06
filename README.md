# dotfiles

[![Build Status](https://travis-ci.com/craighurley/dotfiles.svg?branch=master)](https://travis-ci.com/craighurley/dotfiles)

## Introduction

A collection of scripts to bootstrap a clean install of macOS.

## Installation

1. Install xcode command line tools:

    ```sh
    xcode-select --install
    ```

1. Install macOS SDK headers:

    ```sh
    sudo installer -pkg /Library/Developer/CommandLineTools/Packages/macOS_SDK_headers_for_macOS_10.14.pkg -target /
    ```

1. Clone this repository by running the following commands:

    ```sh
    mkdir ~/Projects
    git clone https://github.com/craighurley/dotfiles.git ~/Projects/dotfiles
    ```

1. Install homebrew by running the following command:

    ```sh
    ~/Projects/dotfiles/.brew_install
    ```

1. Run the following command to do everything.  _Note: you will be prompted for your password a number of times during script execution._

    ```sh
    ~/Projects/dotfiles/bootstrap.sh
    ```

    Essentially, `bootstrap.sh` executes the following commands:

    ```sh
    # Create useful directories.
    ~/Projects/dotfiles/.directories

    # Backup existing dotfiles and symlink to the dotfiles in this project.
    ~/Projects/dotfiles/.dotfiles

    # Copy templates to ~. These files don't really belong in version control, hence they are not symlinked.
    ~/Projects/dotfiles/.templates

    # Configure sensible defaults in macOS.
    ~/Projects/dotfiles/.macos

    # Install command line package manager and additional command line tools.
    ~/Projects/dotfiles/.brew

    # Install command line package manager and additional applications.
    ~/Projects/dotfiles/.cask

    # Apply preferences to applications.
    ~/Projects/dotfiles/.preferences
    ```

1. Restart your computer.

1. If you want to automatically install applications from the _App Store_, open the _App Store_ and sign in, then run the following command:

    ```sh
    ~/Projects/dotfiles/.mas
    ```

## Post Install Tasks

1. Import Terminal config.
1. Import iTerm config.
1. Import gpg keys.
1. Import ssh keys.
1. Update exports in the `~/.extra` file:
    - github
    - homebrew
1. Sign into Firefox account to sync settings.
1. Download VS Code settings from gist.

## Update

Run the following commands to get the latest version of this project:

```sh
cd ~/Projects/dotfiles/
git pull origin master
```

## Feedback

Suggestions/improvements [welcome](https://github.com/craighurley/dotfiles/issues)!
