# Setting up the new computer

## Install apps

Applications to install:
- WebStorm
- IntelliJ Idea
- VS Code
- iTerm2
- Chrome
- Firefox
- Affinity Design
- Affinity Photo
- Franz
- Notion
- Spotify
- Commander One and ask for license transfer to the new machine
- Dropbox
- Docker
- Folx
- Logi Options
- Plex Media Server
- Unrchiver

Optionally:
- Reason Studio
- Audacity
- Kindle
- Renoise
- TeamViewer
- Zoom
- Skype
- Typelight
- Adobe XD
- Onyx
- Luminar 3

## Other settings

### Configure terminal

1. Install **iTerm2** via `brew`:
```
brew cask install iterm2
```
Or [download](https://www.iterm2.com/downloads.html) from website.

2. Set the color theme:

Install [Solarized Dark Theme](https://raw.githubusercontent.com/mbadolato/iTerm2-Color-Schemes/master/schemes/Solarized%20Dark%20-%20Patched.itermcolors). Save the file to `Downloads` and open it. The iTerm will install it. Apply the theme via `Prerences -> Profiles -> Colors -> Load presets`.

3. Install **Oh My Zsh**

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

4. Install `Powerlevel10k` theme:
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

5. Install `Meslo LG M for Powerline` from [here](https://github.com/powerline/fonts/blob/master/Meslo%20Slashed/Meslo%20LG%20M%20Regular%20for%20Powerline.ttf) or `Meslo Nerd patched` from [here](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k)

6. Install `Autosuggestion`:
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

7. Update `~/.zshrc` with following [config](.zshrc).

8. Fix terminal in `Webstorm` if broken following guide [here](https://giorgosgaganis.com/2016/11/25/making-powerline-fonts-work-inside-intellij-idea-terminal/)

Original guide can be found [here](https://gist.github.com/kevin-smets/8568070) and [here](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k)

### Configure `Home` and `End` keys for full keyboard on `Mac`

Create new `DefaultKeyBinding.dict` file in Library:
```
sudo bash 
mkdir -p ~/Library/KeyBindings ; cd ~/Library/KeyBindings
vim DefaultKeyBinding.dict
```

Copy the following content:
```
{
  /* Remap Home / End keys */
  /* Home Button*/
  "\UF729" = "moveToBeginningOfLine:"; 
  /* End Button */
  "\UF72B" = "moveToEndOfLine:"; 
  /* Shift + Home Button */
  "$\UF729" = "moveToBeginningOfLineAndModifySelection:"; 
  /* Shift + End Button */
  "$\UF72B" = "moveToEndOfLineAndModifySelection:"; 
  /* Ctrl + Home Button */
  "^\UF729" = "moveToBeginningOfDocument:"; 
  /* Ctrl + End Button */
  "^\UF72B" = "moveToEndOfDocument:"; 
  /* Shift + Ctrl + Home Button */
  "$^\UF729" = "moveToBeginningOfDocumentAndModifySelection:";
  /* Shift + Ctrl + End Button*/
  "$^\UF72B" = "moveToEndOfDocumentAndModifySelection:"; 
}
```

Original setup from [medium post](https://medium.com/@elhayefrat/how-to-fix-the-home-and-end-buttons-for-an-external-keyboard-in-mac-4da773a0d3a2)
