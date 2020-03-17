# dev-setup
Notes to help guide me the next time I reinstall OSX or set up some development tools

## OSX System Preferences
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
    - If you're still using a Logitech Mouse with GHub disable mouse acceleration by:
        - Open up terminal and check if mouse acceleration is enabled by typing 
        `defaults find scaling`
        - In terminal type `defaults write .GlobalPreferences com.apple.mouse.scaling -1.` to disable mouse acceleration completely
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

## Applications and Development Tools
1. Install Command Line Tools
    1. Open terminal and type `xcode-select --install`
1. [Install Homebrew](https://brew.sh/)
    1. Use `brew search _____` to search formulae and casks
    1. Use `brew cask install` to install casks, aka apps, from the command line
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
1. [Download GitHub Desktop](https://desktop.github.com/) and install it.
    1. Change preferences in GitHub Desktop to preferred editor and shell
    1. Remember that you can use 1. 1. 1. 1. to make an ordered list in markdown and it will automatically update the number order if you delete an item from the list.
    1. Reference of [GitHub flavored markdown](https://guides.github.com/features/mastering-markdown/)
1. Install zsh
    1. Open terminal and type `brew install zsh`
    1. Install Oh My Zsh `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
    1. Add (enable) plugins by opening .zshrc file and adding in plugins, one per line, at the specified location in the document. Here are some you were using:
        - git
        - osx
        - zsh_reload

1. Install Node Version Manager (NVM)
    1. Open terminal and type `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | zsh)`
    1. Restart iterm

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
    
1. Change Text Edit Settings so if you ever edit something in this app, the format won't change
    - In Preferences, in New Document, change format to plain text
    - In Preferences, in Open and Save, change Opening Files and Saving Files to Unicode (UTF-8)


