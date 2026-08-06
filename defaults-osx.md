# defaults

```bash
defaults write <ns> <setting> -<type> <value>
```


## settings

```bash
# Spaces-animations
defaults write com.apple.dock workspaces-swoosh-animation-off -bool true

# No 3d-dock
defaults write com.apple.dock no-glass -bool true

# iTunes links to library
defaults write com.apple.iTunes invertStoreLinks -bool true

# Make hidden apps translucent in dock
defaults write com.apple.Dock showhidden -bool true

# Prevent .DS crap on network shares
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# Show plaintext e-mail
defaults write com.apple.mail PreferPlainText -bool true

# Default to extended Browse dialogue
defaults write -g NSNavPanelExpandedStateForSaveMode -bool true

# Song notification from iTunes dock icon
defaults write com.apple.dock itunes-notifications -bool true

# Current directory as default search directory
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

# Enable quarantine dialog
defaults write com.apple.LaunchServices LSQuarantine -bool true

# Mac App Store debug menu
defaults write com.apple.appstore ShowDebugMenu -bool true
```
