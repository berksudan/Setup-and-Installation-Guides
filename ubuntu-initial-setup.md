# Ubuntu Initial Setup

This guide outlines the essential steps to set up a fresh Ubuntu installation.

## System and Application Setup

- **Install Sublime Text Editor:** Install Sublime via Snap and add it to the dock.
  ```bash
  sudo snap install sublime-text --classic
  ```
    - Add this to Preferences: `"save_on_focus_lost": true,`
- Run system updates and package installations:
  ```bash
  sudo snap refresh
  sudo apt update && sudo snap refresh && sudo apt upgrade && sudo apt autoremove
  sudo apt install -y build-essential libpq-dev python3-dev
  ```
- **Apply firmware updates** through Ubuntu's Software Updater and restart.
- **Disable system sounds** in Ubuntu Sound Settings.
- **Set Overamplification** in Ubuntu Sound Settings.
- Configure trash settings to automatically delete files after **30 days**.
- Enable Fingerprint Log in (if possible)

## Applications Installation

- **Spotify**: Install via Snap.
  ```bash
  sudo snap install spotify
  ```
  - Download all major playlists for offline listening.
- **Pinta**: Install via Snap.
  ```bash
  sudo snap install pinta
  ```
- **Flameshot**: Install the APT version and configure settings:
  ```bash
  sudo apt install flameshot
  ```
  - Then, set the `Print Screen` shortcut: `sh -c "flameshot gui && sleep 3 && pkill flameshot"`

  - Configure the screenshot folder and import the following configuration as `flameshot.conf`(Replace `<USER>` with your username):
    ```ini
    [General]
    autoCloseIdleDaemon=true
    checkForUpdates=true
    contrastOpacity=188
    drawColor=#ff0000
    drawThickness=4
    filenamePattern=Screenshot_Flameshot_%F_%T
    saveAfterCopy=true
    savePath=/home/<USER>/Pictures/Screenshots
    savePathFixed=true
    ```

- **Vim**: Install via APT:
  ```bash
  sudo apt install vim
  ```
- **Firefox**: Change the default search engine to DuckDuckGo and sign in.

- **GPaste**: Set up gpaste clipboard manager:
  ```bash
  sudo apt install gpaste
  ```
  - Increase gpaste capacities to very high (if you have enough disk space), such as `Max history size`=`10000`, `Max memory usage`=`16383 (MB)`
  - Run: `sudo apt install gnome-shell-extension-gpaste`
  - Log out and log in (on Wayland)
  - Run: `sudo apt install gnome-shell-extension-prefs`
  - Next, launch `Gnome Extensions` app, scroll down and turn on the slider icon to enable GPaste indicator
- **PyCharm**: Install via Snap:
  ```bash
  sudo snap install pycharm-community --classic
  ```
  - In PyCharm, change the "Toggle Case" shortcut from "Ctrl+Shift+U" to "Alt+Shift+U", see: https://stackoverflow.com/a/51160081
- **Okular - PDF Editor**: Install via APT:
  ```bash
  sudo apt install okular
  ```
- **VLC Media Player:** Install via Snap:
  ```bash
  sudo snap install vlc
  ```

## Hibernation Setup and Power Management

- Enable hibernation (set your swap as 1.9*ram) following this guide:
  - [YouTube Tutorial](https://youtu.be/qJDJHOaM6FE?si=jDcgtN3RAmrs2Q73)
  - [Enable Hibernate on Ubuntu 21.10](https://ubuntuhandbook.org/index.php/2021/08/enable-hibernate-ubuntu-21-10/)
- Configure hibernation for lid close behavior: [Change Lid Close Behavior on Ubuntu](https://ubuntuhandbook.org/index.php/2020/05/lid-close-behavior-ubuntu-20-04/)
- Change swappiness using here: https://askubuntu.com/questions/103915/how-do-i-configure-swappiness
## Additional Software and Configurations

- **OpenAI Sessions**: Set up and pin the sessions in the browser.
- **Terminal Appearance**: Customize the terminal look and feel.
- **Nautilus Bookmarks**: Add the following directories:
    - `~/Desktop/repos`
    - `~/opt`
    - `/opt`
- **Gio Trash**: Use `gio trash` (or its modern alternative) for trashing files via the terminal.
