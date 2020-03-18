# dev-setup
Notes to help guide me the next time I reinstall OSX or set up some development tools

## OSX System Preferences
---
1. After a fresh install, update OSX with any available security updates
1. Create a new admin user, log in to this new user to finalize it's setup, and then log out. From now on, only use your previous user account. This is so you always have an admin user you can log in with if something happens with your other user-account.
1. In Security and Privacy
    - Immediately Require password after computer sleeps
    - Require admin password to access system wide preferences
    - Check (enable) apps from App Store and identified developers
    - Enable File-Vault and write down the recovery key and keep it in a safe place
    - Enable the firewall
    - Check (enable) stealth mode
    - Uncheck (disable) Siri and dictation
    - Uncheck (disable) Location-based suggestions, Significant Locations, Location-Based Apple Ads, Homekit (if you aren't using it)
    - Uncheck (disable) any analytic reporting
    - Limit Ad Tracking 
    - Check ("Show location icon in menu bar when System Services request your location)
1. In Spotlight
    - Uncheck (disable) Spotlight Suggestions
    - Uncheck (disable) Allow Spotlight Suggestions in Look Up
1. In Display
    - Select Sunset to Sunrise
1. In Energy Saver
    - Computer sleep: Never
    - Put hard disks to sleep when possible
    - Wake for network access
    - Start up automatically after power failure
1. In Keyboard
    - Uncheck any shortcuts you don't use, especially the Spotlight settings
    - Change Key Repeat all the way to Fast
    - Change Delay Until Repeat all thew way to Short
    - Turn dictation On
    - Check (enable) Use Enhanced Dictation which allows offline use
1. In Mouse
    - If you're still using a Logitech Mouse with GHub disable mouse acceleration by...
        - Open up your terminal and check if mouse acceleration is enabled by typing 
            ```
            defaults find scaling
            ```
        - In terminal type the following to disable mouse acceleration completely
            ```
            defaults write .GlobalPreferences com.apple.mouse.scaling -1.
            ```
    - Make sure scrolling speed is at the 5th notch or lower, so that mouse scrolling still works when using Synergy to control another mac computer
1. In Printer
    - Install Brother HL-2270DW driver (find on web if needed, or just grab it from another mac that's on the network)
1. In Sound
    - Check (enable) Show volume in menu bar
1. In iCloud
    - Verify Desktop and Documents Folders aren't selected as being synced
1. In Software Update
    - Automatically download and install updates for everything except macOS updates
1. In Network
    - In WiFi, Advanced, DNS, Under DNS Servers, input Cloudflare's DNS:
        - 1.1.1.1
        - 1.0.0.1
        - 2606:4700:4700::1111
        - 2606:4700:4700::1001 
    - In Wifi, Advanced, DNS, Under Search Domains, input:
        - .local
1. In Bluetooth
    - Uncheck "Show Bluetooth in menu bar"
1. In Extensions
    - Check (enable) whatever extensions you want available
1. In Sharing
    - Check/Uncheck whatever you want to share or not share 
    - You currently have Printer and File sharing enabled
1. In Users & Groups
    - Double check login items (do this after you install certain Applications as well)
1. In Accessibility
    - Uncheck (disable) Shake mouse pointer to locate

# Applications and Development Tools

### Install Command Line Tools
1. Open your terminal and type 
    ```
    xcode-select --install
    ```
---
### Homebrew
1. [Install Homebrew](https://brew.sh/)
    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    ```
1. Tap homebrew's cask/fonts
    ```
    brew tap homebrew/cask-fonts
    ```
    - To install a font (where inconsolata is the name of the font you wish to install) 
    ```
    brew cask install font-inconsolata
    ```
1. Other Tips
    1. Use `brew search _____` to search formulae and casks
    1. Use `brew cask install ____` to install casks, aka apps, from the command line
    1. Use `brew cask outdated` to see what apps can be updated
    1. Use `brew cask upgrade` to update all of the apps that can be updated  
    1. Here is a list of the apps you currently have installed through `brew cask install`
        - alfred
        - firefox
        - bitwarden
        - iterm2
        - hazel
        - league-of-legends
        - appcleaner
        - slack
        - balsamiq-wireframes
        - resilio-sync
        - native-access
        - scrivener
        - vscodium
        - scapple
        - tor-browser
        - pocket-casts
        - spotify
        - liteicon
        - mountain-duck
        - evernote
        - imageoptim
        - vlc
        - synergy
        - 4k-video-downloader
        - pulse-sms
        - calibre
        - zoomus
        - anki
---
### Github
1. [Download GitHub Desktop](https://desktop.github.com/) and install it.
1. Change preferences in GitHub Desktop to preferred editor (VSCodium) and shell (iterm2)
1. Remember that you can create an ordered list by using "1." for each item. This way it will automatically update the number order if you rearrange or delete an item from the list. Example:
    ```
    1. First ordered item 
    1. Second ordered item
    1. Third ordered item
    ```
1. Reference of [GitHub flavored markdown](https://guides.github.com/features/mastering-markdown/)

---    
### Zsh   
1. Install zsh
    ```
    brew install zsh
    ```
1. Change the default shell to zsh
    ```
    chsh -s /bin/zsh
    ```
---
### Oh My Zsh
1. Install Oh My Zsh 
    ```
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
1. Add (activate) plugins by opening .zshrc file and adding in plugins, one per line, at the specified location in the document. Here are some you are using:
    - `git`
    - `osx`
    - `zsh_reload`
1. Add the line below to remove the user@user prompt at the beginning of every line
    ```
    export DEFAULT_USER=`whoami`
    ```    
1. Uncomment the following lines to enable them
    ```
    HYPHEN_INSENSITIVE="true"
    COMPLETION_WAITING_DOTS="true"
    ```    
---
### Powerlevel10k Theme    
1. Install Powerlevel10k theme by typing 
    ```
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
    ```
1. Open .zshrc file and set the theme 
    ```
    ZSH_THEME="powerlevel10k/powerlevel10k"
    ```
1. The powerline fonts will be installed in the configuration wizard in the next step. Otherwise download the fonts manually from here: https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k

1. Close iTerm2 and reopen it (don't use src to restart) to start the powerlevel10k configuration wizard. And if you ever want to run the configuration wizard again, simply type
    ```
    p10k configure
    ```
---
### Install zsh-syntax-highlighting
1. Clone the repository 
    ```
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    ```
1. Add (activate) the plugin in the .zshrc file, and **REMEMBER - This must be the last plugin listed!**
    ```
    zsh-syntax-highlighting
    ```
1. Restart iTerm
---
### Install zsh-autosuggestions
1. Clone the repository
    ```
    git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    ```
1. Add (activate) the plugin in the .zshrc file
    ```
    zsh-autosuggestions
    ```
---
### iTerm2 Preferences
1. Modify iterm2 Preferences
    1. Duplicate default profile so you can always have the default as a backup
    2. Increase font size as needed
    3. Add these MacOS shortcuts for more movability using the keyboard (located under Profiles -> Keys -> +) (learned from  http://sourabhbajaj.com/mac-setup/iTerm/)
        - shortcut: ⌘←, Action: Send Escape Sequence, Esc+: OH
        - shortcut: ⌘→, Action: Send Escape Sequence, Esc+: OF
        - shortcut: ⌥←, Action: Send Escape Sequence, Esc+: b
        - shortcut: ⌥→, Action: Send Escape Sequence, Esc+: f
---



### NVM & Node
1. Install Node Version Manager (NVM)
    1. Install NVM. Open iterm and type 
        ```
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | zsh
        ```
    1. Restart iterm (you can do this by either typing `src`, if you have activated the zsh_reload plugin, or just quit and re-open iTerm)
    1. Make sure NVM has been installed
        ```
        nvm --version
        ```
        You should get a response like this:
        ```
        ❯ nvm --version
        0.35.3
        ```

1. Install Node
    1. List the available versions to install
        ```
        nvm ls-remote --lts
        ```
    1. Install the latest version of a release by simply using it's name
        ```
        nvm install --lts=Dubnium
        ```
---
## VSCodium
1. Install Extensions for VSCodium
    - Prettier
    - Visual Studio IntelliCode
    - Code Spell Checker
    - IntelliSense for CSS class names in HTML
    - npm Intellisense
    - Path Intellisense
    - SCSS IntelliSense
    - Tailwind CSS IntelliSense
    - Tailwind sass syntax

## Text Edit    
1. Change Text Edit Settings so if you ever edit something in this app, the format won't change
    - In Preferences, in New Document, change format to plain text
    - In Preferences, in Open and Save, change Opening Files and Saving Files to Unicode (UTF-8)


